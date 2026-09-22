# Takhassosyab MVP

## MVP Goal

The first version of Takhassosyab is a real and usable specialist discovery platform.

The core experience is:

**Discover → View → Verify → Connect**

The MVP is not the final version of Takhassosyab. It is the foundation for a secure, scalable and professional platform.

---

## User Roles

### 1. Visitor

Visitors can:

- Browse the platform
- Search for specialists
- Filter specialists
- View public specialist profiles
- View skills and experience
- View public portfolios
- View verification status

### 2. Registered User

Registered users can:

- Create an account
- Create and edit their profile
- Search for specialists
- Save specialists
- Contact specialists
- Send contact requests
- Report inappropriate content or users

### 3. Specialist

Specialists can:

- Create a professional profile
- Add professional title
- Add skills and expertise
- Add work experience
- Add location
- Add languages
- Add portfolio projects
- Add certificates
- Request verification
- Set availability
- Receive contact requests
- Manage their professional information

### 4. Administrator

Administrators manage the platform and its users.

Admin capabilities include:

- View users
- Search users
- Block users
- Unblock users
- Suspend users
- Manage specialist profiles
- Review verification requests
- Review certificates and documents
- Manage categories
- Manage locations
- Moderate content
- Manage reports
- Manage platform settings
- Manage administrator roles and permissions
- View audit logs

---

## Core MVP Features

### Authentication

- Registration
- Login
- Logout
- Password hashing
- Email verification
- Secure authentication
- Role-based authorization

### User Profiles

Users can create and manage basic professional or personal profiles.

### Specialist Profiles

Each specialist can have:

- Name
- Professional title
- Profile photo
- Bio
- Skills
- Experience
- Location
- Languages
- Portfolio
- Certificates
- Verification status
- Availability
- Contact options

### Search & Discovery

Users can search specialists by:

- Name
- Skill
- Profession
- Category
- Province
- City
- Verification status

### Specialist Profile Page

The profile page should clearly present:

- Identity
- Professional expertise
- Experience
- Skills
- Portfolio
- Certificates
- Verification
- Location
- Contact options

### Verification

Specialists can request verification.

The system should support different verification states:

- Not verified
- Verification pending
- Verified
- Rejected
- Verification expired or revoked

---

# Admin Panel

The Admin Panel is a core part of Takhassosyab.

It must be designed from the beginning rather than added later.

## Admin Dashboard

The dashboard can provide:

- Total users
- Total specialists
- Pending verification requests
- Reports
- Blocked users
- Recent activity
- System statistics

## User Management

Administrators can:

- Search users
- View user details
- Block users
- Unblock users
- Suspend users
- Restore accounts
- View account status

## Specialist Management

Administrators can:

- Search specialists
- View specialist profiles
- Edit appropriate information
- Review verification
- Manage specialist status

## Content Moderation

Administrators can:

- Review reported content
- Remove inappropriate content
- Review reports
- Take moderation actions

## Category & Location Management

Administrators can manage:

- Professional categories
- Skills
- Provinces
- Cities
- Other discovery-related data

## Admin Roles

The platform should support role-based admin permissions.

Initial admin roles may include:

- Super Admin
- User Admin
- Verification Admin
- Content Admin
- Support Admin

Administrators should only have the permissions required for their responsibilities.

---

# Security Principles

Security is a fundamental part of the MVP.

The system should include:

- Secure password hashing
- Authentication
- Authorization
- Role-based access control
- Input validation
- Rate limiting
- Secure file handling
- Protected admin routes
- Audit logging
- Privacy-aware data handling

Sensitive documents must not be publicly accessible by default.

Important administrative actions should be recorded.

---

# Audit Log

Administrative actions should record:

- Who performed the action
- What action was performed
- Which user or resource was affected
- When it happened
- Reason when required

Example:

**Admin A blocked User B at 2026-09-22 12:00 because of a confirmed policy violation.**

---

# Main Navigation

## Public

- Home
- Discover Specialists
- Categories
- Specialist Profile
- Login
- Register

## Registered User

- Home
- Discover
- Saved Specialists
- Messages
- Notifications
- Profile
- Settings

## Specialist

- Dashboard
- Professional Profile
- Portfolio
- Certificates
- Verification
- Messages
- Notifications
- Settings

## Administrator

- Dashboard
- Users
- Specialists
- Verification
- Content
- Reports
- Categories
- Locations
- Administrators
- Audit Logs
- Settings

---

# Future Features

The following features are planned for later versions:

- Professional video feed
- Professional posts
- Advanced messaging
- Reviews and ratings
- Organizations
- AI-powered specialist matching
- Mobile applications
- Service marketplace
- Payments
- Advanced analytics
- Recommendation system
- Multi-country expansion
- Advanced search
- Professional communities

---

# MVP Development Principle

The MVP should be small enough to build and test, but strong enough to become the foundation of the full Takhassosyab platform.

The architecture must allow future expansion without requiring a complete rewrite.

**Takhassosyab starts as an MVP, but it is designed for long-term growth.**
