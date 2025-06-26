# Personal Portfolio Website

## Overview

This is a modern, responsive personal portfolio website built with Flask and Bootstrap for Prajwal Thapa, a BASW student at Saraswati Multiple Campus (TU). The application features a glass-morphism design with smooth animations, dark mode toggle, and a contact form with file logging. It's designed to showcase his educational background in arts, social work studies, and commitment to community development in an elegant single-page application.

## System Architecture

The application follows a simple Flask-based architecture with a clean separation of concerns:

- **Backend**: Flask web framework serving templates and handling form submissions
- **Frontend**: Bootstrap 5 with custom CSS and vanilla JavaScript for interactivity
- **Styling**: Glass-morphism design with CSS custom properties and responsive layouts
- **Data Storage**: File-based logging for contact form submissions (no database required)
- **Deployment**: Gunicorn WSGI server with autoscale deployment target

## Key Components

### Backend Components
- **app.py**: Main Flask application with routes for homepage and contact form handling
- **main.py**: Application entry point for development server
- **Contact Form Handler**: Validates form inputs and logs submissions to files

### Frontend Components
- **templates/index.html**: Single-page application template with navigation and sections
- **static/css/style.css**: Custom styling with CSS variables and glass-morphism effects
- **static/js/script.js**: Interactive features including typing effects, scroll animations, and form validation
- **static/assets/**: Static assets including sample CV file

### Key Features
- Responsive navigation with glass-morphism effect
- Hero section with typing animation featuring social work and arts student titles
- Portfolio sections: About (BASW student info), Projects (Coming Soon placeholders), Skills (Social Work & Academic), Contact
- Dark mode toggle functionality
- Smooth scrolling and scroll-triggered animations
- Contact form with client-side validation
- File-based logging system for form submissions
- Personalized content for Prajwal Thapa's profile

## Data Flow

1. **Page Load**: Flask serves the main template with all portfolio sections
2. **User Interaction**: JavaScript handles smooth scrolling, animations, and form interactions
3. **Contact Submission**: 
   - Client-side validation occurs first
   - Form data is sent to Flask backend via POST request
   - Server validates data and logs to `logs/contact_submissions.log`
   - User receives feedback via flash messages
4. **Static Assets**: Served directly by Flask for CSS, JS, and asset files

## External Dependencies

### Python Dependencies
- **Flask 3.1.1**: Web framework for routing and templating
- **email-validator 2.2.0**: Email validation for contact forms
- **flask-sqlalchemy 3.1.1**: Database ORM (prepared for future database integration)
- **gunicorn 23.0.0**: Production WSGI server
- **psycopg2-binary 2.9.10**: PostgreSQL adapter (prepared for future database integration)

### Frontend Dependencies (CDN)
- **Bootstrap 5.3.0**: CSS framework for responsive design
- **Font Awesome 6.4.0**: Icon library
- **Google Fonts**: Inter and Poppins font families

### System Dependencies
- **PostgreSQL**: Database system (configured but not actively used)
- **OpenSSL**: SSL/TLS support

## Deployment Strategy

The application is configured for deployment on Replit with the following setup:

- **Runtime**: Python 3.11 with Nix package management
- **Web Server**: Gunicorn with bind to 0.0.0.0:5000
- **Deployment Target**: Autoscale for automatic scaling
- **Development Mode**: Hot reload enabled for development
- **Port Configuration**: Waits for port 5000 to be available

### Environment Configuration
- Session secret key configurable via `SESSION_SECRET` environment variable
- Development mode with debug logging enabled
- File-based logging with automatic directory creation

## Changelog

```
Changelog:
- June 26, 2025. Initial setup with John Doe template
- June 26, 2025. Customized for Prajwal Thapa:
  - Updated personal information (name, email, phone, location)
  - Changed hero typing animation to social work and arts student focused titles
  - Modified About section for BASW student with arts background
  - Updated skills to remove tech skills, focus on academic and social work skills
  - Changed projects to "Coming Soon" with social work and community themes
  - Updated contact information for Nepal location
  - Modified resume download filename and content to reflect arts background
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```

## Notes for Development

- The application is prepared for database integration with SQLAlchemy and PostgreSQL but currently uses file-based logging
- Glass-morphism design uses CSS custom properties for easy theme customization
- JavaScript is modular and extensible for additional interactive features
- Form validation occurs on both client and server sides
- Static assets are organized for easy maintenance and updates
- The portfolio content is placeholder data that should be customized for actual use