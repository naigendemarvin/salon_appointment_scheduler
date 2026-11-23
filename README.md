
Salon Appointment Scheduler

An interactive command-line salon appointment booking system built with Bash and PostgreSQL, developed as part of the freeCodeCamp Relational Databases Certification.

Overview

This project automates customer management and appointment scheduling through a terminal interface. Users can view available salon services, register as new customers or log in automatically via their phone number, and book appointments that persist directly in a relational PostgreSQL database.

Project Structure

• salon.sh — Executable Bash script handling the interactive CLI menu, input validation, customer lookup/registration, and appointment booking.
• salon.sql — PostgreSQL database dump containing the complete schema (customers, services, appointments) and seeded service records.

Database Schema

The salon database consists of three relational tables:

Table	Columns	Constraints
services	service_id, name	PRIMARY KEY (service_id)
customers	customer_id, phone, name	PRIMARY KEY (customer_id), UNIQUE (phone)
appointments	appointment_id, customer_id, service_id, time	PRIMARY KEY (appointment_id), FOREIGN KEYs referencing customers and services


Features

• Dynamic Service Menu: Queries the services table in real time and formats available options cleanly.
• Input Validation: Uses regular expressions to ensure numeric service selections and verifies service existence before proceeding.
• Customer Recognition: Checks if a phone number already exists in the customers table; automatically registers first-time visitors before booking.
• Persistent Storage: Records all appointments with relational foreign keys and outputs a formatted booking confirmation.

Setup & Usage

1. Clone the repositorybash
git clone https://github.com
cd salon-appointment-scheduler
Use code with caution.
2. Restore the PostgreSQL databasebash
psql -U postgres < salon.sql
Use code with caution.
(Note: Update the username flag -U to match your local PostgreSQL role, e.g., freecodecamp, and ensure the connection string inside salon.sh matches your local database user.)
3. Make the script executable and run itbash
chmod +x salon.sh
./salon.sh
Use code with caution.

Technologies Used

• Bash / Shell Scripting
• PostgreSQL (psql, pg_dump)
• Linux CLI Tools (sed, regular expressions)
