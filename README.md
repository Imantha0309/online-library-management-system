# Library Management System
<img width="1727" height="728" alt="Screenshot 2026-06-11 101941" src="https://github.com/user-attachments/assets/1c2c8b82-3491-4d9c-b65b-dbaadb08e027" />
<img width="1577" height="892" alt="Screenshot 2026-06-11 121309" src="https://github.com/user-attachments/assets/5db08042-9766-4633-b44e-eb6eab266099" />
<img width="1886" height="893" alt="Screenshot 2026-06-11 121241" src="https://github.com/user-attachments/assets/646b9ab6-934e-4dfe-b9b9-19620df7af77" />
<img width="1563" height="883" alt="Screenshot 2026-06-11 121223" src="https://github.com/user-attachments/assets/b0018699-9cff-4c1d-841a-2c2830821e57" />


A comprehensive Spring Boot web application for managing library operations including book cataloging, staff management, and user interactions.

## Features

### User Features
- **Book Browsing**: View all available books with pagination
- **Advanced Search**: Search books by title, author, or ISBN
- **Filtering**: Filter books by availability status
- **Sorting**: Sort books by various criteria (title, author, publication date)
- **Staff Directory**: Browse library staff members and their information
- **User Registration**: Create an account to access the system
- **Responsive Design**: Mobile-friendly interface

### Admin Features
- **Secure Authentication**: Admin login with Spring Security
- **Book Management**: Complete CRUD operations for books
- **Staff Management**: Complete CRUD operations for staff members
- **Dashboard**: Overview with statistics and quick access
- **Modal Forms**: User-friendly forms for adding/editing records
- **AJAX Operations**: Seamless user experience without page reloads

## Technology Stack

- **Backend**: Spring Boot 3.5.7, Spring Security 6, Spring Data JPA
- **Database**: H2 in-memory database (with H2 console at `/h2-console`)
- **Frontend**: Thymeleaf templates, custom CSS, vanilla JavaScript
- **Build Tool**: Maven
- **Java Version**: 17

## Prerequisites

- Java 17 or higher
- Maven 3.6+
- IDE (IntelliJ IDEA, Eclipse, or VS Code)

## Installation & Setup

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd online-library-management-system
   ```

2. **Build the Application**:
   ```bash
   mvn clean install
   ```

3. **Run the Application**:
   ```bash
   mvn spring-boot:run
   ```

4. **Access the Application**:
   - Open browser and navigate to `http://localhost:8080`
   - Admin login: `admin@libraryse.com` / `admin123`
   - User login: `john.doe@example.com` / `password123`

## Project Structure

```
online-library-management-system/
├── src/
│   ├── main/
│   │   ├── java/com/librarysystem/
│   │   │   ├── controller/
│   │   │   │   ├── HomeController.java
│   │   │   │   ├── BookController.java
│   │   │   │   ├── StaffController.java
│   │   │   │   ├── AdminController.java
│   │   │   │   ├── AdminBookController.java
│   │   │   │   ├── AuthController.java
│   │   │   │   └── LoginController.java
│   │   │   ├── model/
│   │   │   │   ├── Book.java
│   │   │   │   ├── Staff.java
│   │   │   │   ├── User.java
│   │   │   │   └── UserRole.java
│   │   │   ├── repository/
│   │   │   │   ├── BookRepository.java
│   │   │   │   ├── StaffRepository.java
│   │   │   │   └── UserRepository.java
│   │   │   ├── service/
│   │   │   │   ├── BookService.java
│   │   │   │   ├── StaffService.java
│   │   │   │   └── UserService.java
│   │   │   ├── config/
│   │   │   │   ├── SecurityConfig.java
│   │   │   │   └── DataInitializer.java
│   │   │   └── LibrarySystemApplication.java
│   │   └── resources/
│   │       ├── templates/
│   │       │   ├── index.html
│   │       │   ├── books.html
│   │       │   ├── book-detail.html
│   │       │   ├── staff.html
│   │       │   ├── staff-detail.html
│   │       │   ├── login.html
│   │       │   ├── auth/signup.html
│   │       │   └── admin/
│   │       │       ├── admin-dashboard.html
│   │       │       ├── admin-books.html
│   │       │       └── admin-staff.html
│   │       ├── static/css/style.css
│   │       └── application.properties
│   └── test/
├── pom.xml
└── README.md
```

## API Endpoints

### Public Endpoints
- `GET /` - Home page
- `GET /books` - Book listing with search/filter
- `GET /books/{id}` - Book details
- `GET /staff` - Staff listing
- `GET /staff/{id}` - Staff details

### Admin Endpoints (require ADMIN role)
- `GET /admin` - Admin dashboard
- `GET /admin/books` - Book management
- `POST /admin/books` - Create new book
- `PUT /admin/books/{id}` - Update book
- `DELETE /admin/books/{id}` - Delete book
- `GET /admin/staff` - Staff management
- `POST /admin/staff` - Create new staff member
- `PUT /admin/staff/{id}` - Update staff member
- `DELETE /admin/staff/{id}` - Delete staff member
- `GET /admin/stats` - Dashboard statistics

### Authentication
- `GET /login` - Login page
- `POST /login` - Process login
- `GET /auth/signup` - Registration page
- `POST /auth/signup` - Process registration
- `POST /logout` - Logout

## Configuration

### Application Properties
```properties
# Database Configuration (H2 in-memory)
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=password

# JPA Configuration
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.H2Dialect

# H2 Console
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# Server Configuration
server.port=8080
```

### Color Theme
The application uses a consistent color scheme:
- **Header**: #343131 (Dark Gray)
- **Primary Buttons**: #A04747 (Red)
- **Highlights**: #D8A25E (Gold)
- **Accent**: #EEDF7A (Light Yellow)

## Sample Data

The application includes sample data initialization on first run:
- **5 Sample Books**: Classic literature with realistic metadata
- **5 Sample Staff Members**: Various library positions
- **2 Users**: Admin and regular user accounts

## Security

- **Authentication**: Spring Security with database-backed UserDetailsService
- **Password Encryption**: BCrypt password encoding
- **Role-Based Access**: USER and ADMIN roles
- **Session Management**: Secure session handling

## Development

### Adding New Features
1. Create model classes in `model` package
2. Add repository interfaces in `repository` package
3. Implement business logic in `service` package
4. Create controllers in `controller` package
5. Add Thymeleaf templates in `templates` directory

### Database Changes
- Update model classes with new fields
- Modify repository interfaces for new queries
- Update service layer for new business logic
- Run application to apply schema changes (H2 in-memory, schema recreated on startup)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions:
- Create an issue in the repository
- Contact the development team

---

**Library Management System** - Built with Spring Boot and modern web technologies.
