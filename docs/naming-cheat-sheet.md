# Naming Cheat Sheet

Condensed version of all the naming systems for XPERTO. You can visit the detailed explaination on the subpages.

## Page naming
- Regular/customer facing pages: **kebab-case**

```text
event-details
org-admin-dashboard
main-stage
home
```

- System/non-public pages: **snake_case** and always prefix with `xperto_`

```text
xperto_manage_events
xperto_reminders
```

## Element naming

### Groups

- Structural groups: (Main containers)

```text
Header
Body
Footer
Section
```

- Regular groups: Use ``{Group type} {Group name}`` like usual.

For example:  
```text
{Group type} {Group name}
Group Testimonials
FloatingGroup Sidebar
Popup Deletion Confirmation
```

- Sub groups: Use ``[{Parent's name}] {Group type} {Group name}``.

For instance:

```text
Parent group:
FloatingGroup Nav
    
Sub groups:
[Nav] Group Menu

// "Nav" is the parent name from above
```

- RepeatingGroups: Use RepeatingGroup ``{Data type} or RG {Data type}``.

```text
RG Comment
```

### Reusable elements

Reusable elements should be named like pages, with type: ``[{Reusable type}] {ReusableElementName}``.

For example:

```text
[Drawer] UserDetails
[Dialog] Login
```

Common reusable types include:

- Container: A big component that contains a lot of elements and logics inside, similar to an **organism** in atomic design, mainly used for breaking the apps into smaller parts.
  - Drawer: Either a popup or floating group that displays data as a drawer.
  - Dialog: A popup with CTAs.
  - Subpage: For groups used in single-page behavior.
- Workflow: Invisible components that encapsulate workflows only.
- Component: Small components, like a simple like button with logics that manage the number of likes.

### Visual Elements

- Non-dynamic elements: You should keep the element type first, and then its name, like usual: ``{Element type} {Name}``.

```text
Button Submit Feedback
```

- Dynamic elements: Use ``{Element type} {Data field}`` or ``{Element type} {Operations}``.

```text
Text username
//or 
Text firstName + lastName
```

### Input Elements

Input elements should reflect the data they are changing: ``{Element type} {Data field} or {Element type} {Data type/Data field}``.

```text
Input username or Input User/username
```

### Custom states

To differentiate custom states from data fields and data types, use **snake_case** for custom states.

### Notation of state, data & clickable

- ``<S>`` or ``<State>``for elements with custom states.
- ``<D>`` or ``<Data>`` for elements with custom data sources (parent elements only, no need to mark child elements that inherit the data).
- ``<C>`` or ``<Click>`` for non-input elements that are clickable (e.g. texts, groups)

![Notation of state](/_media/notation-of-state.png)

*An example of using notations*

### Notation of order

Groups, data fields, option set fields, etc when related to ordering (e.g. steps in an onboarding process, indicated by an option set) should come with a number indicator (``no_``) before the name.

```text
1_onboardingStep
2_onboardingStep
```

## Style naming

- For non-text elements: ``{Type} {Background} [Optional] Size variant``

*Types* can be: ``Primary, Secondary, Success, Danger (or Destructive), Alert (or Notice), Neutral (or Default), Background and Surface``

*Background* can be: ``Filled or Outlined``
  
```text
Primary Outlined Large
Seconday Filled Small
```

- For text elements: ``{Type} {Size} {[Optional] Color variant} {[Optional] Weight variant}``.

```text
Heading L
Heading XL Danger 500
```

## Workflow naming & organization

- Front-end workflows: Keep as default for simple/general workflows. If workflows are more complicated:
  - Navigating/Screen transition workflows: `Page 1` -> `Page 2`.
  - Others: Purpose of the workflow, in **snake_case**. For instance: `register_user`.

**Color coding** is preferable than foldering due to the ease of view. Workflows interacting with the same object (e.g. CRUD operations of User) should be in one color. Workflows with the same purpose (e.g. triggers used for analytics) should be **in one folder**. Workflow names with `[Tag]` is also a good approach, as Bubble sorts the workflows by name.

## Database naming

For data types: `PascalCase`. In **Singular form**, example: *Post* instead of *Posts*. Do not abbreviate.

```text
Company
MemberInvitation
Message
Notification
```

For data fields: `camelCase`. In **Singular form** for primitive types. **Plural** for complex types. Do not abbreviate.

```text
image
name
noOfTickets
ticketCount
isPrivate
participants
```

For option sets: `SCREAMING_SNAKE_CASE`

```
BLUE
GREEN
RED
```

For option set fields:
- Use regular texts when the field needs to be displayed to end-users.
- Use rules like data fields for regular fields.
- Use **kebab-case** if the Display field is used for URL param.

```
BLUE - Blue <-- for display
ADMIN - Admin <-- for table or workflow
COMPLETED - complete <-- for URL params
```

## Field or Unique ID Generation

**Organizer Key**
- Format: ``xorg-{short name}``
- Max Length: ``15``

```text
xorg-piche
xorg-acme
```

**Event Key**
- Format: ``xevt-{org name}_{event name}``
- Max Length: ``15``

```text
xevt-piche_natcon
xevt-acme_annual_conference
```

**Ticket Key**
- Format: ``xevt-{org name}_{event name}-xtkt-{short name}``
- Max Length: ``10``

```text
xevt-piche_natcon-xtkt-active
xevt-piche_natcon-xtkt-inactive
xevt-piche_natcon-xtkt-student
xevt-piche_natcon-xtkt-svipengr
xevt-piche_natcon-xtkt-nonmember
xevt-piche_natcon-xtkt-earlybird
```

**Lounge/Meeting Room Key
- Format: ``xmet-{short name}``
- Max Length: ``15``
- Case: **snake_case**

```text
xmet-meeting_room_1
```