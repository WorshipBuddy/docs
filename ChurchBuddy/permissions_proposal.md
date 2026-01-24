# ChurchBuddy Section-Based Permissions Proposal

## Overview

ChurchBuddy has expanded significantly with many new tabs and sections. Currently, permissions are only team-based (None, Viewer, Scheduler, Admin per team). This proposal outlines a comprehensive section-based permission system where each major section/tab has its own permission levels.

## Proposed Permission Levels

For each section, users can have one of these permission levels:
- **None** - Cannot access the section at all (hidden from navigation)
- **Viewer** - Read-only access (can view but not modify)
- **Editor** - Can create and edit, but cannot delete or manage settings
- **Admin** - Full access including delete, settings management, and advanced features

## Main Tabs and Sections

### 1. Dashboard Tab (`main-org`)

**Current State:** Overview dashboard with widgets showing upcoming services, events, schedules, and volunteer opportunities.

**Recommended Permissions:**
- **None** - Tab hidden
- **Viewer** - Can view dashboard widgets (read-only)
- **Editor** - Can customize dashboard layout and add/remove widgets (no admin features)
- **Admin** - Full access (same as Editor currently, as Dashboard is primarily a view)

**Note:** Dashboard is informational, so Editor and Admin could be the same.

---

### 2. Calendar Tab (`org-calendar`)

#### 2.1 Calendar Sub-section (FullCalendar view)

**Recommended Permissions:**
- **None** - Cannot see calendar view
- **Viewer** - Can view calendar (services, events, room bookings visible based on other permissions)
- **Editor** - Can view calendar (functionality comes from Services/Events/Rooms permissions)
- **Admin** - Can view calendar (functionality comes from Services/Events/Rooms permissions)

#### 2.2 Services Sub-section

**Operations:** Create, edit, delete services; schedule teams/people; view service details

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view services and schedules (read-only)
- **Editor** - Can create/edit services, schedule people, cannot delete services
- **Admin** - Full access: create, edit, delete services; schedule; manage service settings

#### 2.3 Events Sub-section

**Operations:** Create, edit, delete events; manage event registration; view event details

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view events (read-only)
- **Editor** - Can create/edit events, manage registration forms, cannot delete events
- **Admin** - Full access: create, edit, delete events; manage all event settings

#### 2.4 Rooms Sub-section

**Operations:** Create/edit/delete rooms; create/edit/delete room bookings; manage room conflicts; view room calendar

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view rooms and bookings (read-only calendar view)
- **Editor** - Can create/edit room bookings, cannot create/delete rooms or manage room settings
- **Admin** - Full access: create/edit/delete rooms; create/edit/delete bookings; manage room settings and conflicts

#### 2.5 Resources Sub-section

**Operations:** Create/edit/delete resources; check out/check in resources; manage maintenance records; view resource status

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view resources and their status (read-only)
- **Editor** - Can check out/check in resources; add maintenance records; cannot create/delete resources
- **Admin** - Full access: create/edit/delete resources; checkout/checkin; manage all resource settings

---

### 3. Teams Tab (`org-teams`)

**Operations:** Create, edit, delete teams; manage team positions; assign team permissions; view team members

**Recommended Permissions:**
- **None** - Tab hidden
- **Viewer** - Can view teams, positions, and members (read-only)
- **Editor** - Can edit existing teams (positions, descriptions), cannot create/delete teams
- **Admin** - Full access: create, edit, delete teams; manage all team settings and permissions

---

### 4. People Tab (`org-people`)

#### 4.1 People Dashboard Sub-section

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view dashboard widgets (read-only)
- **Editor** - Can customize dashboard layout
- **Admin** - Full dashboard customization access

#### 4.2 People Sub-section

**Operations:** Add/edit/delete people; manage user profiles; assign positions; view people list

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view people list and profiles (read-only)
- **Editor** - Can add/edit people; manage profiles; assign positions; cannot delete people or manage permissions
- **Admin** - Full access: add/edit/delete people; manage permissions; assign roles

#### 4.3 Groups Sub-section

**Operations:** Create/edit/delete groups; manage group members (manual groups); manage group rules (automatic groups); view group members

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view groups and their members (read-only)
- **Editor** - Can edit existing groups (add/remove members); cannot create/delete groups or manage rules
- **Admin** - Full access: create/edit/delete groups; manage rules; manage all group settings

#### 4.4 Workflows Sub-section

**Operations:** Create/edit/delete workflows; manage workflow steps and conditions; trigger workflows; view workflow logs

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view workflows and logs (read-only)
- **Editor** - Can edit existing workflows; trigger workflows; cannot create/delete workflows
- **Admin** - Full access: create/edit/delete workflows; manage all workflow settings

#### 4.5 Forms Sub-section

**Operations:** Create/edit/delete forms; manage form questions; view form responses; export responses

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view forms and responses (read-only)
- **Editor** - Can edit existing forms; view responses; cannot create/delete forms
- **Admin** - Full access: create/edit/delete forms; manage questions; export responses

#### 4.6 Check-in Sub-section (Settings)

**Operations:** Manage check-in stations; configure check-in settings; view check-in logs

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view check-in stations and settings (read-only)
- **Editor** - Can edit check-in stations; cannot manage settings
- **Admin** - Full access: create/edit/delete stations; manage all check-in settings

---

### 5. Giving Tab (`org-giving`)

#### 5.1 Giving Dashboard Sub-section

**Operations:** View giving statistics; view giving feed; view charts

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view dashboard (read-only)
- **Editor** - Same as Viewer (dashboard is view-only)
- **Admin** - Same as Viewer (dashboard is view-only)

#### 5.2 Donors Sub-section

**Operations:** View donor list; view donor details; search donors; export donor data

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view donor list and details (read-only)
- **Editor** - Can view and search donors (read-only, no export)
- **Admin** - Full access: view, search, export donor data

#### 5.3 In-Kind Donations Sub-section

**Operations:** Create/edit/delete in-kind donations; view in-kind donations; export records

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view in-kind donations (read-only)
- **Editor** - Can create/edit in-kind donations; cannot delete
- **Admin** - Full access: create/edit/delete; export records

#### 5.4 Statements Sub-section

**Operations:** Generate donor statements; email statements; view statement history

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view statement history (read-only)
- **Editor** - Can generate and view statements; cannot email
- **Admin** - Full access: generate, email, manage all statement settings

#### 5.5 Cash/Check Donations Sub-section

**Operations:** Record cash/check donations; edit/delete physical donations; view physical donation records

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view physical donations (read-only)
- **Editor** - Can record and edit physical donations; cannot delete
- **Admin** - Full access: record, edit, delete physical donations

#### 5.6 Giving Manage Sub-section

**Operations:** Configure giving settings; manage giving funds; manage Stripe integration; manage email templates for giving

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view giving settings (read-only)
- **Editor** - Cannot access (settings are admin-only)
- **Admin** - Full access: manage all giving settings, funds, integration, templates

---

### 6. Organization Settings Tab (`org-settings`)

#### 6.1 Organization Details Sub-section

**Operations:** Edit organization name, address, contact info; manage organization settings

**Recommended Permissions:**
- **None** - Sub-tab hidden (should only be visible to Org Admins/Owners)
- **Viewer** - Can view organization details (read-only)
- **Editor** - Cannot access (this should be Admin-only)
- **Admin** - Full access: edit all organization details and settings

#### 6.2 Announcements Sub-section

**Operations:** Create/edit/delete announcements; manage announcement settings

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view announcements (read-only)
- **Editor** - Can create/edit announcements; cannot delete or manage settings
- **Admin** - Full access: create/edit/delete announcements; manage settings

#### 6.3 Background Checks Sub-section

**Operations:** Configure background check integration; view background check status; manage background check settings

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view background check status (read-only)
- **Editor** - Cannot access (sensitive, admin-only)
- **Admin** - Full access: configure integration, manage all settings

#### 6.4 Giving Settings Sub-section (within Settings)

**Operations:** Configure giving integration; manage giving settings

**Recommended Permissions:**
- **None** - Sub-tab hidden
- **Viewer** - Can view giving settings (read-only)
- **Editor** - Cannot access (settings are admin-only)
- **Admin** - Full access: manage all giving settings

---

### 7. WorshipBuddy Tab (`org-worshipbuddy`)

**Operations:** Configure WorshipBuddy integration; manage songbook access; view WorshipBuddy data

**Recommended Permissions:**
- **None** - Tab hidden
- **Viewer** - Can view WorshipBuddy integration status (read-only)
- **Editor** - Cannot access (integration management is admin-only)
- **Admin** - Full access: configure integration, manage access

---

### 8. Events Detail Page (`org-event-detail`)

This is a special page that opens when viewing an event in detail. It has multiple operational tabs.

#### 8.1 Event Details Tab

**Operations:** Edit event name, dates, description, location; manage event settings; publish/unpublish event

**Recommended Permissions:**
- **Viewer** - Can view event details (read-only)
- **Editor** - Can edit event details; cannot delete or change critical settings
- **Admin** - Full access: edit all details, delete event, manage all settings

#### 8.2 Event Registration Tab

**Operations:** Configure registration form; manage registration questions; set registration dates; manage registration settings

**Recommended Permissions:**
- **Viewer** - Can view registration form configuration (read-only)
- **Editor** - Can edit registration form and questions; cannot change registration settings
- **Admin** - Full access: manage all registration settings

#### 8.3 Registration Responses Tab

**Operations:** View registration submissions; manage registrants; export registrations; manage registrant assignments (transportation, housing, meals)

**Recommended Permissions:**
- **Viewer** - Can view registrations (read-only)
- **Editor** - Can view and manage registrant assignments; cannot export or delete registrations
- **Admin** - Full access: view, manage, export, delete registrations

---

### 9. Event Dashboard (`event-dashboard`)

This is the operational dashboard for managing event logistics. It has tabs that appear based on enabled services.

#### 9.1 Registration/Check-in Tab

**Operations:** Check in/out registrants; manage check-in stations; view check-in logs; search registrants

**Recommended Permissions:**
- **Viewer** - Can view check-in logs (read-only)
- **Editor** - Can check in/out registrants; cannot manage stations
- **Admin** - Full access: check in/out; manage stations; view all logs

#### 9.2 Transportation Tab (if enabled)

**Sub-sections:**
- **Vehicles:** Create/edit/delete vehicles; view vehicle list
- **Drivers:** Create/edit/delete drivers; assign drivers to vehicles
- **Arrival Routes:** Create/edit/delete arrival routes; assign registrants to routes
- **Departure Routes:** Create/edit/delete departure routes; assign registrants to routes

**Recommended Permissions:**
- **Viewer** - Can view transportation data (vehicles, drivers, routes, assignments) - read-only
- **Editor** - Can create/edit routes and assignments; cannot create/delete vehicles or drivers; cannot manage transportation settings
- **Admin** - Full access: manage vehicles, drivers, routes, assignments, settings

#### 9.3 Housing Tab (if enabled)

**Operations:** Create/edit/delete housing locations; assign registrants to housing; manage housing assignments; view housing capacity

**Recommended Permissions:**
- **Viewer** - Can view housing locations and assignments (read-only)
- **Editor** - Can create/edit housing assignments; cannot create/delete locations or manage housing settings
- **Admin** - Full access: manage locations, assignments, settings

#### 9.4 Meals Tab (if enabled)

**Operations:** Create/edit/delete meal periods; manage meal attendance; create menu items; view meal planning data

**Recommended Permissions:**
- **Viewer** - Can view meal periods and attendance (read-only)
- **Editor** - Can mark attendance; create/edit meal periods; cannot delete or manage meal settings
- **Admin** - Full access: manage meal periods, attendance, menu items, settings

---

## Permission Inheritance and Hierarchy

### Organization-Level vs Section-Level

- **Organization Admin (`org_admin: true`)**: Should have Admin access to all sections by default, unless explicitly overridden
- **Organization Owner**: Same as Org Admin, plus ownership transfer and deletion rights
- **Section-Specific Permissions**: Can override organization-level permissions for specific sections

### Team Permissions (Existing System)

Team permissions should continue to work for:
- Scheduling people to services (team-based)
- Viewing team-specific data
- Team management (if user is Team Admin)

Section permissions would control access to features and tabs, while team permissions control scheduling and team-specific operations.

## Recommended Permission Model Structure

```json
{
  "org_admin": true/false,
  "section_permissions": {
    "dashboard": "viewer|editor|admin",
    "calendar": {
      "calendar_view": "viewer|editor|admin",
      "services": "viewer|editor|admin",
      "events": "viewer|editor|admin",
      "rooms": "viewer|editor|admin",
      "resources": "viewer|editor|admin"
    },
    "teams": "viewer|editor|admin",
    "people": {
      "dashboard": "viewer|editor|admin",
      "people": "viewer|editor|admin",
      "groups": "viewer|editor|admin",
      "workflows": "viewer|editor|admin",
      "forms": "viewer|editor|admin",
      "check_in": "viewer|editor|admin"
    },
    "giving": {
      "dashboard": "viewer|editor|admin",
      "donors": "viewer|editor|admin",
      "inkind": "viewer|editor|admin",
      "statements": "viewer|editor|admin",
      "physical": "viewer|editor|admin",
      "manage": "viewer|editor|admin"  // Admin only recommended
    },
    "settings": {
      "organization_details": "viewer|editor|admin",  // Admin only recommended
      "announcements": "viewer|editor|admin",
      "background_checks": "viewer|editor|admin",  // Admin only recommended
      "giving": "viewer|editor|admin"  // Admin only recommended
    },
    "worshipbuddy": "viewer|editor|admin",  // Admin only recommended
    "events_detail": {
      "details": "viewer|editor|admin",
      "registration": "viewer|editor|admin",
      "responses": "viewer|editor|admin"
    },
    "event_dashboard": {
      "checkin": "viewer|editor|admin",
      "transportation": "viewer|editor|admin",
      "housing": "viewer|editor|admin",
      "meals": "viewer|editor|admin"
    }
  },
  "team_permissions": [
    // Existing team permissions structure
    {
      "team_name": "Music",
      "permissions": ["admin", "scheduler", "viewer"]
    }
  ]
}
```

## Migration Strategy

1. **Backward Compatibility**: Existing team permissions should continue to work
2. **Default Behavior**: If no section permissions are set, use existing team permissions logic
3. **Organization Admin Override**: `org_admin: true` grants Admin to all sections unless explicitly overridden
4. **Gradual Rollout**: Start with most critical sections (Giving, Settings, Events) and expand to others

## Security Considerations

- **Sensitive Sections**: Giving Manage, Settings, Background Checks should default to Admin-only
- **Financial Data**: Giving sections should have careful permission controls
- **Personal Data**: People sections should respect privacy (Viewer might not see all personal data)
- **Audit Trail**: All permission changes should be logged

## UI/UX Considerations

- Sections with "None" permission should be hidden from navigation
- Sections with "Viewer" permission should show read-only indicators
- Editor vs Admin distinction should be clear in the UI (disable delete buttons, hide settings buttons for Editors)
- Permission management UI should be intuitive and organized by section/tab

