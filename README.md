# Bus-agency
Name: Kwa Maxwill
Matricule: FE25A106
Role: Analyst lead 
GitHub username: @kwamaxwill
Email: kwamaxwillmua@gmail.com
----------------------------------------------------------------------
## Team Table
Name: Brian-Austin Shiezi Mbe Jr
Matricule: FE25A036
Role: Project management
GitHub username: brianaustin.mbe@gmail.com

# Bus Agency Booking System

Seat booking, parcel tracking and departure management system for Just Use X, a travel agency running buses from Buea Park to Douala.

## Documentation

- [Software Requirements Specification (SRS) v0.1](docs/srs.md): IEEE 830 / ISO 29148 style requirements for the Bus Agency Booking System (CEF 345, Week 4), including use case descriptions (UC-01 to UC-03).
- [Field Notes](docs/field-notes/): notes from observing a real bus agency desk, which informed the requirements.
- [Use case diagram](docs/diagrams/usecases.drawio.svg): UML use case diagram (renders on GitHub, and opens for editing in draw.io).

## Problem Summary

The agency currently faces five problems:

1. The same seat is sometimes sold twice, or more tickets are sold than the bus has seats.
2. Nearly empty departures go unnoticed until the bus is about to leave.
3. Parcels get lost, with no proof of receipt or delivery.
4. Booking for a departure never closes, so passengers are booked after the bus has left.
5. The two desks keep separate records and cannot see each other's sales.

## Key Business Rules

- No seat is sold twice.
- A departure closes booking at its departure time.
- Parcel fees are calculated by weight.

## Users

| Role | Responsibilities |
|------|------------------|
| Agent | Log in, book seats, reserve seats without payment, record payments, view unpaid reservations, register and track parcels |
| Manager | Everything an Agent can do, plus manage buses and routes, schedule trips, view the daily report, manage users |

## Project Structure
