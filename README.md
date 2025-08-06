# interview
interview uchun
Task 1 – Django Skills
 Purpose: Evaluate candidate’s hands-on knowledge in:
Django model design
Admin interface customization
Data import/export and filtering
Command usage
Basic data processing (formatting, filtering, messaging)
Pre requirements for all tasks 
1.1 Install django 
1.2 Create  excel file with cards which includes those columns 
card_number: (e.g. 8600 1234 5678 9012, 8600123456789012, etc.)
expire: expired / random formats like 12/24, 2024-12, 12.2024, etc.
phone: formatted/unformatted (e.g. 99 973 03 03, 973-03-03, empty, etc.)
Status enum [active, inactive, expired]
balance: between 0 and 1.2 billion UZS
Sample: 
card_number
expire
phone
status
balance
8600 4835 2559 2899
2025-07
973-03-03
expired
200.00 
8600855254356990
03.2026
(empty)
active
842,714,800.00 
8600327218840361
2026-08
99 973 03 03
active
22,300.00 
8600 3901 0981 2774
04/25
(empty)
active
8,911,200.00 
8600 0871 2045 1520
11.2026
973-03-03
expired
400.00 
8600910092834567
07/26
(empty)
expired
684,214,300.00 
8600 1234 5678 9012
12/24
99 973 03 03
inactive
5,000.00 
8600 7843 9910 1122
06.2024
(empty)
inactive
0.00 


1.3 Models & Admin
Create Django model Card with above fields


Register model in django admin


Add filters in admin panel by status, expire, phone, balance


Add readable formatting for phone & card number

1.4 Excel Import Button (Admin Panel)
Add button or section in admin to import Excel file


Clean and normalize data (phone, card formatting) before saving


Reject invalid rows with errors


1.5 Export via Management Command
Create a command to export cards:


Filter by status, card_number, or phone


Export to CSV (full or partial filtered data)



1.6 Messaging Feature (Optional Command)
Management command: send fake message to filtered cards


E.g. all cards with status='active'
Template:

Sizning kartangiz [card_number] aktiv va foydalanishga [balance] UZS mavjud!
Log messages sent (simulate message sending using telegram bot)

Maximize reusability by creating utility functions such as:
def card_mask(card_number): ...
def phone_mask(phone): ...
def format_card(raw_card): ...
def format_phone(raw_phone): ...
def prepare_message(card_number, balance, lang="UZ"): ...
def send_message(message, chat_id=12345): ...
Reusing logic will make your code cleaner, easier to test, and more maintainable.
