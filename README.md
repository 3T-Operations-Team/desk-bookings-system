# System Name
Desk bookings

# Contributors
[Antonio Neves](https://github.com/antonioNeves3T)

[Mayank Yadav](https://github.com/matank78)

[Nikita Tsvetkov](https://github.com/nick-t-v)

[Sean Sexton](https://github.com/sean-sexton-gif)

# Background Context
This is a Test Driven Development (TDD) Sandbox Project created as part of the TDD training provided by [Valentina Jemuović](https://www.linkedin.com/in/valentinajemuovic) through the [Optivem Journal](https://journal.optivem.com/). The aim is to safely practice applying TDD to a legacy code project. This involves setting up an automated build pipeline and then retroactively adding in automated tests following TDD.

# Use Cases: 
1. Employee books a desk.

As an employee I must be able to book a desk for a specific date and receive an email confirming the booking.
- The Employee must be able to log in using their email address and generated password.
- After logging in, the Employee must see the current day's desk bookings.
- The Employee must be able to choose a date.
- Once the date is chosen the Employee must be able to see available desks.
- The Employee must be able to select an available desk and book it.
- Then once the booking has been confirmed the Employee must receive a confirmation email with the booking details.
2. Employee views desk booking history.

As an Employee I must be able to view a history of desks that I have booked.The Employee must be able to sign in using their email address.
- After logging in the Employee must be able to see a list of all desks they have booked and the booking details (booking date/desk).
3. Employee cancels desk booking.

As an Employee I must be able to cancel a desk booking.
- The Employee must be able to log in using their email address.
- After signing in the Employee must be able to see a list of all desks they have booked and the booking details (date/desk).
- The Employee must then be able to select current and future bookings.
- The Employee must then be able to cancel that booking ~by adding their confirmation number for that booking~.
- Then once a booking has been canceled the Employee should receive a confirmation email with the cancelled bookings details.
4. Employee views current desk availability.

As an Employee I must be able to see what desks are currently available.
- The Employee must be able to log in using their email address.
- After signing in, the Employee must see the current day's desk bookings.
- The Employee must be able to choose a date/time.
- Once the date is chosen the Employee must be able to see available desks.

# External systems
1. Email sending service - [SendGrid](https://sendgrid.com/). e2e, UAT and production environments use sendgrid test plan credentials. Host and API key are set via the following backend environment variables: 
- `SENDGRID_HOST` - default value is `api.sendgrid.com`
- `SENDGRID_KEY` - needs to be provided
2. System clock - saving timestamps (e.g. booking created time)

# System Architecture Style
Frontend + Monolithic Backend

# Architecture Diagram
![](./systemArchitecture.png)

# Tech stack
## FE: 
Vite + Vitest, React
## BE:
Spring Boot + MongoDB

# Repository Strategy
Multi Repo approach

# Branching Strategy
Feature Branching

# Deployment Model
Deployment on AWS

# Repositories
### FE:
https://github.com/3T-Operations-Team/desk-bookings-fe.git

### BE: 
https://github.com/3T-Operations-Team/desk-bookings-be.git

### System Test:
https://github.com/3T-Operations-Team/desk-bookings-system-tests.git

# Project Boards
https://github.com/orgs/3T-Operations-Team/projects/4/views/1

# Manual Testing
https://github.com/3T-Operations-Team/desk-bookings-system/blob/master/manualTestingProcedure.txt

# Pipeline Tool
Github Actions

# Docker Registry
GitHub Container Registry

# Environments
Acceptance: http://ops-desk-bookings-acceptance-fe.us-east-1.elasticbeanstalk.com/

E2E: http://ops-desk-bookings-e2e-fe.us-east-1.elasticbeanstalk.com/

UAT: http://ops-desk-bookings-uat-fe.us-east-1.elasticbeanstalk.com/

Prod: http://ops-desk-bookings-prod-fe.us-east-1.elasticbeanstalk.com/

# Pipeline Dashboard

## Component Stages

| Component          | Commit Stage         |
| ------------------ | ----------------------- |
| **Frontend**        | [![Commit Frontend Pipeline](https://github.com/3T-Operations-Team/desk-bookings-fe/actions/workflows/commit-stage.yml/badge.svg)](https://github.com/3T-Operations-Team/desk-bookings-fe/actions/workflows/commit-stage.yml) |
| **Backend**    | [![Commit Backend pipeline](https://github.com/3T-Operations-Team/desk-bookings-be/actions/workflows/commit-stage.yml/badge.svg)](https://github.com/3T-Operations-Team/desk-bookings-be/actions/workflows/commit-stage.yml) |

## System Stages

|                    |  Acceptance Stage    | UAT Stage            |  Production Stage     |
| ------------------ | -------------------- | -------------------- |-----------------------|
| **System**         | [![Acceptance Stage](https://github.com/3T-Operations-Team/desk-bookings-system-tests/actions/workflows/acceptance-stage.yml/badge.svg)](https://github.com/3T-Operations-Team/desk-bookings-system-tests/actions/workflows/acceptance-stage.yml) | [![UAT Stage](https://github.com/3T-Operations-Team/desk-bookings-system/actions/workflows/uat-stage.yml/badge.svg)](https://github.com/3T-Operations-Team/desk-bookings-system/actions/workflows/uat-stage.yml) | [![Production Stage](https://github.com/3T-Operations-Team/desk-bookings-system/actions/workflows/production-stage.yml/badge.svg)](https://github.com/3T-Operations-Team/desk-bookings-system/actions/workflows/production-stage.yml) |
