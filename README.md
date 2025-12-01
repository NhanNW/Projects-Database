Library Management System –  Using SQL Server 
 Database Design & Business Logic Implementation

This project is a  School Library Management System built using SQL Server and ASP.NET MVC .  
I am responsible for **designing the entire database**, **stored logic**, and **triggers** to ensure that all library operations follow real-world rules.

+ Users  
- Manage students, teachers, librarians  
- Includes login, role, creation date, status (they are still active or not)

+ Books & Categories
- Manage BookID, Title, Author, TotalCopies, AvailableCopies,...
- Category reference

+ Borrowing & BorrowDetails & BorrowRequest
- Borrow request  
- Borrowed books  
- Due date, return date, quantity

+ Reservations  
- Book reservations when no copies are available

+ BorrowRequests  
- Temporary request list for student borrow operations

Business Logic (Triggers I implemented)
- trg_OnlyLibrarianCanApprove (Only User with role Librarian can approve Borrowing)
- trg_BorrowDetails_InsertCheck (For logic can not borrow book with the quantity bigger than number available copies of that book)
- trg_EnsureLibrarianApproval (For logic only Librarian can approve Reservation)
- trg_OnlyLibrarianCreateFines (For logic only the librarian can issue penalty slips to those who violate the library rules (such as returning books late, etc.)
- trg_DueDateCheck (For logic due date must be bigger or equal to start date of borrow book)
- trg_TuDongTangSoLuongBanCopy (auto increase number of available copies of book when it is returned)
- trg_BorrowingStatus (auto update status in borrow details)
- trg_CheckReturnDate (For logic the return date can not be later than current date)
- trg_LimitBooksPerBorrow (For logic each BorrowID can only borrow max 5 books)
- trg_OnlyLibrarianCanCreateNotification (For logic only librarian can create notifications for users)

How to run
+ Copy the SQL file in the /Database/ folder
+ Run on SQL Server Management Studio
+ Database name: LibrarySystem
+ Open the .sln file in Visual Studio 2022
+ Restore NuGet packages
+ Update connection string inside
