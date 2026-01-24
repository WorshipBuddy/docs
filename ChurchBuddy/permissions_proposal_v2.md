# ChurchBuddy Section-Specific Permissions Proposal v2

## Overview

This proposal provides **section-specific permission structures** for each tab and sub-tab in ChurchBuddy. Rather than forcing a one-size-fits-all permission model, each section has permission levels that make sense for its specific functionality.

## Permission Model Basics

Each section can have its own set of permission levels. Common levels include:
- **No Access** - Section/tab is hidden and inaccessible
- **Viewer** - Read-only access
- **Editor** - Can create/edit (no delete or settings)
- **Admin** - Full access including delete and settings
- **Custom levels** - Some sections may have specialized permission levels

---

## 1. Dashboard Tab (`main-org`)

**Description:** Overview dashboard with customizable widgets showing services, events, schedules, and volunteer opportunities.

**Recommended Permission Levels:**
- **No Access** - Tab hidden from navigation
- **Viewer** - Can view dashboard widgets (read-only)
- **Editor** - Can customize dashboard layout, add/remove widgets

**Rationale:** Dashboard is primarily informational and customizable. No need for Admin level since there's nothing to delete or manage beyond layout.

---

## 2. Calendar Tab (`org-calendar`)

### 2.1 Calendar Sub-section (FullCalendar View)

**Description:** Visual calendar view showing services, events, and room bookings.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view calendar (visibility of items depends on other section permissions)

**Rationale:** Calendar view is read-only. Editing happens through Services/Events/Rooms sections.

---

### 2.2 Services Sub-section

**Description:** Manage services, schedule teams/people to services, view service details.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view services and schedules (read-only)
- **Scheduler** - Can schedule people to existing services, cannot create/edit/delete services
- **Editor** - Can create/edit services, schedule people, cannot delete services
- **Admin** - Full access: create, edit, delete services; manage all settings

**Rationale:** Scheduling is a common task that needs its own permission level. Separating scheduling from service management provides better granularity.

---

### 2.3 Events Sub-section

**Description:** Create and manage events, view event list.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view events (read-only)
- **Editor** - Can create/edit events, manage registration forms, cannot delete events
- **Admin** - Full access: create, edit, delete events; manage all event settings

**Rationale:** Events are important but deletion should be restricted. Editor can manage event content and registration without deletion rights.

---

### 2.4 Rooms Sub-section

**Description:** Manage rooms and room bookings, handle conflicts.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view rooms and bookings calendar (read-only)
- **Booker** - Can create/edit room bookings, cannot create/delete rooms or manage settings
- **Editor** - Can create/edit rooms and bookings, cannot delete rooms or manage settings
- **Admin** - Full access: create, edit, delete rooms; manage bookings; resolve conflicts; manage settings

**Rationale:** Room booking is a frequent task that needs its own permission level. Separating booking from room management allows delegation.

---

### 2.5 Resources Sub-section

**Description:** Manage resources/equipment, check out/in, maintenance records.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view resources and status (read-only)
- **Checkout** - Can check out/check in resources; add maintenance records; cannot create/delete resources
- **Editor** - Can create/edit resources; checkout/checkin; cannot delete resources
- **Admin** - Full access: create, edit, delete resources; manage all settings

**Rationale:** Resource checkout is a common operational task that should be separate from resource management.

---

## 3. Teams Tab (`org-teams`)

**Description:** Manage teams, positions, team structure.

**Recommended Permission Levels:**
- **No Access** - Tab hidden
- **Viewer** - Can view teams, positions, members (read-only)
- **Editor** - Can edit existing teams (positions, descriptions), cannot create/delete teams
- **Admin** - Full access: create, edit, delete teams; manage all team settings

**Rationale:** Team structure is important. Editor can modify existing teams but creation/deletion should be restricted.

---

## 4. People Tab (`org-people`)

### 4.1 People Dashboard Sub-section

**Description:** Customizable dashboard with widgets about people.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view dashboard widgets (read-only)
- **Editor** - Can customize dashboard layout and widgets

**Rationale:** Dashboard is for viewing and customization only.

---

### 4.2 People Sub-section

**Description:** Manage people, profiles, assign positions, manage permissions.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view people list and profiles (read-only)
- **Editor** - Can add/edit people and profiles; assign positions; cannot delete people or manage permissions
- **Admin** - Full access: add/edit/delete people; manage permissions; assign roles

**Rationale:** People management is sensitive. Permission management should be Admin-only.

---

### 4.3 Groups Sub-section

**Description:** Manage groups (manual and automatic), group members, group rules.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view groups and members (read-only)
- **Editor** - Can edit existing groups (add/remove members for manual groups); cannot create/delete groups or manage rules
- **Admin** - Full access: create/edit/delete groups; manage rules; manage all group settings

**Rationale:** Group rules and creation should be restricted. Editor can manage membership of existing groups.

---

### 4.4 Workflows Sub-section

**Description:** Create and manage automated workflows, workflow steps, conditions.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view workflows and logs (read-only)
- **Editor** - Can edit existing workflows (steps, conditions); trigger workflows; cannot create/delete workflows
- **Admin** - Full access: create/edit/delete workflows; manage all workflow settings

**Rationale:** Workflows are powerful automation tools. Creation/deletion should be Admin-only.

---

### 4.5 Forms Sub-section

**Description:** Create and manage forms, form questions, view responses.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view forms and responses (read-only)
- **Editor** - Can edit existing forms (questions, settings); view responses; cannot create/delete forms or export
- **Admin** - Full access: create/edit/delete forms; manage questions; export responses

**Rationale:** Form creation and data export should be restricted. Editor can modify existing forms.

---

### 4.6 Check-in Sub-section (Settings)

**Description:** Manage check-in stations, configure check-in settings.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view check-in stations and settings (read-only)
- **Editor** - Can edit existing check-in stations; cannot create/delete stations or manage settings
- **Admin** - Full access: create/edit/delete stations; manage all check-in settings

**Rationale:** Check-in configuration is operational. Editor can modify stations but settings should be Admin-only.

---

## 5. Giving Tab (`org-giving`)

### 5.1 Giving Dashboard Sub-section

**Description:** View giving statistics, live feed, charts.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view dashboard (read-only)
- **Financial Viewer** - Can view all financial data including sensitive information (same as Viewer, but indicates higher trust level)

**Rationale:** Dashboard is view-only. Financial Viewer level can be used for accounting purposes where users need access to all financial data but shouldn't manage settings.

---

### 5.2 Donors Sub-section

**Description:** View donor list, search donors, export donor data.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view donor list and details (read-only, no export)
- **Financial Viewer** - Can view and search donors (read-only, no export)
- **Admin** - Full access: view, search, export donor data

**Rationale:** Donor data export is sensitive and should be Admin-only. Viewer levels don't allow export.

---

### 5.3 In-Kind Donations Sub-section

**Description:** Record and manage in-kind donations.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view in-kind donations (read-only)
- **Editor** - Can create/edit in-kind donations; cannot delete
- **Admin** - Full access: create/edit/delete in-kind donations

**Rationale:** In-kind donations are less sensitive than financial donations. Editor can record them.

---

### 5.4 Statements Sub-section

**Description:** Generate and email donor statements.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view statement history (read-only)
- **Generator** - Can generate statements and view them; cannot email statements
- **Admin** - Full access: generate, email, manage all statement settings

**Rationale:** Email functionality should be restricted. Generator can create statements but emailing requires Admin.

---

### 5.5 Cash/Check Donations Sub-section

**Description:** Record cash and check donations.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view physical donations (read-only)
- **Editor** - Can record and edit physical donations; cannot delete
- **Admin** - Full access: record, edit, delete physical donations

**Rationale:** Recording physical donations is an operational task. Editor can record but deletion requires Admin.

---

### 5.6 Giving Manage Sub-section

**Description:** Configure giving settings, funds, Stripe integration, email templates.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view giving settings (read-only)
- **Admin** - Full access: manage all giving settings, funds, integration, templates

**Rationale:** Financial settings are sensitive. Only Admin should have access (no Editor level).

---

## 6. Organization Settings Tab (`org-settings`)

### 6.1 Organization Details Sub-section

**Description:** Edit organization name, address, contact info, basic settings.

**Recommended Permission Levels:**
- **No Access** - Tab should be hidden for non-org-admins by default
- **Viewer** - Can view organization details (read-only)
- **Admin** - Full access: edit all organization details and settings

**Rationale:** Organization details are foundational. Only Admin should edit (no Editor level).

---

### 6.2 Announcements Sub-section

**Description:** Create and manage organization announcements.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view announcements (read-only)
- **Editor** - Can create/edit announcements; cannot delete
- **Admin** - Full access: create/edit/delete announcements; manage settings

**Rationale:** Announcements are communication tools. Editor can create/edit but deletion should be restricted.

---

### 6.3 Background Checks Sub-section

**Description:** Configure background check integration, view status.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view background check status (read-only)
- **Admin** - Full access: configure integration, manage all settings

**Rationale:** Background checks are sensitive. Only Admin should configure (no Editor level).

---

### 6.4 Giving Settings Sub-section (within Settings)

**Description:** Configure giving integration settings.

**Recommended Permission Levels:**
- **No Access** - Sub-tab hidden
- **Viewer** - Can view giving settings (read-only)
- **Admin** - Full access: manage all giving settings

**Rationale:** Financial settings are sensitive. Only Admin should configure (no Editor level).

---

## 7. WorshipBuddy Tab (`org-worshipbuddy`)

**Description:** Configure WorshipBuddy integration, manage songbook access.

**Recommended Permission Levels:**
- **No Access** - Tab hidden
- **Viewer** - Can view WorshipBuddy integration status and access songbook (if configured)
- **Admin** - Full access: configure integration, manage access

**Rationale:** Integration management should be Admin-only. Viewer can use the integration if configured.

---

## 8. Event Detail Page (`org-event-detail`)

This page appears when viewing/editing a specific event.

### 8.1 Event Details Tab

**Description:** Edit event name, dates, description, location, settings.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view event details (read-only)
- **Editor** - Can edit event details; cannot delete event or change critical settings (like publish status)
- **Admin** - Full access: edit all details, delete event, manage all settings

**Rationale:** Event deletion and publishing should be restricted. Editor can modify event content.

---

### 8.2 Event Registration Tab

**Description:** Configure registration form, questions, registration dates.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view registration form configuration (read-only)
- **Editor** - Can edit registration form and questions; cannot change registration dates or settings
- **Admin** - Full access: manage all registration settings including dates

**Rationale:** Registration dates are critical. Editor can modify form content but not timing.

---

### 8.3 Registration Responses Tab

**Description:** View registration submissions, manage registrants, export data.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view registrations (read-only)
- **Editor** - Can view and manage registrant assignments (transportation, housing, meals); cannot export or delete registrations
- **Admin** - Full access: view, manage, export, delete registrations

**Rationale:** Data export and deletion should be restricted. Editor can manage operational assignments.

---

## 9. Event Dashboard (`event-dashboard`)

Operational dashboard for managing event logistics. Tabs appear based on enabled services.

### 9.1 Registration/Check-in Tab

**Description:** Check in/out registrants, manage stations, view logs.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view check-in logs (read-only)
- **Check-in Operator** - Can check in/out registrants; cannot manage stations or settings
- **Admin** - Full access: check in/out; manage stations; view all logs

**Rationale:** Check-in is an operational task. Operators need to check people in but don't need to manage stations.

---

### 9.2 Transportation Tab (if enabled)

**Description:** Manage vehicles, drivers, routes, assignments.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view transportation data (read-only)
- **Route Manager** - Can create/edit routes and assignments; cannot manage vehicles/drivers or settings
- **Editor** - Can create/edit routes, vehicles, drivers, assignments; cannot delete or manage settings
- **Admin** - Full access: manage vehicles, drivers, routes, assignments, settings

**Rationale:** Route management is operational. Route Manager can handle day-to-day route operations.

---

### 9.3 Housing Tab (if enabled)

**Description:** Manage housing locations, assignments.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view housing locations and assignments (read-only)
- **Housing Coordinator** - Can create/edit housing assignments; cannot create/delete locations or manage settings
- **Admin** - Full access: manage locations, assignments, settings

**Rationale:** Housing coordination is operational. Coordinators can assign people but not manage location structure.

---

### 9.4 Meals Tab (if enabled)

**Description:** Manage meal periods, attendance, menu items.

**Recommended Permission Levels:**
- **No Access** - Cannot access this tab
- **Viewer** - Can view meal periods and attendance (read-only)
- **Attendance Tracker** - Can mark meal attendance; cannot create/edit meal periods
- **Editor** - Can create/edit meal periods and mark attendance; cannot delete or manage settings
- **Admin** - Full access: manage meal periods, attendance, menu items, settings

**Rationale:** Attendance tracking is operational. Trackers can mark attendance without managing meal periods.

---

## Permission Structure Summary

### Permission Levels Used Across Sections

The following permission levels are used throughout the system, but **not all sections have all levels**:

- **No Access** - Universal (hides section)
- **Viewer** - Universal (read-only)
- **Editor** - Used in many sections (create/edit, no delete/settings)
- **Admin** - Universal (full access)

### Section-Specific Permission Levels

Some sections have specialized permission levels that make sense for their operations:

- **Services:** Scheduler
- **Rooms:** Booker
- **Resources:** Checkout
- **Giving Dashboard:** Financial Viewer
- **Statements:** Generator
- **Event Check-in:** Check-in Operator
- **Transportation:** Route Manager
- **Housing:** Housing Coordinator
- **Meals:** Attendance Tracker

---

## Recommended Data Structure

```json
{
  "org_admin": true/false,
  "section_permissions": {
    "dashboard": "viewer|editor",
    "calendar": {
      "calendar_view": "viewer|no_access",
      "services": "viewer|scheduler|editor|admin|no_access",
      "events": "viewer|editor|admin|no_access",
      "rooms": "viewer|booker|editor|admin|no_access",
      "resources": "viewer|checkout|editor|admin|no_access"
    },
    "teams": "viewer|editor|admin|no_access",
    "people": {
      "dashboard": "viewer|editor|no_access",
      "people": "viewer|editor|admin|no_access",
      "groups": "viewer|editor|admin|no_access",
      "workflows": "viewer|editor|admin|no_access",
      "forms": "viewer|editor|admin|no_access",
      "check_in": "viewer|editor|admin|no_access"
    },
    "giving": {
      "dashboard": "viewer|financial_viewer|no_access",
      "donors": "viewer|financial_viewer|admin|no_access",
      "inkind": "viewer|editor|admin|no_access",
      "statements": "viewer|generator|admin|no_access",
      "physical": "viewer|editor|admin|no_access",
      "manage": "viewer|admin|no_access"
    },
    "settings": {
      "organization_details": "viewer|admin|no_access",
      "announcements": "viewer|editor|admin|no_access",
      "background_checks": "viewer|admin|no_access",
      "giving": "viewer|admin|no_access"
    },
    "worshipbuddy": "viewer|admin|no_access",
    "events_detail": {
      "details": "viewer|editor|admin|no_access",
      "registration": "viewer|editor|admin|no_access",
      "responses": "viewer|editor|admin|no_access"
    },
    "event_dashboard": {
      "checkin": "viewer|checkin_operator|admin|no_access",
      "transportation": "viewer|route_manager|editor|admin|no_access",
      "housing": "viewer|housing_coordinator|admin|no_access",
      "meals": "viewer|attendance_tracker|editor|admin|no_access"
    }
  },
  "team_permissions": [
    // Existing team permissions structure (unchanged)
    {
      "team_name": "Music",
      "permissions": ["admin", "scheduler", "viewer"]
    }
  ]
}
```

---

## Key Differences from Previous Proposal

1. **Section-Specific Permission Levels**: Each section has permission levels that make sense for its operations (e.g., Scheduler, Booker, Checkout, Route Manager)

2. **No One-Size-Fits-All**: Some sections only have Viewer/Admin (Settings), others have Viewer/Editor/Admin, and some have specialized operational levels

3. **Operational Permission Levels**: Sections with frequent operational tasks have specialized permission levels (Check-in Operator, Route Manager, Housing Coordinator, Attendance Tracker)

4. **Financial Permissions**: Giving sections have Financial Viewer level to distinguish financial data access from regular viewing

5. **Clear No Access Option**: Every section explicitly has "No Access" as an option

6. **Fewer Permission Levels for Sensitive Sections**: Settings sections typically only have Viewer and Admin (no Editor)

---

## Migration and Implementation Notes

1. **Default Behavior**: If section permissions are not set, use existing team permissions logic as fallback
2. **Organization Admin**: `org_admin: true` grants Admin to all sections by default, but can be overridden per section
3. **Backward Compatibility**: Existing team permissions continue to work for scheduling and team-specific operations
4. **UI Considerations**: Permission management UI should clearly show which permission levels are available for each section (not all sections have all levels)

