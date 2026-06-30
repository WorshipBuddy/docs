# ChurchBuddy Simplified Permissions Proposal

Based on your vision, here's what the permissions structure looks like:

## Dashboard
- **Visible to:** Everyone (all users can see the Dashboard tab)

---

## Giving Tab (`org-giving`)

**Permission Levels:**
- **No Access** - Tab is hidden, user cannot see or access Giving at all
- **Book Keeper** - Can see all sub-tabs EXCEPT "Manage" sub-tab
  - Can access: Dashboard, Donors, In-Kind, Statements, Cash/Check
  - Cannot access: Manage (settings)
- **Admin** - Can see ALL sub-tabs including "Manage"
  - Full access to all giving functionality and settings

---

## Teams Tab (`org-teams`)

**Keep Original Permissions:**

**Visibility:** 
- Visible to: **Owners, Org Admins, Team Admins, and Schedulers**

**Permission Model:**
- Uses **team-based permissions** (per team, not per section)
- Users have `team_permissions` array with entries like:
  ```json
  {
    "team_name": "Music",
    "permissions": ["Admin", "Scheduler", "Viewer"]
  }
  ```

**Permission Levels (per team):**
- **Admin (Team Admin)** - Can edit team details (name, description, positions), assign people to positions, view/edit availability for team members, schedule people for their teams
- **Scheduler** - Can assign people to positions for existing services, view team availability, see services where their team is assigned
- **Viewer** - Read-only access to specific teams
- **Member** - Default, no special team permissions

**Key Points:**
- Permissions are **team-specific** (user can be Admin for "Music" team but Viewer for "Usher" team)
- Team permissions control which teams a user can see/manage/schedule
- Team permissions are separate from section access

---

## People Tab (`org-people`)

**Keep Original Permissions:**

**Visibility:**
- Visible to: **Owners, Org Admins, and Team Admins** (users with "Admin" in any team_permissions)

**Permission Model:**
- Uses **organization-level** and **team-level** permissions
- Team Admins can access People page but can only manage people in their assigned teams
- Org Admins and Owners can manage all people

**Team Admin Access:**
- Can view/manage people who are in teams they have Admin permissions for
- Cannot add/remove users from organization
- Cannot manage people outside their teams

**Org Admin/Owner Access:**
- Can manage all people in organization
- Can add/remove users
- Can assign permissions

---

## Calendar Tab (`org-calendar`)

**Keep Original Permissions:**

**Visibility:**
- Visible to: **Everyone** (all users can see Calendar tab)

**Permission Model:**
- Uses **team-based permissions** for scheduling and service management
- Calendar view is visible to all, but editing/scheduling is controlled by team permissions

**Sub-sections (Services, Events, Rooms, Resources):**
- **Services:** Team permissions (Scheduler/Admin) control which teams users can schedule for
- **Events:** Team permissions affect event visibility and management
- **Rooms & Resources:** Currently org-level (likely need org admin or full access)

**Team Permission Behavior:**
- Users with **Scheduler** team permissions can schedule people for their teams on existing services
- Users with **Admin** team permissions can edit services and schedule for their teams
- Users with **Viewer** team permissions can view services where their teams are scheduled (read-only)

---

## Organization Settings Tab (`org-settings`)

**Keep Original Permissions:**

**Visibility:**
- Visible to: **Owners and Organization Admins ONLY**

**Permission Model:**
- **Org-level only** - No team permissions affect this
- Only users with `org_admin: true` or users who are the organization owner can access

**Access Control:**
- Settings tab is completely hidden from users who are not Owner or Org Admin
- No team-based permissions apply to Settings

---

## WorshipBuddy Tab (`org-worshipbuddy`)

**Leave as is:**

**Current Access Control:**
- Owners and Org Admins: Always have access
- Other users: Access controlled by `worshipbuddy_permissions` settings
  - Can specify allowed teams or allowed users
  - If user is in an allowed team or is in the allowed users list, they can access
  - If no teams/users specified, only Owners/Org Admins can access

---

## Summary of Changes vs Current System

### New Permissions Structure:
1. **Dashboard** - No change (already visible to everyone)
2. **Giving** - NEW section-based permissions (No Access, Book Keeper, Admin)
3. **Teams** - Keep existing team-based permissions (no change)
4. **People** - Keep existing org-level + team-level permissions (no change)
5. **Calendar** - Keep existing team-based permissions (no change)
6. **Organization Settings** - Keep existing org-level only (no change)
7. **WorshipBuddy** - Keep existing access control (no change)

### Key Insight:
- **Giving** is the only section getting NEW section-based permissions
- All other sections continue using the existing permission model:
  - **Team-based permissions** (Teams, Calendar)
  - **Org-level permissions** (People, Settings)
  - **Custom access control** (WorshipBuddy)

