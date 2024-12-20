# Library_Management_Syetem_API


Library Management System API Documentation
--------------------------------------------
Introduction
----------
The Library Management System API is a Django-based web application that enables the 
management of a library's data, including authors, books, and borrowing records. It provides a 
RESTful interface for performing CRUD operations on the data and is integrated with a MySQL 
database for data storage.
Features
1. Authors:
o Add, update, delete, and view author information.
2. Books:
o Add, update, delete, and view book details, including their availability.
3. Borrow Records:
o Manage borrowing and returning of books with real-time updates to availability.
4. Admin Panel:
o A graphical interface to manage the library's data.
5. API Endpoints:
o RESTful endpoints for seamless integration with external systems or frontend 
applications.


Prerequisites
-----------
1. Python: Version 3.10 or above.
2. MySQL: Installed and running.
3. Git: Installed for version control.
4. Postman: Optional, for testing API endpoints.
   
Setup Instructions
---------------
1. Clone the Repository
Clone the project repository to your local machine:
git clone <your-repository-url>
cd Library-Management-System-API
2. Create a Virtual Environment
Activate the virtual environment:
o Windows:
env\Scripts\activate
3. Install Dependencies
Install the required Python packages:
pip install -r requirements.txt
4. Configure the Database
1. Create a database in MySQL:

CREATE DATABASE library_management;
-------------------------------------
3. Update the DATABASES setting in settings.py:
4. DATABASES = {
5. 'default': {
6. 'ENGINE': 'django.db.backends.mysql',
7. 'NAME': 'library_management',
8. 'USER': '<your-mysql-username>',
9. 'PASSWORD': '<your-mysql-password>',
10. 'HOST': '127.0.0.1',
11. 'PORT': '3306',
12.}
}
5. Apply Migrations
Run the following commands to create database tables:
python manage.py makemigrations
python manage.py migrate
6. Create a Superuser
Create a superuser to access the admin panel:
python manage.py createsuperuser

Superuser Credentials
----------------------
• Username: Suresh
• Password: Suresh@#23


8. Run the Server
   ---------------
Start the Django development server:
python manage.py runserver
Access the application at http://127.0.0.1:8000/.
API Endpoints
Base URL
http://127.0.0.1:8000/api/
1. Author Endpoints
GET All Authors
• Endpoint: /authors/
• Method: GET
• Response:
• [
• {
• "id": 1,
• "name": "George Orwell",
• "bio": "Author of 1984 and Animal Farm"
• }
]
Create an Author
• Endpoint: /authors/
• Method: POST
• Request Body:
• {
• "name": "Agatha Christie",
• "bio": "Queen of Mystery Novels"
}
2. Book Endpoints
GET All Books
• Endpoint: /books/
• Method: GET
• Response:
• [
• {
• "id": 1,
• "title": "1984",
• "author": {
• "id": 1,
• "name": "George Orwell",
• "bio": "Author of 1984 and Animal Farm"
• },
• "isbn": "9780451524935",
• "available_copies": 10
• }
]
Create a Book
• Endpoint: /books/
• Method: POST
• Request Body:
• {
• "title": "Harry Potter and the Philosopher's Stone",
• "author": 1,
• "isbn": "9780747532743",
• "available_copies": 5
}
Admin Panel
Access the admin panel at:
http://127.0.0.1:8000/admin/
Log in using the superuser credentials:
• Username: admin
• Password: admin123
From the admin panel, you can:
• Add, update, or delete authors and books.
• View and manage database records.

Project Structure
-----------------
Library_Management/
├── New_Library_Management/
│ ├── __init__.py
│ ├── settings.py
│ ├── urls.py
│ ├── wsgi.py
│ ├── asgi.py
├── api/
│ ├── __init__.py
│ ├── admin.py
│ ├── apps.py
│ ├── models.py
│ ├── serializers.py
│ ├── views.py
│ ├── urls.py
│ ├── migrations/
├── manage.py
└── env/

Testing the API
---------------
Using Postman
1. Open Postman and create a new request.
2. Use the API base URL (http://127.0.0.1:8000/api/) with endpoints like /authors/ and /books/.
3. Add headers for JSON requests:
Content-Type: application/json
4. Test various endpoints:
o GET requests to fetch data.
o POST requests to add data.
Future Enhancements
1. Add user authentication with token-based access.
2. Integrate Swagger for API documentation.
3. Implement search and filtering functionality.
4. Add advanced reporting for library activity.
