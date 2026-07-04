# Campus Event Registration Portal

A web-based portal that allows students to browse, view, and register for
campus events. Built as a Software Project Management (SPM) summer term
project.

---

## Team Members

| Name              | Enrollment No. |
|-------------------|----------------|
| Sanskar Singh     | E22CSEU0714    |
| Dhawal Bharmoria  | E23CSEU1139    |
| Dhruv Singh       | E23CSEU1085    |

---

## 1. Project Overview

The Campus Event Registration Portal is a multi-page website that lets
students discover upcoming campus events and reserve a seat online. The
project demonstrates a complete user journey — from browsing events to
receiving a booking confirmation — and is documented following standard
software project management practices.

The project was intentionally kept small in scope so that every stage of
the software lifecycle (planning, design, development, testing,
documentation) could be completed and clearly explained.

---

## 2. Objectives

- Provide a single place for students to see all upcoming campus events.
- Allow students to view event details and register online.
- Validate registration input and generate a unique booking identifier.
- Let students review their saved bookings.
- Apply the software project management process end-to-end on a small,
  fully-understood codebase.

---

## 3. Scope

### In Scope
- Browse a list of campus events
- Filter events by category
- View full details of a selected event
- Submit a registration form with client-side validation
- Generate a confirmation page with a unique booking ID
- View all previously saved bookings

### Out of Scope
- User authentication and login
- Online payment processing
- Backend server and database (data is stored in the browser)
- Administrative panel for managing events

---

## 4. User Flow

The portal implements a single, linear user journey:

```
Home  →  Events List  →  Event Detail  →  Registration Form
                                                       │
                                                       ▼
                            My Bookings  ←  Confirmation Page
```

Every page links to the next logical step, so the user is never left
without a clear path forward.

---

## 5. Technologies Used

| Technology   | Purpose                                            |
|--------------|----------------------------------------------------|
| HTML         | Structure and content of every page                |
| CSS          | Styling, layout, and responsive design             |
| JavaScript   | Interactivity, filtering, form validation, storage |
| localStorage | Persisting bookings in the browser between visits  |

No external frameworks or libraries were used. This was a deliberate
decision so that every line of code is fully understood and explainable.

---

## 6. File Structure

```
eduevents/
├── index.html            Home page
├── events.html           Browse all events with category filter
├── event.html            Details of a single event
├── register.html         Registration form with validation
├── confirmation.html     Booking confirmation page
├── my-bookings.html      List of saved bookings
├── css/
│   └── style.css         Shared stylesheet
├── js/
│   ├── data.js           Event data and storage helpers
│   └── main.js           Shared navbar and footer
├── README.md             This document
└── ER-DIAGRAM.md         Entity-Relationship diagram
```

---

## 7. Data Model

The portal uses two primary data structures:

1. **Events** — defined as a JavaScript array in `js/data.js`. This acts as
   the application's data source for the demo.
2. **Bookings** — saved in the browser's `localStorage` under the key
   `edu_events_bookings`. Each booking is a JSON object containing the
   registrant's details and a reference to the event.

The full entity-relationship diagram is available in
[`ER-DIAGRAM.md`](ER-DIAGRAM.md).

---

## 8. Software Project Management Activities

This project applied the standard SPM lifecycle:

1. **Requirement Analysis** — defined features and wrote the scope statement.
2. **Design** — decided the user flow, page list, and file structure.
3. **Work Breakdown** — split the work into page-level tasks.
4. **Task Allocation** — divided tasks between the two team members.
5. **Version Control** — used Git and GitHub for source management.
6. **Testing** — manually tested each page and the full flow.
7. **Documentation** — produced this README and the ER diagram.

---

## 9. Testing

The following test cases were executed manually:

| # | Test Case                                | Expected Result                          |
|---|------------------------------------------|------------------------------------------|
| 1 | Open the home page                       | Featured events are displayed            |
| 2 | Navigate to the events list              | All events are listed                    |
| 3 | Click a category filter                  | Only matching events are shown           |
| 4 | Open an event's detail page              | Correct event details appear             |
| 5 | Submit an empty registration form        | Validation errors appear; form is blocked |
| 6 | Enter an invalid email address           | Email field shows an error               |
| 7 | Enter a phone number with letters        | Phone field shows an error               |
| 8 | Submit a fully completed form            | Confirmation page appears with booking ID |
| 9 | Open the My Bookings page                | The saved booking appears                |
| 10| Refresh the browser                      | Bookings persist via localStorage        |

---

## 10. How to Run

1. Download or clone this repository.
2. Open `index.html` in any modern web browser (Chrome, Edge, Firefox).
3. No installation, server, or internet connection is required.

---

## 11. Future Improvements

- User login so each student sees only their own bookings
- Backend database to replace browser localStorage
- Administrative panel to add, edit, and remove events
- Email confirmation on successful registration
- Payment integration for paid events
