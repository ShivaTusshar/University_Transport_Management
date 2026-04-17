# IIT Guwahati Transport Management System

A comprehensive, web-based portal designed to streamline and manage transportation logistics across the IIT Guwahati campus. This system connects students, vehicle drivers, and administrators to provide real-time updates and efficient routing for campus Cadys, college buses, and local city buses.

## 🚀 Key Features

* **Multi-Tier User Roles:** Distinct dashboards and access levels for Students, Cady Drivers, College Bus Drivers, and Transport Managers.
* **Smart Cady Routing:** An advanced sorting algorithm that allows users to find campus vehicles based on "Arrive Here First", "Reach Destination First", or "Most Empty Seats".
* **Real-Time Fleet Tracking:** Drivers can update their current location, next destination, and available seat counts, which instantly reflects on the student dashboard.
* **Timetable Management:** Administrative controls to easily Create, Read, Update, and Delete (CRUD) schedules for local city buses.
* **Emergency Services Directory:** Quick access to vital university services (Ambulance, Fire Station, Shifting) with direct driver contact details.
* **Secure Authentication:** User passwords are encrypted using PHP's native BCRYPT hashing algorithms.

## 🛠️ Technology Stack

* **Frontend:** HTML5, CSS3 
* **Backend:** PHP 7+ 
* **Database:** MySQL
* **Environment:** XAMPP / WAMP Server

## ⚙️ Local Setup & Installation

To run this project locally, follow these steps:

1. **Install a Local Server:** Download and install [XAMPP](https://www.apachefriends.org/index.html).
2. **Set Up the Directory:** * Navigate to your XAMPP installation folder (usually `C:\xampp\htdocs\`).
   * Create a new folder named `transport`.
   * Clone or extract the project files into this `transport` folder.
3. **Configure the Database:**
   * Open the XAMPP Control Panel and start **Apache** and **MySQL**.
   * Open your web browser and go to `http://localhost/phpmyadmin`.
   * Create a new database named `test`.
   * Click the **Import** tab, upload the `test.sql` file provided in this repository, and click **Go** to generate the tables and mock data.
4. **Launch the Application:**
   * Open your browser and navigate to `http://localhost/transport/login1.php` to access the portal.

## 🔑 Default Testing Credentials

The system utilizes predefined email addresses to authenticate staff roles. You can use the following credentials to test the different interfaces (default passwords for drivers are set to their respective names + birth year formats in the database, but can be bypassed if you check the SQL file directly. For testing the existing hashes, use these):

* **Manager Dashboard:** * Email: `manager1000@gmail.com`
  * *(Note: You may need to create a test user and update the hash in the DB, or refer to the SQL dump for the exact password format).*
* **Cady Driver Dashboard:** * Email: `ram1001@gmail.com` (Driver ID: 1001)
  * Email: `shyam1002@gmail.com` (Driver ID: 1002)
* **Bus Driver Dashboard:** * Email: `bdriver2001@gmail.com` (Driver ID: 2001)

## 📁 Core Directory Structure

* `/login.php` & `/login1.php` - Central authentication and role-based routing.
* `/sp.php` & `/regester1.php` - Secure user registration logic.
* `/trans.php` - Primary student/user dashboard.
* `/managerhome.php` - Administrative control center.
* `/cadybackend.php` - Contains the routing and sorting algorithms for campus vehicles.
* `/test.sql` - The complete database schema and mock data.

---
*Developed by Tusshar, Computer Science and Engineering, IIT Guwahati.*
