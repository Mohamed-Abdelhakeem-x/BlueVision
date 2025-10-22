# BlueVision - Full Stack Django + React Application

A modern full-stack web application built with Django REST Framework backend and React frontend.

## 📁 Project Structure

```
BlueVision/
├── Server/                 # Django Backend
│   ├── api/               # API application
│   │   ├── models.py      # Database models
│   │   ├── views.py       # API views
│   │   ├── serializers.py # DRF serializers
│   │   └── urls.py        # API URL patterns
│   ├── Bluevision/        # Django project settings
│   │   ├── settings.py    # Project configuration
│   │   └── urls.py        # Main URL configuration
│   ├── manage.py          # Django management script
│   ├── requirements.txt   # Python dependencies
│   └── db.sqlite3         # SQLite database
├── client/                # React Frontend
├── .gitignore            # Git ignore rules
└── README.md             # This file
```

## 🚀 Features

### Backend (Django)
- ✅ Django REST Framework for API endpoints
- ✅ JWT Authentication with SimpleJWT
- ✅ CORS configuration for React integration
- ✅ User registration and authentication
- ✅ User profile management
- ✅ SQLite database (easily configurable for PostgreSQL)
- ✅ API documentation ready

### Frontend (React)
- ✅ Modern React application initialized
- 🔄 JWT token management (ready to implement)
- 🔄 API integration with Django backend (ready to implement)

## 🛠️ Quick Start

### Backend Setup

1. **Navigate to Server directory**:
   ```bash
   cd Server
   ```

2. **Create virtual environment**:
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations**:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Create superuser** (optional):
   ```bash
   python manage.py createsuperuser
   ```

6. **Start development server**:
   ```bash
   python manage.py runserver
   ```

The Django API will be available at `http://localhost:8000`

### Frontend Setup (React)

1. **Navigate to client directory**:
   ```bash
   cd client
   ```

2. **Start development server**:
   ```bash
   npm start
   ```

The React app will be available at `http://localhost:3000`

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register/` - User registration
- `POST /api/auth/login/` - User login

### User Management
- `GET /api/user/` - Get current user information (requires authentication)

### Profile Management
- `GET /api/profile/` - Get user profile (requires authentication)
- `PUT /api/profile/update/` - Update user profile (requires authentication)

### API Usage Examples

#### Register a new user:
```bash
curl -X POST http://localhost:8000/api/auth/register/ \
  -H "Content-Type: application/json" \
  -d '{
    "username": "testuser",
    "email": "test@example.com",
    "password": "testpass123",
    "password_confirm": "testpass123",
    "first_name": "Test",
    "last_name": "User"
  }'
```

#### Login:
```bash
curl -X POST http://localhost:8000/api/auth/login/ \
  -H "Content-Type: application/json" \
  -d '{
    "username": "testuser",
    "password": "testpass123"
  }'
```

#### Get user profile (with JWT token):
```bash
curl -X GET http://localhost:8000/api/profile/ \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

## 🔧 Configuration

### Django Settings
The project is configured with:
- JWT authentication
- CORS enabled for React frontend
- Pagination (20 items per page)
- Media file serving in development

### Environment Variables
Create a `.env` file in the Server directory with:
```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
```

## 🗄️ Database Models

### User Profile Model
- `user`: One-to-one relationship with Django User
- `bio`: Text field for user biography
- `location`: Char field for user location
- `birth_date`: Date field for birth date
- `avatar`: Image field for profile picture
- `created_at`: Auto-generated creation timestamp
- `updated_at`: Auto-generated update timestamp

## 🔒 Authentication

The API uses JWT (JSON Web Tokens) for authentication:
- Access tokens for API requests
- Refresh tokens for token renewal
- Automatic profile creation on user registration

## 🌐 CORS Configuration

CORS is configured to allow requests from:
- `http://localhost:3000` (React development server)
- `http://127.0.0.1:3000`

## 📦 Dependencies

### Backend Dependencies
- Django 5.2.6
- Django REST Framework
- Django CORS Headers
- SimpleJWT for authentication
- PostgreSQL adapter (psycopg2-binary)
- Python-dotenv for environment variables

### Frontend Dependencies (to be installed)
- React
- Axios for API calls
- React Router for navigation

## 🚀 Development

- Backend runs on port 8000
- Frontend runs on port 3000
- CORS is configured to allow requests from localhost:3000
- Media files are served at `/media/` in development

## 🏭 Production Deployment

For production deployment:
1. Set `DEBUG=False` in Django settings
2. Configure proper database (PostgreSQL recommended)
3. Set up static file serving
4. Configure environment variables
5. Use a production WSGI server (Gunicorn)
6. Build React app for production
7. Set up reverse proxy (Nginx)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 📞 Support

For support and questions, please open an issue in the repository.