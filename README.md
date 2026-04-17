# Campus Transportation Management System

A web-based portal designed to streamline transit tracking for university campuses. This system provides real-time tracking, route planning, and schedule management for both city buses and inner-campus utility vehicles (caddies). 

## 🚀 Features
* **Dual-Tier Transit Tracking:** Separate modules for heavy-duty city buses and internal campus caddies.
* **Driver Portal:** Authenticated access for drivers to update their live location, next destination, and current status (Waiting/Started).
* **Passenger Dashboard:**
  * **Bus Routing:** Check ETAs and statuses for buses moving between the Institute, Bhawarkua, and C21 Mall.
  * **Cady Routing:** Graph-based ETA calculations for campus caddies with custom sorting (Arrive First, Reach Destination First, Most Empty Seats).
* **Admin Controls:** Add new bus schedules directly to the database.

## 🛠 Tech Stack
* **Frontend:** HTML, CSS 
* **Backend:** PHP (Session management, routing logic)
* **Database:** MySQL (Relational schema for drivers, vehicles, locations, and schedules)

## ⚙️ Installation & Setup
1. Install a local server environment like **XAMPP** or **WAMP**.
2. Clone this repository into your server's root directory (e.g., `htdocs` for XAMPP).
3. Start the **Apache** and **MySQL** modules from your control panel.
4. Open phpMyAdmin (`http://localhost/phpmyadmin`) and create a new database named `test`.
5. Execute the required SQL queries to generate the necessary tables (see Database Schema section).
6. Access the application via your browser at `http://localhost/your-folder-name/trans.php` (or your designated homepage).

## 🗄️ Database Schema Requirements
To run this project locally, your `test` database must include the following tables:
* `citybus` (busno, time, rtime)
* `bdriver` (bdid, bdpassword)
* `bmanage` (bdid, bno, mexpectedmovetime, eexpectedmovetime)
* `binfo` (bno, currentlocation, nextlocation, status)
* `blocation` (blocname)
* `bus` (bno)
* `location` (locname)
* `cady` (cno)
* `manages` (cno, routeno, did)
* `info` (cno, currentloc, seatsavail)
* `expectedtime` (loc1, loc2, routeno, time)

## 💡 How It Works
* **Bus Module:** Uses fixed routes. ETAs are calculated using hardcoded conditionals based on the driver's manually updated status and location.
* **Cady Module:** Uses dynamic graph traversal. It calculates travel time dynamically by treating campus locations as nodes and routes as edges, using the `expectedtime` table to accumulate total journey times. Results are sorted using a custom PHP implementation based on user preferences.
