# 👥 Employee Attendance Management System

A comprehensive web-based employee attendance tracking system built with Spring Boot backend and vanilla JavaScript frontend.

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat&logo=spring&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)

## 🎯 Features

- **Employee Management**: Add, edit, delete, and view employee records
- **Attendance Tracking**: Record daily attendance with check-in/check-out times
- **Leave Management**: Handle employee leave requests and approvals
- **Department Management**: Organize employees by departments
- **Holiday Calendar**: Manage company holidays and events
- **Shift Management**: Configure and assign work shifts
- **Dashboard Analytics**: Visual overview of attendance statistics
- **User Authentication**: Secure login system for employees and administrators

## 🏗️ Architecture

```
PROJECT-PDM/
│
├── src/main/               # Backend (Spring Boot)
│   ├── java/
│   └── resources/
│
├── target/                 # Compiled backend files
│
├── js/                     # Frontend JavaScript
├── css/                    # Frontend Stylesheets
│
├── *.html                  # Frontend Pages
│   ├── Dashboard.html
│   ├── Attendance.html
│   ├── Employees.html
│   ├── Department.html
│   ├── LeaveRecords.html
│   ├── Holiday.html
│   ├── Shifts.html
│   └── UserLogin.html
│
├── data.sql                # Database initialization
├── schema.sql              # Database schema
├── pom.xml                 # Maven configuration
└── server.js               # Node.js alternative server
```

## 🚀 Quick Start

### Prerequisites

**Option 1: Spring Boot (Recommended)**
- Java JDK 11+
- Maven 3.6+
- MySQL/PostgreSQL (or H2 for development)

**Option 2: Node.js**
- Node.js 14+
- npm or yarn

**Frontend Server**
- Python 3.x

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/NguyenNhatAnh-dev/PROJECT-PDM.git
cd PROJECT-PDM
```

2. **Database Setup**
```bash
# Run the schema and data scripts
mysql -u root -p < schema.sql
mysql -u root -p < data.sql
```

3. **Configure Database Connection**

Edit `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/attendance_db
spring.datasource.username=your_username
spring.datasource.password=your_password
```

## 🎮 Running the Application

### Backend Options

**Option A: Spring Boot (Maven)**
```bash
# Development mode
mvn spring-boot:run

# Or build and run JAR
mvn clean package
java -jar target/attendance-system-0.0.1-SNAPSHOT.jar
```
Backend will run on: `http://localhost:8080`

**Option B: Node.js**
```bash
# Install dependencies
npm install

# Start server
node server.js
```
Backend will run on: `http://localhost:3000`

### Frontend

```bash
# Navigate to project root
cd PROJECT-PDM

# Start Python HTTP server
python3 -m http.server 5500
```
Frontend will be available at: `http://localhost:5500`

### Access the Application

1. Open browser and go to: `http://localhost:5500/UserLogin.html`
2. Default credentials:
   - **Admin**: `5` / `123456`
   - **Employee**: `1` / `123456`

## 📁 Project Structure

### Backend (Spring Boot)

```
src/main/java/
├── controller/        # REST API endpoints
├── model/             # Entity classes
├── repository/        # Data access layer
├── service/           # Business logic
└── config/            # Configuration classes
```

### Frontend

```
├── js/
│   ├── main.js            # Core functionality
│   ├── attendance.js      # Attendance management
│   ├── employees.js       # Employee CRUD
│   └── dashboard.js       # Dashboard analytics
│
├── css/
│   ├── style.css          # Global styles
│   └── components.css     # Component styles
│
└── *.html                 # Page templates
```

## 🔧 Configuration

### Backend Configuration

**application.properties**
```properties
# Server port
server.port=8080

# Database
spring.datasource.url=jdbc:mysql://localhost:3306/attendance_db
spring.datasource.username=root
spring.datasource.password=password

# JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# File upload
spring.servlet.multipart.max-file-size=10MB
```

### Frontend Configuration

Edit `js/config.js`:
```javascript
const API_BASE_URL = 'http://localhost:8080/api';
```

## 📡 API Endpoints

### Authentication
```
POST   /api/auth/login
POST   /api/auth/logout
GET    /api/auth/profile
```

### Employees
```
GET    /api/employees
GET    /api/employees/{id}
POST   /api/employees
PUT    /api/employees/{id}
DELETE /api/employees/{id}
```

### Attendance
```
GET    /api/attendance
POST   /api/attendance/checkin
POST   /api/attendance/checkout
GET    /api/attendance/employee/{id}
```

### Departments
```
GET    /api/departments
POST   /api/departments
PUT    /api/departments/{id}
DELETE /api/departments/{id}
```

### Leave Records
```
GET    /api/leaves
POST   /api/leaves
PUT    /api/leaves/{id}/approve
PUT    /api/leaves/{id}/reject
```

### Holidays
```
GET    /api/holidays
POST   /api/holidays
DELETE /api/holidays/{id}
```

### Shifts
```
GET    /api/shifts
POST   /api/shifts
PUT    /api/shifts/{id}
DELETE /api/shifts/{id}
```

## 🧪 Testing

```bash
# Run unit tests
mvn test

# Run integration tests
mvn verify

# Run specific test
mvn test -Dtest=EmployeeServiceTest
```

## 📊 Database Schema

### Main Tables
- `employees` - Employee information
- `attendance` - Daily attendance records
- `departments` - Department organization
- `leave_records` - Leave requests
- `holidays` - Company holidays
- `shifts` - Work shift definitions
- `users` - Authentication data

See `schema.sql` for complete database structure.

## 🛠️ Technologies Used

### Backend
- **Spring Boot 2.7+** - Application framework
- **Spring Data JPA** - Database abstraction
- **Spring Security** - Authentication & authorization
- **MySQL/PostgreSQL** - Relational database
- **Maven** - Dependency management
- **Lombok** - Reduce boilerplate code

### Frontend
- **HTML5** - Page structure
- **CSS3** - Styling and animations
- **Vanilla JavaScript** - Interactive functionality
- **Fetch API** - HTTP requests
- **LocalStorage** - Client-side data storage

### Development Tools
- **Python HTTP Server** - Development server
- **Maven** - Build automation
- **Git** - Version control

## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**NguyenNhatAnh-dev**
- GitHub: [@NguyenNhatAnh-dev](https://github.com/NguyenNhatAnh-dev)

## 🙏 Acknowledgments

- Spring Boot Documentation
- MDN Web Docs
- Stack Overflow Community

## 📧 Contact & Support

For issues, questions, or contributions:
- Open an issue on GitHub
- Email: nhatanh4works@gmail.com

---

⭐ Star this repository if you find it helpful!