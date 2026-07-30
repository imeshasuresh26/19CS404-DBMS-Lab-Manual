# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="1516" height="737" alt="Screenshot 2026-07-27 001156" src="https://github.com/user-attachments/assets/0592b801-ef8b-4200-b4d7-3236e70df4b1" />


### Entities and Attributes


| Entity | Attributes (PK, FK) | Notes |
|--------|----------------------|-------|
| Members | MemberID (PK), MemberName, MembershipType, StartDate, Phone | Stores member information. |
| Programs | ProgramID (PK), ProgramName, Duration, Schedule | Stores fitness program details. |
| Trainers | TrainerID (PK), TrainerName, Specialization, Phone | Stores trainer information. |
| Member_Program | MemberID (FK), ProgramID (FK), JoinDate | Connects members and programs (M:N). |
| Trainer_Program | TrainerID (FK), ProgramID (FK) | Connects trainers and programs (M:N). |
| TrainingSession | SessionID (PK), MemberID (FK), TrainerID (FK), SessionDate, SessionTime | Stores personal training sessions. |
| Attendance | AttendanceID (PK), SessionID (FK), MemberID (FK), Status | Records member attendance. |
| Payments | PaymentID (PK), MemberID (FK), Amount, PaymentDate, PaymentType | Stores payment details. |

### Relationships and Constraints


| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Member – Program | M:N | Total | A member can join multiple programs, and a program can have multiple members. |
| Trainer – Program | M:N | Total | A trainer can teach multiple programs, and a program can have multiple trainers. |
| Member – TrainingSession | 1:N | Partial | A member may book many personal training sessions. |
| Trainer – TrainingSession | 1:N | Partial | A trainer can conduct many training sessions. |
| TrainingSession – Attendance | 1:N | Total | Attendance is recorded for every training session. |
| Member – Payment | 1:N | Partial | A member can make multiple membership or session payments. |


### Assumptions

- Each member has a unique MemberID and can join multiple fitness programs.
- Each trainer can teach multiple programs and conduct multiple personal training sessions.
- Every payment is made by one member and attendance is recorded for every training session.

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="1322" height="732" alt="Screenshot 2026-07-27 085147" src="https://github.com/user-attachments/assets/a10d650d-320a-4bf8-afe5-895dbebe22d8" />


### Entities and Attributes


| Entity | Attributes (PK, FK) | Notes |
|--------|----------------------|-------|
| Members | MemberID (PK), MemberName, Address, Phone | Stores library member details. |
| Books | BookID (PK), Title, Author, Category | Stores book information. |
| Loans | LoanID (PK), MemberID (FK), BookID (FK), LoanDate, ReturnDate | Records book borrowing details. |
| Events | EventID (PK), EventName, EventDate, EventTime | Stores library event details. |
| Speakers | SpeakerID (PK), SpeakerName, Expertise, Contact | Stores speaker information. |
| Event_Speaker | EventID (FK), SpeakerID (FK) | Connects events and speakers (M:N). |
| Rooms | RoomID (PK), RoomName, Capacity, Purpose | Stores room information. |
| RoomBooking | BookingID (PK), RoomID (FK), EventID (FK), BookingDate | Records room bookings. |
| Fine | FineID (PK), LoanID (FK), Amount, PaymentStatus | Stores overdue fine information. |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Member – Loan | 1:N | Partial | A member can borrow multiple books. |
| Book – Loan | 1:N | Partial | A book can be borrowed many times over its lifetime. |
| Member – Event | M:N | Partial | Members can register for multiple events, and events can have many members. |
| Event – Speaker | M:N | Total | Every event has one or more speakers, and speakers may attend multiple events. |
| Room – Event | 1:N | Total | One room can host many events at different times. |
| Loan – Fine | 1:1 | Partial | A loan generates a fine only if the book is returned late. |

### Assumptions

- Each member can borrow multiple books, but each loan record belongs to one member and one book.
- Every event is conducted in one room and may have one or more speakers.
- Overdue fines are applied only when a borrowed book is returned after its due date.

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="1563" height="732" alt="Screenshot 2026-07-27 192457" src="https://github.com/user-attachments/assets/69490323-74b2-4646-a8bf-301bc56dd173" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|----------------------|-------|
| Customers | CustomerID (PK), CustomerName, Phone, Email | Stores customer information. |
| Reservations | ReservationID (PK), CustomerID (FK), ReservationDate, ReservationTime, Guests | Stores reservation details. |
| Tables | TableID (PK), TableNumber, Capacity, Status | Stores table details. |
| Waiters | WaiterID (PK), WaiterName, Phone, Shift | Stores waiter information. |
| Orders | OrderID (PK), ReservationID (FK), OrderDate, TotalAmount | Stores customer orders. |
| Dishes | DishID (PK), DishName, Price, CategoryID (FK) | Stores menu items. |
| Categories | CategoryID (PK), CategoryName, Description | Stores dish categories. |
| Order_Dish | OrderID (FK), DishID (FK), Quantity | Connects orders and dishes (M:N). |
| Bills | BillID (PK), ReservationID (FK), FoodCharge, ServiceCharge, TotalAmount | Stores billing information. |


### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Customer – Reservation | 1:N | Partial | A customer can make multiple reservations. |
| Reservation – Order | 1:N | Total | Every reservation can have one or more food orders. |
| Order – Dish | M:N | Total | An order contains multiple dishes, and a dish can appear in many orders. |
| Category – Dish | 1:N | Total | One category contains many dishes. |
| Waiter – Reservation | 1:N | Total | A waiter serves multiple reservations. |
| Table – Reservation | 1:N | Total | A table can be reserved multiple times on different dates and times. |
| Reservation – Bill | 1:1 | Total | Each reservation generates one bill. |

### Assumptions

- A customer can make multiple reservations, but each reservation belongs to only one customer.
- Every reservation is assigned to one table and one waiter.
- Each reservation generates one bill, and an order can contain multiple dishes.

---

done by:IMESHA S,212225040131.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
