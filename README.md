# Gym Management System

A Business Requirements Analysis project for a **Gym Management System (GMS)** developed as part of the **SWR302** course at FPT University.

The project focuses on analyzing and documenting the business requirements, workflows, system actors, functional requirements, business rules, screen specifications, integrations, and acceptance criteria for a gym management platform.

> This repository focuses primarily on business analysis and system requirements documentation rather than a production-ready implementation.

---
## Project Members

Bui Dinh Long - leader
Nguyen Sy Minh Man
Tran Dang Khoa


## Project Overview

The Gym Management System is designed to centralize gym operations involving:

- Customer account management
- Membership packages
- Membership registration and activation
- Membership QR access
- Personal Trainer account approval
- PT service packages
- PT booking requests
- Training schedules
- Training session records
- System notifications
- SMS notifications
- Gym operational reports
- Excel report export

The system is designed around three main user roles:

- **Customer**
- **Personal Trainer (PT)**
- **Gym Owner**

It also interacts with two external services:

- **QR Service**
- **SMS Service**

---

## Business Objectives

The main objectives of the system are to:

1. Centralize Customer, PT, membership, booking, schedule, and visit information.
2. Support membership registration and activation at the gym counter.
3. Generate a stable QR code for each active membership.
4. Support QR-based gym check-in and check-out.
5. Allow the Gym Owner to review PT registration requests.
6. Allow PTs to manage packages, bookings, schedules, and training sessions.
7. Allow Customers to view memberships, PT profiles, bookings, schedules, and notifications.
8. Deliver notifications through both the application and SMS.
9. Provide operational reports with Excel export support.

---

## System Actors

### Customer

Customers can:

- Register and log in
- View and update their profile
- View membership information
- View their membership QR code
- Browse available Personal Trainers
- Submit PT package booking requests
- View training schedules
- View notifications

### Personal Trainer

Personal Trainers can:

- Register a PT account request
- Maintain their profile
- Manage PT packages
- Review booking requests
- Confirm or reject Customer bookings
- Create training schedules
- Record training session results
- View assigned Customers

A PT account must be approved by the Gym Owner before PT functions become available.

### Gym Owner

The Gym Owner is the main internal operational actor.

The Gym Owner can:

- Manage membership packages
- Register Customer memberships at the gym counter
- Activate memberships
- Review PT account requests
- Manage general notifications
- View operational dashboards
- Generate reports
- Export reports to Excel

---

## Core Business Features

### Account Management

- Customer account registration
- PT account registration
- Role-based login
- Profile management
- PT approval workflow

### Membership Management

- Membership package administration
- Counter-based membership registration
- Membership validity calculation
- Membership activation
- Stable membership QR generation
- Membership status tracking

Membership payments are performed outside the system.

### PT Management

- PT registration and approval
- PT package creation and management
- Customer PT package booking
- PT booking approval or rejection
- Customer–PT assignment

### Training Management

- Training schedule creation
- Customer and PT schedule viewing
- Training session recording
- Completed session protection

Completed training sessions are treated as immutable records.

### QR Check-in / Check-out

Each active membership is associated with a stable QR code.

Basic workflow:

```text
Customer presents QR
        ↓
QR Service reads membership code
        ↓
QR Service determines CHECK_IN / CHECK_OUT
        ↓
QR Service sends visit event to GMS
        ↓
GMS validates and stores visit
        ↓
Visit becomes Open / Closed
