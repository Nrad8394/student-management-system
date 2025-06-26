# Student Management System

A comprehensive Django-based web application for managing educational institutions. This system provides role-based access control for administrators (HOD), staff, and students with features for attendance tracking, course management, student records, and communication.

## 🚀 Features

### For Administrators (HOD)
- **Dashboard**: Overview of system statistics and recent activities
- **Staff Management**: Add, edit, delete, and manage staff members
- **Student Management**: Complete student lifecycle management
- **Course Management**: Create and manage academic courses
- **Subject Management**: Add subjects and assign them to courses
- **Session Management**: Academic year/session management
- **Attendance Reports**: View and analyze attendance data
- **Leave Management**: Approve/reject leave requests from staff and students
- **Feedback System**: View feedback from students and staff
- **Notifications**: Send announcements to staff and students

### For Staff
- **Personal Dashboard**: Staff-specific information and quick actions
- **Student Attendance**: Mark and manage student attendance
- **Leave Requests**: Submit leave applications
- **Student Results**: Enter and update student examination results
- **Feedback**: Provide feedback about students and courses
- **Notifications**: Receive important announcements

### For Students
- **Personal Dashboard**: Student-specific information and academics overview
- **Attendance Tracking**: View personal attendance records
- **Results**: Check examination results and academic performance
- **Leave Requests**: Submit leave applications
- **Feedback**: Provide feedback about subjects and staff
- **Notifications**: Receive important announcements from administration

## 🛠️ Technology Stack

- **Backend**: Django 4.1.7 (Python Web Framework)
- **Database**: MySQL
- **Frontend**: HTML, CSS, JavaScript, Bootstrap 4
- **Authentication**: Django's built-in authentication with custom user model
- **UI Components**: AdminLTE theme with various plugins

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- Python 3.8 or higher
- MySQL Server
- pip (Python package installer)
- Git

## ⚡ Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/student-management-system.git
cd student-management-system
```

### 2. Create Virtual Environment
```bash
python -m venv venv
venv\Scripts\activate  # On Windows
# source venv/bin/activate  # On macOS/Linux
```

### 3. Install Dependencies
```bash
pip install -r requrements.txt
```

### 4. Database Setup
1. Create a MySQL database for the project
2. Update database settings in `school_management_system/settings.py`:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'your_database_name',
        'USER': 'your_mysql_username',
        'PASSWORD': 'your_mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 5. Run Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create Superuser
```bash
python manage.py createsuperuser
```

### 7. Start Development Server
```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` in your browser to access the application.

## 📂 Project Structure

```
student-management-system/
├── manage.py                          # Django management script
├── requrements.txt                    # Python dependencies
├── README.md                          # Project documentation
├── media/                             # User uploaded files
├── static/                            # Static files (CSS, JS, images)
├── school_management_system/          # Main project directory
│   ├── __init__.py
│   ├── settings.py                    # Django settings
│   ├── urls.py                        # Main URL configuration
│   ├── wsgi.py                        # WSGI configuration
│   └── asgi.py                        # ASGI configuration
└── student_management_app/            # Main application
    ├── migrations/                    # Database migrations
    ├── templates/                     # HTML templates
    ├── __init__.py
    ├── admin.py                       # Django admin configuration
    ├── apps.py                        # App configuration
    ├── models.py                      # Database models
    ├── views.py                       # Main views
    ├── HodViews.py                    # Administrator views
    ├── StaffViews.py                  # Staff views
    ├── StudentViews.py                # Student views
    ├── forms.py                       # Django forms
    ├── urls.py                        # App URL patterns
    ├── EmailBackEnd.py                # Email backend configuration
    ├── LoginCheckMiddleWare.py        # Custom middleware
    └── tests.py                       # Unit tests
```

## 🗄️ Database Models

The application includes the following main models:

- **CustomUser**: Extended Django user model with role-based access
- **AdminHOD**: Administrator profile model
- **Staffs**: Staff member profiles
- **Students**: Student profiles
- **Courses**: Academic courses
- **Subjects**: Course subjects
- **SessionYearModel**: Academic sessions/years
- **Attendance & AttendanceReport**: Attendance tracking
- **LeaveReportStudent & LeaveReportStaff**: Leave management
- **FeedBackStudent & FeedBackStaffs**: Feedback system
- **NotificationStudent & NotificationStaffs**: Notification system
- **StudentResult**: Student examination results

## 🔐 User Roles & Permissions

### HOD (Administrator)
- Full system access
- User management (staff and students)
- Academic management (courses, subjects, sessions)
- Reports and analytics
- System configuration

### Staff
- Student attendance management
- Result entry and updates
- Leave request submission
- Feedback provision
- View assigned subjects and students

### Student
- View personal academic information
- Check attendance and results
- Submit leave requests
- Provide feedback
- Receive notifications

## 🚀 Deployment

### For Production Deployment:

1. **Environment Variables**: Set up environment variables for sensitive data
2. **Database**: Configure production database settings
3. **Static Files**: Collect static files using `python manage.py collectstatic`
4. **Security**: Update `DEBUG = False` and configure `ALLOWED_HOSTS`
5. **Web Server**: Deploy using Gunicorn/uWSGI with Nginx

### Environment Variables to Set:
```bash
DJANGO_SECRET_KEY=your-secret-key
DATABASE_NAME=your-db-name
DATABASE_USER=your-db-user
DATABASE_PASSWORD=your-db-password
DATABASE_HOST=your-db-host
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Known Issues

- Some UI elements may need responsive design improvements
- Email functionality requires SMTP configuration
- File upload validation needs enhancement

## 🔧 Troubleshooting

### Common Issues:

1. **Database Connection Error**
   - Verify MySQL server is running
   - Check database credentials in settings.py
   - Ensure database exists

2. **Migration Errors**
   - Delete migration files (except `__init__.py`)
   - Run `python manage.py makemigrations` and `python manage.py migrate`

3. **Static Files Not Loading**
   - Run `python manage.py collectstatic`
   - Check `STATIC_URL` and `STATIC_ROOT` settings

## 📞 Support

For support and questions:
- Create an issue in the GitHub repository
- Email: [your-email@example.com]

## 🏆 Acknowledgments

- Django Framework
- Bootstrap UI Framework
- AdminLTE Theme
- All contributors and testers

---

**Note**: This is a learning/demonstration project. For production use, additional security measures and testing are recommended.
