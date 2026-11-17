# Software Requirements Specification

## Version A Structured SRS for Bus Agency Seat Booking

This document defines the requirements for a booking system used by a Buea-Douala travel agency. Replace every bracketed placeholder before approval. A placeholder states exactly where project-specific information is needed.

| Document field | Value |
| --- | --- |
| Agency name | Fako Express|
| Version | version 1.0 |
| Date | 15- 11 2026 |
| Prepared by | Kwa Maxwill Mua and Mbaku Junior Williams |
| Approval owner | Mr AGUM |

## 1 Introduction

### 1.1 Purpose

The system shall help staff sell and manage seats on scheduled Buea-Douala journeys. It shall show seat availability, keep bookings, receive or record payments, and give passengers a booking reference.

### 1.2 Scope

- Create and manage scheduled trips between Buea and Douala, including approved boarding and drop-off points.
- Let staff or passengers select an available seat and create a booking.
- Record payment status, issue a booking confirmation, and support approved booking changes or cancellations.
- Provide departure manifests and simple booking and sales reports.

### 1.3 Out of Scope

- Vehicle maintenance, driver payroll and fuel management.
- Multi-agency marketplace booking unless approved later.
- Features not confirmed by MR AGUM.

## 2 Overall Description

### 2.1 Users and Roles

| Role | Main responsibility |
| --- | --- |
| Agency Administrator | Manages users, buses, route settings, fares and reports. |
| Booking Agent | Creates, changes and cancels bookings; records approved payments. |
| Passenger | Selects a trip and seat through  web |
| Dispatcher | Views the departure manifest and checks passengers in. |

### 2.2 Operating Assumptions

- The agency supplies the approved route, timetable, fleet and fare information.
- Each bus has a defined seat layout before it can be assigned to a trip.
- A booking is for one passenger, one trip and one seat unless [PLACEHOLDER: group booking rule] is approved.
- The system currency, language and time zone are XAF, English / French, GMT +1.

## 3 Functional Requirements

### FR-01 Trip setup

An Administrator shall create a trip with route, travel date, departure time, assigned bus, fare and boarding points. The system shall reject a trip when required details are missing.

### FR-02 Seat availability

The system shall display the assigned bus seat layout and mark each seat as available, held, booked, cancelled or blocked. A seat booked for a trip shall not be offered again for that trip.

### FR-03 Booking creation

An authorised user shall create a booking by selecting a trip, boarding point, passenger details and an available seat. The system shall assign a unique booking reference.

### FR-04 Passenger details

The system shall capture the passenger fields approved by agency data policy. It shall validate required fields and show an error without creating a booking when validation fails.

### FR-05 Payment status

The system shall record each booking as unpaid, pending, paid, refunded or cancelled. It shall store the payment method and reference when those details are available.

### FR-06 Payment confirmation

When a payment is confirmed through Mobile Money or Cash, the system shall mark the related booking paid and issue a receipt or confirmation reference.

### FR-07 Booking change and cancellation

An authorised user shall change a booking or cancel it according to cancellation and refund policy. The system shall preserve the original booking record and reason for change.

### FR-08 Confirmation

After a successful booking, the system shall show the booking reference, trip details, boarding point, seat number and payment status. It shall send a confirmation through email when configured.

### FR-09 Check in

A Dispatcher shall search by booking reference, passenger name or seat number and mark a passenger checked in. The system shall show checked-in status on the manifest.

### FR-10 Manifest

Before departure, authorised staff shall view or print a manifest for one trip showing booked seats, passenger details approved for operations, boarding point, payment status and check-in status.

### FR-11 Reports

An Administrator shall view booking, payment and seat-occupancy reports for a selected date range, route or trip. Report fields are [PLACEHOLDER: approved report list].

### FR-12 User access

The system shall require sign-in for staff functions and limit each role to its approved actions.

### FR-13 Audit trail

The system shall record the user, date and action when a booking, payment status, trip or seat status is changed.

## 4 Non Functional Requirements

| ID | Requirement |
| --- | --- |
| NFR-01 Security | The system shall use secure sign-in and encrypted connections. Password, session and access rules are security policy. |
| NFR-02 Availability | The required service hours and allowed downtime are 24/7. |
| NFR-03 Performance | The system shall return seat availability and booking results within 5s under [PLACEHOLDER: expected concurrent users]. |
| NFR-04 Usability | The booking flow shall work on the devices used by agency staff and passengers: Mobile phone, PC. |
| NFR-05 Data protection | The system shall retain and protect passenger data according to applicable policy or law and retention period. |
| NFR-06 Recovery | Backups, restore testing and recovery time targets are 2hrs. |

## 5 Main Use Cases

### UC-01 Book a seat

**Actor:** Booking Agent or Passenger.

The actor selects a trip and available seat, supplies required passenger information, chooses a payment method, and receives a booking reference. The system prevents double booking.

### UC-02 Pay for a booking

**Actor:** Passenger or Booking Agent.

The actor provides the booking reference and completes the approved payment step. The system records the provider result and changes status only after valid confirmation.

### UC-03 Check in passenger

**Actor:** Dispatcher.

The dispatcher finds the booking, confirms the passenger is eligible under [PLACEHOLDER: departure rule], and marks the passenger checked in.

## Placeholder Register

| Placeholder position | Value needed |
| --- | --- |
| Cover details | Agency name, document owner, version and date. |
| Service scope | Approved departure points, destinations, stops and operating days. |
| Seat and fare rules | Bus layouts, fare list, child or luggage rules, cancellation and refund policy. |
| Payments | Accepted methods, payment provider, settlement process and confirmation rules. |
| Operations | Roles, office hours, support contacts and escalation path. |
| Technical targets | Hosting, retention, recovery, performance and privacy obligations. |
