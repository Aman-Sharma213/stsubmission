
# Prashikshan Setu - Smart Internship Recommendation Platform

A comprehensive web-based platform that connects students with relevant internship opportunities using advanced matching algorithms and real-time job data from external APIs.

## Features

### Core Functionality
- **Smart Recommendation System**: Advanced matching algorithm that considers education level, skills, interests, and location preferences
- **Real-time Job Integration**: Fetches live internship data from Jooble API
- **User Authentication**: Secure Firebase-based authentication system
- **Personalized Profiles**: Individual user profiles with skill tracking and preferences
- **Save Internships**: Bookmark interesting opportunities for later review
- **Multi-role Support**: Separate interfaces for students and administrators

### User Features
- **Profile Creation**: Build comprehensive profiles with education, skills, and preferences
- **Intelligent Matching**: Get personalized internship recommendations with match percentages
- **Search & Filter**: Search internships by keywords, location, and other criteria
- **Application Tracking**: Save and manage internship applications
- **Real-time Updates**: Access to fresh job postings from Jooble API

### Admin Features
- **Internship Management**: Add, edit, and manage internship listings
- **User Analytics**: View platform statistics and user engagement
- **Job Data Monitoring**: Monitor external API integrations
- **Content Moderation**: Manage platform content and listings

## Technology Stack

### Frontend
- **HTML5/CSS3**: Modern, responsive design
- **JavaScript (ES6+)**: Interactive functionality and API integrations
- **CSS Grid/Flexbox**: Responsive layout system
- **Font Awesome**: Icon library
- **Google Fonts**: Typography (Poppins)

### Backend Services
- **Firebase Firestore**: NoSQL database for user data and internships
- **Firebase Authentication**: User authentication and authorization
- **Firebase Analytics**: User behavior tracking

### External APIs
- **Jooble API**: Real-time job/internship data
- **Email Integration**: Application submission via mailto links

## Installation & Setup

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection for Firebase and API services
- Firebase project setup

### Firebase Configuration
1. Create a new Firebase project at [Firebase Console](https://console.firebase.google.com)
2. Enable Firestore Database
3. Enable Authentication (Email/Password)
4. Get your Firebase configuration object
5. Replace the Firebase config in the HTML file:

```javascript
const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "your-sender-id",
    appId: "your-app-id",
    measurementId: "your-measurement-id"
};
```

### Jooble API Setup
1. Register at [Jooble API](https://jooble.org/api/about)
2. Get your API key
3. Replace the API key in the code:

```javascript
const JOOBLE_API_KEY = 'your-jooble-api-key';
```

### Deployment
1. Clone or download the project files
2. Update Firebase and Jooble API configurations
3. Deploy to any web hosting service (GitHub Pages, Netlify, Firebase Hosting, etc.)
4. Access the application through your domain

## Usage Guide

### For Students
1. **Sign Up**: Create an account with email and password
2. **Complete Profile**: Add education, skills, interests, and location
3. **Get Recommendations**: Use the recommendation system to find matching internships
4. **Browse Listings**: Explore real-time job postings from Jooble
5. **Save Opportunities**: Bookmark interesting internships for later
6. **Apply**: Use direct application links or email integration

### For Administrators
1. **Admin Account**: Sign up with admin role
2. **Add Internships**: Create new internship listings
3. **Manage Content**: Edit or remove existing listings
4. **Monitor Analytics**: View platform usage statistics
5. **API Management**: Monitor external API integrations

## Matching Algorithm

The platform uses a sophisticated matching algorithm that considers:

- **Education Match (20%)**: Compares user education level with requirements
- **Skills Match (40%)**: Uses cosine similarity to match skill sets
- **Interest Match (25%)**: Matches user interests with job sectors
- **Location Match (15%)**: Considers geographic preferences and remote work

Match scores are calculated as percentages, with minimum thresholds to ensure quality recommendations.

## Database Schema

### Users Collection
```
users: {
  uid: string,
  name: string,
  email: string,
  role: 'student' | 'admin',
  createdAt: timestamp
}
```

### Internships Collection
```
internships: {
  title: string,
  company: string,
  description: string,
  requiredSkills: array,
  sector: string,
  educationLevel: string,
  location: string,
  stipend: string,
  createdAt: timestamp,
  source: 'manual' | 'api'
}
```

### Saved Internships Collection
```
savedInternships: {
  userId: string,
  jobId: string,
  title: string,
  company: string,
  description: string,
  location: string,
  salary: string,
  link: string,
  savedAt: timestamp
}
```

## API Integrations

### Jooble API
- **Endpoint**: `https://jooble.org/api/{API_KEY}`
- **Method**: POST
- **Purpose**: Fetch real-time internship data
- **Rate Limits**: Check Jooble documentation for current limits

### Firebase APIs
- **Authentication**: User sign-up, login, logout
- **Firestore**: Data storage and retrieval
- **Analytics**: User behavior tracking

## Security Features

- **Firebase Authentication**: Secure user authentication
- **Data Validation**: Input sanitization and validation
- **Access Control**: Role-based access to admin features
- **CORS Handling**: Proper cross-origin resource sharing
- **XSS Protection**: Input escaping and content sanitization

## Performance Optimizations

- **Lazy Loading**: Content loaded as needed
- **Caching**: Firebase SDK caching for improved performance
- **Debounced Searches**: Optimized search functionality
- **Responsive Design**: Optimized for all device sizes
- **CDN Usage**: External libraries loaded from CDNs

## Browser Compatibility

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Development Guidelines
- Follow existing code style and conventions
- Test all new features thoroughly
- Update documentation for new features
- Ensure mobile responsiveness
- Validate all user inputs

## Troubleshooting

### Common Issues
- **Firebase Connection**: Check API keys and project configuration
- **Jooble API**: Verify API key and rate limits
- **Authentication**: Ensure Firebase Auth is properly configured
- **CORS Errors**: Check domain configuration in Firebase

### Support
- Check browser console for error messages
- Verify all API keys are correctly configured
- Ensure internet connection is stable
- Clear browser cache if experiencing issues

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Firebase for backend services
- Jooble for job API services
- Font Awesome for icons
- Google Fonts for typography

## Version History

- **v1.0.0**: Initial release with core functionality
- **v1.1.0**: Added save internships feature
- **v1.2.0**: Enhanced matching algorithm
- **v1.3.0**: Improved UI/UX and mobile responsiveness

---

**Prashikshan Setu** - Bridging the gap between students and opportunities.
