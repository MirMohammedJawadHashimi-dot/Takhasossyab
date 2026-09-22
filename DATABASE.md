# Takhassosyab Database Design

## 1. Database Strategy

Primary Database:
PostgreSQL

The database must be designed for security, consistency, maintainability and future scalability.

---

## 2. Core Entities

### Users
Stores the main account information.

Fields:
- id
- email
- phone
- password_hash
- role
- status
- created_at
- updated_at

---

### Profiles
Stores public professional identity information.

Fields:
- id
- user_id
- display_name
- username
- bio
- profile_image
- location_id
- languages
- website
- created_at
- updated_at

Relationship:

User 1 ─── 1 Profile

---

### Specialists

Stores specialist-specific information.

Fields:
- id
- profile_id
- professional_title
- experience_years
- availability
- verification_level
- average_rating
- total_reviews
- created_at
- updated_at

Relationship:

Profile 1 ─── 0..1 Specialist

---

## 3. Skills

### Skills

Fields:
- id
- name
- slug
- category_id
- description

### Specialist Skills

Fields:
- specialist_id
- skill_id
- proficiency_level

Relationship:

Specialist N ─── N Skill

---

## 4. Categories

Fields:
- id
- name
- slug
- description
- parent_id

Categories can support hierarchical structures.

Example:

Technology
 ├── Software Development
 │    ├── Web Development
 │    ├── Mobile Development
 │    └── Backend Development
 └── Cyber Security

---

## 5. Locations

### Countries

Fields:
- id
- name
- code

### Provinces

Fields:
- id
- country_id
- name

### Cities

Fields:
- id
- province_id
- name

Profiles can reference a city.

---

## 6. Certificates

Fields:
- id
- specialist_id
- title
- issuer
- issue_date
- expiry_date
- credential_id
- document_url
- verification_status
- created_at

---

## 7. Verification

### Verification Records

Fields:
- id
- user_id
- verification_type
- status
- submitted_at
- reviewed_at
- reviewer_id
- notes

Verification types may include:

- Identity
- Profile
- Certificate
- Professional

---

## 8. Portfolio

### Projects

Fields:
- id
- specialist_id
- title
- description
- category_id
- project_url
- cover_image
- created_at
- updated_at

### Project Media

Fields:
- id
- project_id
- media_type
- media_url
- sort_order

Relationship:

Specialist 1 ─── N Projects

Project 1 ─── N Media

---

## 9. Reviews

Fields:
- id
- specialist_id
- reviewer_id
- rating
- comment
- status
- created_at
- updated_at

Rules:

- Rating must be validated.
- Users cannot create unlimited duplicate reviews.
- Review moderation must be supported.

---

## 10. Posts

Fields:
- id
- author_id
- title
- content
- visibility
- status
- created_at
- updated_at

---

## 11. Videos

Fields:
- id
- author_id
- title
- description
- video_url
- thumbnail_url
- duration
- category_id
- status
- views
- created_at
- updated_at

Future media processing may generate multiple video resolutions.

---

## 12. Comments

Fields:
- id
- user_id
- post_id
- video_id
- parent_id
- content
- status
- created_at
- updated_at

Parent comments allow threaded discussions.

---

## 13. Follows

Fields:
- follower_id
- following_id
- created_at

Used for professional networking and content discovery.

---

## 14. Messages

### Conversations

Fields:
- id
- created_at
- updated_at

### Conversation Members

Fields:
- conversation_id
- user_id
- joined_at

### Messages

Fields:
- id
- conversation_id
- sender_id
- content
- message_type
- created_at
- read_at

---

## 15. Notifications

Fields:
- id
- user_id
- type
- title
- body
- data
- read_at
- created_at

---

## 16. Organizations

Fields:
- id
- name
- slug
- description
- logo_url
- website
- location_id
- verification_status
- created_at
- updated_at

---

## 17. Organization Members

Fields:
- organization_id
- user_id
- role
- joined_at

---

## 18. Reports

Fields:
- id
- reporter_id
- target_type
- target_id
- reason
- description
- status
- reviewed_by
- created_at
- resolved_at

Used for moderation and safety.

---

## 19. Audit Logs

Fields:
- id
- user_id
- action
- entity_type
- entity_id
- metadata
- ip_address
- created_at

Important security-sensitive actions should be auditable.

---

## 20. Database Relationships

Main relationship structure:

User
 │
 ├── Profile
 │     │
 │     └── Specialist
 │            ├── Skills
 │            ├── Certificates
 │            ├── Projects
 │            ├── Videos
 │            └── Reviews
 │
 ├── Posts
 ├── Messages
 ├── Notifications
 └── Organizations

---

## 21. Indexing Strategy

Indexes should be created for frequently searched fields.

Important candidates:

- users.email
- users.phone
- profiles.username
- profiles.location_id
- specialists.verification_level
- specialist_skills.skill_id
- projects.specialist_id
- videos.category_id
- reviews.specialist_id

Indexes must be added based on measured query patterns.

---

## 22. Data Integrity

The database must use:

- Primary keys
- Foreign keys
- Unique constraints
- Check constraints
- Appropriate indexes
- Transactions
- Timestamps
- Soft deletion where appropriate

---

## 23. Privacy

Sensitive data must be separated from public profile data.

Passwords must never be stored in plain text.

Private documents such as identity documents and certificates should use controlled access rather than public URLs.

---

## 24. Scalability Strategy

Initial:

Application
   ↓
PostgreSQL

Growing system:

Application
   ↓
Redis Cache
   ↓
PostgreSQL
   +
Search Engine
   +
Object Storage

Large-scale architecture may later introduce:

- Read replicas
- Partitioning
- Background jobs
- Message queues
- Dedicated search infrastructure
- Distributed media processing

Scaling decisions should be based on real system measurements.

---

## 25. Database Migration

Database changes must be version-controlled through migrations.

The application must never depend on manually changing production tables.

---

## 26. Important Engineering Rule

The database should remain simple enough to maintain while providing a strong foundation for future growth.

Do not prematurely create unnecessary microservices or databases.

Start with a modular relational architecture and evolve when real requirements justify the change.