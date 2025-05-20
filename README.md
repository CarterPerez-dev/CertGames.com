# SELLING!!!
----
<p align="center">
  <a href="https://github.com/CarterPerez-dev/ProxyAuthRequired">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=CarterPerez-dev&repo=ProxyAuthRequired&theme=dark&hide_border=true" alt="ProxyAuthRequired Repo" />
  </a>
</p>

![image](https://github.com/user-attachments/assets/da6acb50-9bb0-46be-b319-6bab7cfa7605)

## Due to an unforseen life event, I am need of money, 
## So I am selling this codebase including the IOS app, Web app, assets, customers, etc etc. Please reach out to [My Email](carterperez@certgames.com)
---
# Overview

[API](https://github.com/CarterPerez-dev/CertGames.com/blob/main/API.md)
[Structure](https://github.com/CarterPerez-dev/CertGames.com/blob/main/Tree.md)
[Start to End Pictures](https://github.com/CarterPerez-dev/CertGames.com/blob/main/Start-End-Pics.md)

CertGames is a comprehensive cybersecurity training platform designed to help IT professionals prepare for certification exams through gamified learning experiences. The platform integrates advanced AI-driven tools, practice tests, and interactive simulations to create an engaging learning environment.

**Live Platform:** [CertGames.com](https://certgames.com)  
**iOS App:** [App Store Link](https://apps.apple.com/us/app/comptia-cert-games-practice/id6743811522)  
**LinkedIn:** [CertGames](https://www.linkedin.com/company/certgames/) | [Developer Profile](https://www.linkedin.com/in/carterperez-dev/)  
**Portfolio:** [CarterPerez-dev.com](https://carterperez-dev.com/)

## Table of Contents

- [Architecture Overview](#architecture-overview)
- [Core Components](#core-components)
- [Tech Stack](#tech-stack)
- [Reactive Multi-Platform Design](#reactive-multi-platform-design)
- [API Architecture](#api-architecture)
- [AI Integration](#ai-integration)
- [Database Schema](#database-schema)
- [Security Implementation](#security-implementation)
- [Deployment Architecture](#deployment-architecture)
- [Performance Optimizations](#performance-optimizations)
- [Testing Methodology](#testing-methodology)
- [Future Development Roadmap](#future-development-roadmap)
- [Contact & Support](#contact--support)

***`FWI, if you are curious what all those HTML files are in my honeypot, as well as what my honeypot even does/ looks like in my admin panel -- Well I actually extracted what I did in this appliction and made it a python package, so that has all teh documentation you need about it`***

[flask-honeypot](https://github.com/CarterPerez-dev/flask-honeypot)

## Architecture Overview

CertGames implements a distributed microservices architecture with containerized components, focusing on security, scalability, and high availability. The platform is built on modern web technologies with cross-platform support and highly optimized DevOps configurations for both development and production environments.

### System Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        Cloudflare DNS/CDN Layer                         │
└───────────────────────────────┬─────────────────────────────────────────┘
                               ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                           NGINX Reverse Proxy                           │
└───────────────────────────────┬─────────────────────────────────────────┘
                               ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                          Flask API Server                               │
│                    (uWSGI + Microservices Endpoints)                    │
└───────────┬─────────────────────┬──────────────────────┬────────────────┘
            │                     │                      │
            ▼                     ▼                      ▼
┌────────────────────┐   ┌─────────────────────┐    ┌────────────────┐
│  React Front-end   │   │  Celery Workers     │    │ Socket.IO      │
│  (SPA Application) │   │  (Async Processing) │    │ (Real-time)    │
└────────────────────┘   └─────────┬───────────┘    └────────────────┘
                                    │
                                    ▼
┌──────────────────────┐   ┌─────────────────────┐    ┌────────────────┐
│  React Native iOS    │   │  Redis              │    │  MongoDB Atlas │
│  (Mobile App)        │──▶│  (Cache/Sessions)   │◀───│  (Database)    │
└──────────────────────┘   └─────────────────────┘    └────────────────┘
```

## Core Components

The CertGames platform consists of several interconnected components that work together to deliver a seamless experience:

### 1. Web Application (React)

The web frontend is built as a single-page application using React with Redux for state management. Key features include:

- **Redux Toolkit** implementation for efficient state management
- **Themeable UI** with dynamic color schemes for accessibility
- **Socket.IO** integration for real-time features
- **Responsive design** with mobile-first approach
- **SEO optimization** with React Helmet and structured data
- **Protected routes** with subscription-based access control for Defense In Depth

The React frontend offers a smooth, interactive experience with:

- **Dynamic Question Rendering**: Custom components for different question types
- **Real-time Progress Tracking**: Socket-based progress synchronization
- **Score Calculation Engine**: Client-side scoring with server validation
- **Animated Transitions**: Smooth page and component transitions
- **Tooltip System**: Context-aware help and explanations
- **Achievement Notifications**: Real-time achievement unlocks with animations
- **Dark/Light Mode Toggle**: Complete theming with dynamic color schemes
- **Keyboard Navigation**: Full keyboard support for accessibility
- **Drag and Drop Interfaces**: Interactive learning components
- **Interactive Charts**: Performance visualization with Recharts
- **Client-side Caching**: Optimized data storage for performance

### 2. Mobile Application (React Native/Expo)

The iOS application is built with React Native and Expo, sharing business logic with the web application:

- **Expo SDK 52** for simplified native feature access
- **AsyncStorage/SecureStore** for secure data persistence
- **React Navigation 7** for native navigation patterns
- **Offline support** with queue-based synchronization
- **Native authentication** via Apple and Google Sign-In
- **In-app purchases** through Apple's StoreKit

The mobile app provides a fully-featured experience with:

- **Push Notifications**: Daily question reminders and updates
- **Biometric Authentication**: FaceID/TouchID login options
- **Deep Linking**: Universal links to specific content
- **Offline Mode**: Complete test-taking without internet connection
- **Background Synchronization**: Data syncing when app is inactive
- **Dynamic Content Updates**: OTA updates without App Store approval
- **Device-specific Optimizations**: Adaptive layouts for different screens
- **Haptic Feedback**: Enhanced interactive experience
- **Native Share Functionality**: Integrated with iOS share sheet
- **Low Power Mode Detection**: Adjusted performance for battery saving
- **Accessibility Features**: VoiceOver support and dynamic text sizing

### 3. Backend API (Flask/Python)

A comprehensive Flask application serves as the backend API layer:

- **Modular Blueprint architecture** for organized endpoint groups
- **JWT authentication** with advanced security features
- **uWSGI server** optimized for high performance and connection handling
- **Rate limiting** with progressive penalties to prevent abuse
- **Async processing** with Celery for long-running tasks
- **WebSocket support** via Socket.IO for real-time features
- **OpenAI integration** for AI-assisted learning tools
- **Google Gemini integration** for portfolio generation and analysis

The backend implements sophisticated features:

- **Tiered Subscription Management**: Integration with Stripe and Apple IAP
- **Dynamic Test Generation**: Algorithm-based test compilation from question banks
- **Spaced Repetition System**: Intelligent question scheduling based on user performance
- **Achievement Engine**: Complex rule-based achievement tracking and awards
- **Analytics Pipeline**: Comprehensive user performance tracking
- **Email Service Integration**: Transactional and marketing email capabilities
- **Webhook Processing**: External service integration (payments, notifications)
- **Content Delivery Network**: Dynamic asset management and serving
- **Content Moderation System**: AI-assisted moderation for user-generated content
- **OAuth2 Provider Integration**: Google and Apple authentication flows
- **IP Geolocation**: Location-based content and security features
- **Token Refresh Mechanism**: Secure JWT token lifecycle management

### 4. Portfolio Generator (NEW)

A powerful AI-driven portfolio creation tool for users:

- **Resume-to-Portfolio conversion** using Google's Gemini AI
- **Automated code generation** for complete React-based portfolio websites
- **One-click deployment** to Vercel via GitHub integration
- **Customizable templates** with various style preferences
- **Live code editor** for fine-tuning generated code
- **Error fixing capabilities** with AI assistance

The Portfolio Generator includes:

- **Template Selection**: Multiple design themes and layouts
- **Style Preferences**: Color scheme and typography options
- **Content Extraction**: Intelligent parsing of resume information
- **GitHub Integration**: Automated repository creation
- **Vercel Deployment Pipeline**: One-click hosting deployment
- **Custom Domain Support**: Personal domain configuration
- **CI/CD Setup**: Automated builds and deployments
- **Code Customization**: Full editor for manual adjustments
- **Responsive Design Checking**: Mobile preview capabilities
- **SEO Optimization**: Meta tags and structured data generation
- **Analytics Integration**: Visitor tracking setup
- **Browser Compatibility Testing**: Cross-browser validation

### 5. Security Features

Enterprise-grade security built into the core:

- **Comprehensive honeypot system** with 20+ fake admin pages
- **Advanced threat detection** for identifying scanning and attack patterns
- **Geolocation tracking** for suspicious activities
- **TOR and proxy detection** to identify anonymous access attempts
- **Progressive rate limiting** with increasing penalties for abusive behavior
- **JWT-based authentication** with secure cookie management
- **CSRF protection** for sensitive operations

Security implementations include:

- **Security Headers Framework**: Strict CSP, X-Frame-Options, etc.
- **Input Sanitization Pipeline**: Multi-layer validation and cleaning
- **API Abuse Detection**: Pattern recognition for malicious usage
- **Failed Login Tracking**: Progressive lockouts with tiered penalties
- **SQL Injection Prevention**: Parameterized queries throughout
- **XSS Protection Layers**: Content Security Policy and output encoding
- **CSRF Token System**: State-changing action protection
- **Session Hijacking Prevention**: Secure session management
- **Secure Password Policy Enforcement**: Strength requirements and rotation
- **Automated Vulnerability Scanning**: CI/CD integrated security checks
- **Data Masking**: Sensitive information protection in logs
- **User Account Isolation**: Strict permission boundaries

### 6. Infrastructure Components

- **NGINX** as a reverse proxy with optimized configuration for both dev and prod environments
- **Redis** for session management, caching, and Celery broker
- **MongoDB Atlas** as the primary database
- **Docker** with separate development and production configurations
- **Cloudflare** for CDN, DNS, and DDoS protection
- **Git** for Version Control and CI/CD

Infrastructure features include:

- **Multi-Environment Configurations**: Development, staging, and production
- **Traffic Management**: Intelligent routing and load balancing
- **Auto-scaling Resources**: Demand-based resource allocation
- **High Availability Setup**: Redundancy and failover configurations
- **Disaster Recovery Plan**: Regular backups and restore procedures
- **Security Monitoring**: Intrusion detection and prevention
- **Performance Tracking**: Resource utilization and bottleneck identification
- **Cost Optimization**: Resource allocation efficiency
- **Centralized Logging**: Aggregated logs across services
- **Database Optimization**: Indexing and query performance tuning
- **Cache Warming**: Proactive caching for common requests
- **Geographic Distribution**: Content delivery optimization
- **Compliance Support**: Data handling according to regulations

## Tech Stack

### Frontend (Web)

```json
{
  "Core": {
    "Framework": "React 18.3.1",
    "State Management": "Redux Toolkit",
    "Routing": "React Router 7.1.1"
  },
  "UI/UX": {
    "Styling": "CSS Modules + CSS Variables for theming",
    "Icons": "React Icons",
    "Charts": "Recharts 2.15.1",
    "Animations": "CSS Transitions + React Spring",
    "Data Visualization": "D3.js (integrated via Recharts)"
  },
  "Performance": {
    "Code Splitting": "Dynamic imports with React.lazy()",
    "Bundle Optimization": "Craco + Webpack 5 custom config",
    "Caching Strategy": "Redux persistor + Local Storage",
    "Lazy Loading": "React Suspense + window.IntersectionObserver"
  },
  "Build Tools": {
    "Package Manager": "npm",
    "Bundler": "Webpack 5 (via Craco)",
    "Transpiler": "Babel with custom plugins",
    "Minification": "Terser + CSS Minimizer"
  },
  "DevOps": {
    "Linting": "ESLint with custom config",
    "Testing": "Jest + React Testing Library",
    "CI/CD": "GitHub Actions",
    "Monitoring": "Custom performance metrics + Web Vitals tracking"
  }
}
```
---
### Mobile (iOS)

```json
{
  "Core": {
    "Framework": "React Native",
    "Expo": "Expo SDK 52",
    "State Management": "Redux Toolkit",
    "Navigation": "React Navigation 7"
  },
  "Native Features": {
    "Authentication": "Expo Apple Authentication, Google Sign-In",
    "Storage": "Expo SecureStore + AsyncStorage",
    "Network": "Axios with custom retry logic",
    "In-App Purchases": "React Native IAP"
  },
  "UI/UX": {
    "Components": "Custom components with native styling",
    "Animations": "React Native Reanimated",
    "Haptics": "Expo Haptics",
    "Gestures": "React Native Gesture Handler"
  },
  "Device Support": {
    "iOS Version": "iOS 14+",
    "Form Factors": "iPhone, iPad (Universal App)",
    "Orientation": "Portrait only (optimized experience)",
    "Deep Linking": "Universal Links via Expo"
  },
  "Build System": {
    "Development": "Expo Go + Dev Client",
    "Production": "EAS Build with custom profile",
    "Distribution": "App Store Connect + EAS Update"
  }
}
```
---
### Backend (API)

```json
{
  "Core": {
    "Framework": "Flask 3.1.1",
    "WSGI Server": "uWSGI 2.0.29 with Gevent workers",
    "Authentication": "JWT + OAuth 2.0",
    "Session Management": "Flask-Session with Redis backend"
  },
  "Data Layer": {
    "Database": "MongoDB Atlas (Document-oriented NoSQL)",
    "ORM": "PyMongo with custom abstraction layer",
    "Caching": "Redis 7.2 with tiered expiration strategy",
    "Data Validation": "Custom schema validation + Pydantic"
  },
  "Asynchronous Processing": {
    "Task Queue": "Celery 5.3.6",
    "Message Broker": "Redis",
    "Scheduling": "Celery Beat for periodic tasks",
    "Concurrency": "Gevent workers (8) with thread pool (5)"
  },
  "AI Integration": {
    "LLM Providers": [
      "OpenAI GPT-4o API",
      "Google Gemini Pro API"
    ],
    "Streaming Support": "Flask response streaming + AI provider streaming",
    "Prompt Engineering": "Custom prompt templates with parameter injection",
    "Rate Limiting": "Tiered per-feature limits with progressive penalties"
  },
  "Security Features": {
    "Authentication": "OAuth 2.0 + JWT + Secure HTTP-only cookies",
    "Rate Limiting": "IP-based, progressive with Redis tracking",
    "Honeypot System": "20+ fake admin pages with interaction tracking",
    "Threat Detection": "Geo-tracking + TOR detection + scanning patterns",
    "CSRF Protection": "Token-based validation for sensitive operations",
    "Input Validation": "Custom sanitization and validation",
    "Headers": "Strict security headers via NGINX"
  },
  "APIs and Protocols": {
    "REST API": "JSON with Flask Blueprints",
    "WebSockets": "Socket.IO for real-time features",
    "Webhooks": "For Stripe integration and Apple IAP verification",
    "Payment Processing": "Stripe API + Apple In-App Purchase Server Notifications"
  }
}
```
---
### Infrastructure

```json
{
  "Containerization": {
    "Platform": "Docker with docker-compose",
    "Environment Configurations": {
      "Development": "docker-compose.yml.dev with hot-reloading",
      "Production": "docker-compose.yml with optimized settings"
    },
    "Container Registry": "Private Docker Hub repository",
    "Resource Limits": "Defined per-service CPU and memory constraints",
    "Networking": "Custom bridge network with internal DNS"
  },
  "Web Servers": {
    "Load Balancer": "NGINX with optimized configurations",
    "Environment-Specific Configs": {
      "Development": "Developer-friendly settings with WebSocket proxying",
      "Production": "Performance-optimized with caching and security headers"
    },
    "SSL Termination": "Cloudflare at edge + internal self-signed certs"
  },
  "Message Queuing": {
    "Primary Queue": "Redis for Celery tasks",
    "Durability": "Redis AOF persistence with 1-second fsync",
    "Monitoring": "Redis INFO stats collection via Celery Beat tasks"
  },
  "Caching": {
    "Session Cache": "Redis with 24-hour expiry",
    "Content Cache": "Cloudflare edge caching + Redis L2 cache",
    "Query Cache": "MongoDB query results in Redis (30-minute TTL)"
  },
  "Database": {
    "Primary DB": "MongoDB Atlas M20 cluster (3 nodes)",
    "Replication": "Atlas automatic replication with 3 nodes",
    "Backup": "Daily automated backups with 30-day retention",
    "Scaling": "Auto-scaling enabled with custom triggers"
  },
  "CDN & DNS": {
    "Provider": "Cloudflare Enterprise",
    "Configuration": "Custom page rules, cache TTLs by content type",
    "Security": "WAF with custom ruleset + Bot Management",
    "DNS": "Cloudflare DNS with DNSSEC enabled"
  },
  "Monitoring": {
    "Application Metrics": "Custom in-app telemetry with MongoDB storage",
    "Server Monitoring": "Resource utilization tracking via Celery Beat",
    "Scheduled Health Checks": "10-minute interval API endpoint verification",
    "Logs": "Structured JSON logging with automatic rotation"
  },
  "Disaster Recovery": {
    "Database": "Point-in-time recovery via MongoDB Atlas",
    "Configuration": "Docker Compose templates in version control",
    "Deployment": "Automated build and deployment pipeline",
    "Backup Testing": "Monthly restoration tests for validation"
  }
}
```
---
## Reactive Multi-Platform Design

CertGames employs a reactive architecture pattern to ensure consistency across web and mobile platforms while optimizing for each platform's unique capabilities.

### Key Implementation Points:

1. **Isomorphic Redux Store**: The Redux store structure is identical between web and mobile, with platform-specific middleware handling persistence differences.

2. **Shared API Client**: A custom API client abstraction layer provides consistent data fetching with platform-specific adapters (Axios on web, modified Axios on mobile with offline support).

3. **Cross-Platform Authentication**: OAuth 2.0 flows are standardized but implemented with platform-appropriate SDKs (web browser redirects vs. native iOS authentication).

4. **Custom Hooks Library**: Common business logic is encapsulated in custom React hooks that are reused across platforms with platform-specific implementations where needed.

5. **Responsive Design System**: A unified design system with theme variables that are implemented via CSS variables on web and StyleSheet on mobile.

### Implementation Details

Our Reactive Multi-Platform architecture includes:

- **Platform Detection**: Dynamic feature enabling based on capabilities
- **Capability Abstraction**: Unified API for platform-specific features
- **Component Adaptation**: Responsive components that adjust to platform
- **Input Method Handling**: Touch vs. mouse vs. keyboard optimizations
- **Authentication Flow Variance**: Platform-appropriate auth experiences
- **Shared Redux Actions**: Common action creators with platform variations
- **Media Handling**: Adaptive media loading based on device capabilities
- **Error Boundary Strategy**: Platform-specific error recovery mechanisms
- **Offline Capability Detection**: Feature availability based on connectivity
- **Theme Adaptation**: System-integrated dark/light mode detection
- **Notification Strategy**: Web push vs. native notification handling
- **Payment Processing**: Web-based Stripe vs. native IAP for transactions
- **Performance Profiling**: Platform-specific monitoring and optimization
- **Accessibility Compliance**: WCAG standards across platforms

The backend API follows a modular architecture using Flask Blueprints. Each functional domain is implemented as a separate blueprint with its own routes, business logic, and middleware.

### API Features

- **Modular Blueprint Structure**: 180+ routes organized into 25+ domain-specific blueprints
- **Environment-specific Configurations**: Separate development and production settings
- **Robust Middleware Pipeline**: Authentication, rate limiting, CSRF protection
- **Advanced Security Features**: Progressive rate limiting with increasing penalties
- **Real-time Capabilities**: Socket.IO integration for live updates
- **Comprehensive Documentation**: Consistently structured API documentation

### API Documentation

The API follows RESTful principles with consistent patterns:

- Base URL structure: `https://certgames.com/api/`
- Authentication: JWT tokens in Authorization header (`Bearer <token>`)
- Response format: JSON with consistent structure
- Error handling: Standardized error codes and messages
- Rate limiting: Progressive with header information

Example endpoint structure:

```json
{
  "Authentication": {
    "/api/test/login": {
      "method": "POST",
      "description": "User login with credentials",
      "parameters": {
        "usernameOrEmail": "string",
        "password": "string"
      },
      "response": {
        "user_id": "string",
        "username": "string",
        "email": "string",
        "coins": "integer",
        "xp": "integer",
        "level": "integer",
        "achievements": "array",
        "subscriptionActive": "boolean"
      }
    },
    "/api/oauth/verify-google-token": {
      "method": "POST",
      "description": "Verify Google OAuth token from mobile",
      "parameters": {
        "token": "string",
        "userData": "object",
        "platform": "string"
      },
      "response": {
        "success": "boolean",
        "userId": "string"
      }
    }
  },
  "User Management": {
    "/api/test/user/{user_id}": {
      "method": "GET",
      "description": "Get user details",
      "parameters": {
        "user_id": "path parameter"
      },
      "response": "User object with full details"
    },
    "/api/test/user/{user_id}/daily-bonus": {
      "method": "POST",
      "description": "Claim daily login bonus",
      "parameters": {
        "user_id": "path parameter"
      },
      "response": {
        "success": "boolean",
        "newCoins": "integer",
        "newXP": "integer",
        "newlyUnlocked": "array of achievement IDs"
      }
    }
  },
  "Test System": {
    "/api/test/tests/{category}/{test_id}": {
      "method": "GET",
      "description": "Get test by category and ID",
      "parameters": {
        "category": "path parameter",
        "test_id": "path parameter"
      },
      "response": "Complete test object with questions"
    },
    "/api/test/attempts/{user_id}/{test_id}/finish": {
      "method": "POST",
      "description": "Complete a test attempt",
      "parameters": {
        "user_id": "path parameter",
        "test_id": "path parameter",
        "score": "integer",
        "totalQuestions": "integer"
      },
      "response": {
        "message": "string",
        "newlyUnlocked": "array of achievement IDs",
        "newXP": "integer",
        "newCoins": "integer"
      }
    }
  },
  "AI Generation": {
    "/api/analogy/stream_analogy": {
      "method": "POST",
      "description": "Generate and stream analogy text",
      "parameters": {
        "analogy_type": "string (single|comparison|triple)",
        "concept1": "string",
        "concept2": "string (optional)",
        "concept3": "string (optional)",
        "category": "string"
      },
      "response": "Streaming text response"
    },
    "/api/scenario/stream_scenario": {
      "method": "POST",
      "description": "Generate cybersecurity scenario",
      "parameters": {
        "industry": "string",
        "attack_type": "string",
        "skill_level": "string",
        "threat_intensity": "string"
      },
      "response": "Streaming text response"
    }
  },
  "Portfolio Generation": {
    "/api/portfolio/generate-stream": {
      "method": "POST",
      "description": "Generate portfolio website from resume",
      "parameters": {
        "resume_text": "string",
        "preferences": "object"
      },
      "response": {
        "success": "boolean",
        "message": "string",
        "status": "string"
      }
    },
    "/api/portfolio/deploy": {
      "method": "POST",
      "description": "Deploy generated portfolio to Vercel",
      "parameters": {
        "portfolio_id": "string",
        "github_token": "string",
        "vercel_token": "string",
        "use_oauth": "boolean"
      },
      "response": {
        "success": "boolean",
        "message": "string",
        "task_id": "string",
        "status_url": "string"
      }
    }
  }
}
```
---
## AI Integration

CertGames leverages multiple AI models throughout the platform to enhance the learning experience, with specialized models for different tasks.

### AI-Powered Features

1. **Portfolio Generator (NEW)**: Creates complete React portfolio websites from resume text using Google's Gemini Pro API
2. **Analogy Generation**: Creates analogies for complex cybersecurity concepts using OpenAI's GPT-4o
3. **Scenario Creation**: Generates realistic cybersecurity scenarios for hands-on training
4. **GRC Question Generation**: Produces governance, risk, and compliance questions with adaptive difficulty
5. **Exploit Simulation**: Demonstrates conceptual exploit generation for educational purposes

### AI Integration Architecture

### Multi-model Approach

CertGames strategically uses different AI models for specialized tasks:

- **Gemini Pro**: Powers the portfolio generator with specialized code generation capabilities
- **GPT-4o**: Creates analogies, scenarios, and educational content with advanced reasoning
- **Custom Prompt Engineering**: Tailored instructions for each AI task to ensure high-quality outputs
- **Streaming Implementation**: Real-time streaming of AI responses for immediate user feedback

### Prompt Engineering Example

```python
def generate_grc_question(category, difficulty):
    """
    Generates a GRC-related multiple-choice question in JSON format.
    The model returns a JSON object with keys:
      question (string)
      options (array of 4 strings)
      correct_answer_index (int)
      explanations (dict of strings for "0","1","2","3")
      exam_tip (string)
    """
    prompt = f""" 
You are an expert in concepts found in certifications like CISSP, CompTIA Advanced Security Practitioner (CASP+), CISM, CRISC, and others. Your role is to generate 
challenging and diverse test questions using advanced mult-layered reasoning, related to governance, risk management, risk thresholds, types of risk, Audit, Management, Policy, Cyber Security Ethics, Threat Assessment, 
Leadership, Business Continuity, compliance, regulations, incident resposne, Incident Response and more. focusing on preparing for exams like CISSP/ISC2 and CompTIA certifications. Ensure the questions cover a wide range of scenarios,
principles, and concepts, with multiple-choice answers that are nuanced and complex and specific, avoiding repetitive patterns or overly simplified examples.

CONTEXT: The user has selected:
- Category: {category} (e.g., 'Regulation', 'Risk Management', 'Compliance', 'Audit', 'Governance', 'Management', 'Policy', 'Ethics', 'Threat Assessment', 'Leadership', 'Business Continuity', 'Incident Response', 'Random')
- Difficulty: {difficulty} (e.g., 'Easy', 'Medium', 'Hard')

REQUIREMENTS
1. Four options (0, 1, 2, 3) total, one correct answer. The incorrect options should be very plausible but not correct, requiring the test-taker to carefully differentiate.

2. Explanations:
   - For the correct answer: Provide multiple sentences detailing exactly why it's correct, clearly tying it back to the question's scenario or concept. Show how it fulfills the requirements asked in the question as well as why the other answer choices are incorrect/not the correct answer..
   - For each incorrect answer: Provide multiple sentences detailing why it is NOT correct aswell as why the other incorrect answer choices are incorrect, and why then tell the user what the correct answer is and why it is correct using advanced multi-layered reasoning. 
     Do not just say it's incorrect; fully explain why it falls short. 
     Highlight conceptual differences, limitations, or focus areas that differ from the question's criteria.
   - Regardless of user choice, the generated output must contain full explanations for all answer choices provided. The explanations are produced in advance as part of the JSON object. Each explanation should be at least 3 sentences, rich in detail and conceptual clarity using advanced multi-layered reasoning.

3. Include an "exam_tip" field that provides a short, memorable takeaway or mnemonic to help differentiate the correct concept from the others. The exam tip should help the user recall why the correct answer stands out using advanced multi-layered reasoning.

4. Return ONLY a JSON object with the fields:
   "question", "options", "correct_answer_index", "explanations", and "exam_tip"
   No extra text, no Markdown, no commentary outside the JSON.

5. For each explanation (correct and incorrect):
   - At minimum of 3 sentences for the correct answer.
   - if the user gets the answer correct provide minium 3 senetence answer as to why it is correct, but also why the other answer choices listed are not the correct answer using advanced multi-layered reasoning.
   - Substantial detail.
   - Clearly articulate conceptual reasons, not just factual statements using advanced multi-layered reasoning.

EXAMPLE FORMAT (this is not real content, just structure, make sure to use all topics not just the topic provided in this example):
{{
  "question": "The question",
  "options": ["Option 0","Option 1","Option 2","Option 3"],
  "correct_answer_index": 2,
  "explanations": {{
    "0": "Explain thoroughly why option 0 fails. Mention its scope, focus areas, and why that doesn't meet the question criteria and then explain what the correct answer is and why it is correct aswell as why the other answer choices are incorrect using advanced multi-layered reasoning.",
    "1": "Explain thoroughly why option 1 fails. Mention its scope, focus areas, and why that doesn't meet the question criteria and then explain what the correct answer is and why it is correct aswell as why the other answer choices are incorrect using advanced multi-layered reasoning.",
    "2": "Explain thoroughly why option 2 is correct, linking its characteristics to the question scenario and why the other answer choices are incorrect using advanced multi-layered reasoning",
    "3": "Explain thoroughly why option 3 fails. Mention its scope, focus areas, and why that doesn't meet the question criteria and then explain what the correct answer is and why it is correct aswell as why the other answer choices are incorrect using advanced multi-layered reasoning."
  }},
  "exam_tip": "A short, memorable hint or mnemonic that differentiates the correct approach from others using advanced multi-layered reasoning."
}}

Now generate the JSON object following these instructions.
"""

    try:
        response = client.chat.completions.create(
            model="gpt-4o",  
            messages=[{"role": "user", "content": prompt}],
            max_tokens=1200,
            temperature=0.7,
        )

        content = response.choices[0].message.content.strip()
      
        content = re.sub(r'^```.*\n', '', content)
        content = re.sub(r'\n```$', '', content)

        try:
            generated_question = json.loads(content)
        except json.JSONDecodeError as e:
            logger.error("JSON parsing error in generate_grc_question: %s", e)
            logger.error("Model returned: %s", content)
            raise ValueError("Model did not return valid JSON.") from e

        logger.info("Generated GRC question successfully.")
        return generated_question

    except Exception as e:
        logger.error(f"Error generating GRC question: {str(e)}")
        raise
```

### Portfolio Generation with Google Gemini

The new Portfolio Generator uses Google's Gemini Pro to create comprehensive React-based portfolio websites:

```python
def _construct_portfolio_prompt(self, resume_text, preferences):
    """Construct a detailed prompt for portfolio generation"""
    template_style = preferences.get('template_style', 'modern')
    color_scheme = preferences.get('color_scheme', 'professional')
    features = preferences.get('features', [])
    
    feature_requests = "\n".join([f"- {feature}" for feature in features])
    
    prompt = f"""
    As an expert web developer, create a professional portfolio website for a job seeker based on their resume. 
    I need you to generate a complete React-based portfolio that showcases their skills and experience effectively.
    
    RESUME TEXT:
    {resume_text}
    
    STYLE PREFERENCES:
    - Template style: {template_style}
    - Color scheme: {color_scheme}
    - Requested features: 
    {feature_requests}
    
    TECHNICAL REQUIREMENTS:
    1. Create a clean, responsive React-based portfolio website
    2. Use modern React with functional components and hooks
    3. Create these key files:
       - src/App.js - Main application component
       - src/index.js - Entry point
       - src/index.css - Global styles
       - src/App.css - THIS FILE MUST BE COMPLETELY EMPTY WITH NO CODE WHATSOEVER
       - src/reportWebVitals.js - defualt reportWebVitals file, and the dependency added to package.json
       - public/index.html - HTML template
       - package.json - Dependencies
       - Component files for each section (About, Projects, Skills, Contact, etc.)
       
    4. Make it visually appealing with clean CSS (no frameworks required, but can use simple CSS)
    5. Ensure the code is production-ready, well-structured, and error-free
    6. Include comments to explain the code structure
    7. Keep the design clean, professional and fully responsive
    8. IMPORTANT Maximize {resume_text} utilization by creatively inventing impressive and relevant content to fill any informational gaps, strictly prohibiting all placeholder text
    9. DO NOT USE COMMENTS OR WRITE ANY COMMENTS, DOUBLE ENSURE THERE ARE NO PLACEHOLDERS WHATSOEVER
    10. ENSURE EVERYTHING HAS CORRECT SYNTAX AND NO ERRORS
    
    DEPLOYMENT REQUIREMENTS:
    The code will be deployed to Vercel, so ensure it's compatible with their platform.
    """
    return prompt
```

## Database Schema

CertGames uses MongoDB as its primary database, leveraging its document-oriented nature for flexibility and scalability. The schema is designed for performance with appropriate indexing and denormalization where beneficial.

### Core Collections

```json
{
  "mainusers": {
    "indexes": ["username", "email", "subscriptionActive"],
    "fields": {
      "_id": "ObjectId",
      "username": "string",
      "email": "string",
      "password": "string (hashed)",
      "oauth_provider": "string (null|google|apple)",
      "coins": "integer",
      "xp": "integer",
      "level": "integer",
      "achievements": ["string (achievement IDs)"],
      "xpBoost": "float",
      "currentAvatar": "ObjectId (reference to shop)",
      "nameColor": "string (null|color code)",
      "purchasedItems": ["ObjectId (references to shop)"],
      "subscriptionActive": "boolean",
      "subscriptionStatus": "string (null|active|canceling|expired)",
      "subscriptionPlatform": "string (null|stripe|apple)",
      "lastDailyClaim": "Date",
      "practiceQuestionsRemaining": "integer",
      "subscriptionType": "string (free|premium)",
      "achievement_counters": {
        "total_tests_completed": "integer",
        "perfect_tests_count": "integer",
        "perfect_tests_by_category": {
          "[category]": "integer"
        },
        "highest_score_ever": "float",
        "lowest_score_ever": "float",
        "total_questions_answered": "integer"
      }
    }
  },
  "tests": {
    "indexes": ["testId", "category"],
    "fields": {
      "_id": "ObjectId",
      "testId": "integer",
      "testName": "string",
      "category": "string",
      "difficulty": "string",
      "description": "string",
      "questions": [{
        "id": "string",
        "question": "string",
        "options": ["string"],
        "correctAnswerIndex": "integer",
        "explanation": "string",
        "examTip": "string (optional)"
      }]
    }
  },
  "testAttempts": {
    "indexes": ["userId", "testId", "finished"],
    "fields": {
      "_id": "ObjectId",
      "userId": "ObjectId",
      "testId": "integer or string",
      "category": "string",
      "score": "integer",
      "totalQuestions": "integer",
      "selectedLength": "integer",
      "currentQuestionIndex": "integer",
      "shuffleOrder": ["integer"],
      "answerOrder": ["[integer]"],
      "finished": "boolean",
      "finishedAt": "Date (optional)",
      "examMode": "boolean",
      "examTimerSeconds": "integer",
      "answers": [{
        "questionId": "string",
        "userAnswerIndex": "integer or null",
        "correctAnswerIndex": "integer"
      }]
    }
  },
  "shop": {
    "indexes": ["type", "cost"],
    "fields": {
      "_id": "ObjectId",
      "title": "string",
      "description": "string",
      "imageUrl": "string",
      "type": "string (avatar|nameColor|xpBoost)",
      "cost": "integer or null",
      "effectValue": "any (depends on type)"
    }
  },
  "achievements": {
    "indexes": ["achievementId"],
    "fields": {
      "_id": "ObjectId",
      "achievementId": "string",
      "title": "string",
      "description": "string",
      "icon": "string",
      "criteria": {
        "testCount": "integer (optional)",
        "minScore": "float (optional)",
        "perfectTests": "integer (optional)",
        "coins": "integer (optional)",
        "level": "integer (optional)",
        "totalQuestions": "integer (optional)",
        "perfectTestsInCategory": "integer (optional)",
        "minScoreBefore": "float (optional)",
        "minScoreAfter": "float (optional)",
        "testsCompletedInCategory": "integer (optional)",
        "allTestsCompleted": "boolean (optional)"
      }
    }
  },
  "supportThreads": {
    "indexes": ["userId", "createdAt", "status"],
    "fields": {
      "_id": "ObjectId",
      "userId": "ObjectId",
      "title": "string",
      "status": "string (open|closed)",
      "createdAt": "Date",
      "updatedAt": "Date",
      "messages": [{
        "sender": "string (user|admin)",
        "content": "string",
        "timestamp": "Date"
      }]
    }
  },
  "subscriptionEvents": {
    "indexes": ["userId", "event", "timestamp"],
    "fields": {
      "_id": "ObjectId",
      "userId": "ObjectId",
      "event": "string (subscription_created|subscription_renewed|subscription_canceled|subscription_expired)",
      "platform": "string (stripe|apple)",
      "timestamp": "Date",
      "data": "object (platform-specific data)"
    }
  },
  "performanceMetrics": {
    "indexes": ["timestamp"],
    "fields": {
      "_id": "ObjectId",
      "avg_request_time": "float (seconds)",
      "avg_db_query_time": "float (seconds)",
      "data_transfer_rate": "float (MB/s)",
      "throughput": "float (requests/minute)",
      "error_rate": "float (0.0-1.0)",
      "timestamp": "Date"
    }
  },
  "globalRateLimits": {
    "indexes": ["clientId", "endpoint", "updatedAt"],
    "fields": {
      "_id": "ObjectId",
      "clientId": "string (hashed identifier)",
      "endpoint": "string (endpoint type)",
      "calls": ["Date (timestamps)"],
      "violations": "integer",
      "blockUntil": "Date (optional)",
      "updatedAt": "Date"
    }
  },
  "portfolios": {
    "indexes": ["user_id", "created_at"],
    "fields": {
      "_id": "ObjectId",
      "user_id": "ObjectId",
      "components_array": [{
        "path": "string",
        "content": "string"
      }],
      "components": "object (path: content)",
      "preferences": "object",
      "resume_text": "string",
      "created_at": "timestamp",
      "status": "string",
      "deployment": {
        "deployed": "boolean",
        "url": "string",
        "github_repo": "string"
      }
    }
  },
  "deployment_tasks": {
    "indexes": ["task_id", "user_id", "portfolio_id", "status"],
    "fields": {
      "_id": "ObjectId",
      "task_id": "string",
      "status": "string (pending|completed|failed)",
      "user_id": "string",
      "portfolio_id": "string",
      "error": "string",
      "result": "object",
      "started_at": "timestamp",
      "finished_at": "timestamp"
    }
  },
  "honeypot_interactions": {
    "indexes": ["timestamp", "ip_address", "page_type", "interaction_type"],
    "fields": {
      "_id": "ObjectId",
      "interaction_id": "string",
      "timestamp": "Date",
      "ip_address": "string",
      "user_agent": "string",
      "referer": "string",
      "page_type": "string",
      "interaction_type": "string",
      "http_method": "string",
      "path": "string",
      "query_string": "object",
      "headers": "object",
      "cookies": "object",
      "form_data": "object (optional)",
      "json_data": "object (optional)",
      "geoInfo": {
        "asn": "string",
        "org": "string",
        "country": "string"
      },
      "additional_data": "object"
    }
  },
  "scanAttempts": {
    "indexes": ["timestamp", "ip", "clientId"],
    "fields": {
      "_id": "ObjectId",
      "clientId": "string",
      "ip": "string",
      "path": "string",
      "method": "string",
      "timestamp": "Date",
      "user_agent": "string",
      "ua_info": "object",
      "asn_info": "object",
      "headers": "object",
      "query_params": "object",
      "form_data": "object",
      "json_data": "object",
      "cookies": "object",
      "is_tor_or_proxy": "boolean",
      "bot_indicators": "array",
      "hostname": "string",
      "is_port_scan": "boolean",
      "is_scanner": "boolean",
      "suspicious_params": "boolean",
      "notes": "array"
    }
  }
}
```

### Schema Design Principles

1. **Strategic Denormalization**: Test documents include all questions to minimize round trips for test loading, while user activity is stored in separate collections.

2. **Compound Indexing**: Multiple indexes support common query patterns, such as finding unfinished test attempts for a specific user.

3. **Temporal Data Management**: Time-series data like performance metrics and rate limiting have TTL indexes for automatic pruning.

4. **Flexible Document Structure**: Leverages MongoDB's schema flexibility while maintaining consistent patterns for similar document types.

5. **Embedded vs. Referenced**: Uses embedded documents for tightly coupled data (test questions) and references for shared resources (shop items).

### New Collections (Honeypot & Portfolio)

The system has been expanded with:

1. **honeypot_interactions**: Records all interactions with the honeypot system
2. **scanAttempts**: Tracks attempted scans and potential attacks
3. **portfolios**: Stores user-generated portfolio websites
4. **deployment_tasks**: Tracks the status of portfolio deployment operations

## Security Implementation

Security is a top priority in CertGames, with multiple layers of protection throughout the system.

### Security Features

1. **Multi-layered Authentication**:
   - Password hashing with bcrypt
   - OAuth 2.0 integration (Google, Apple)
   - Session management with Redis
   - Secure token storage (HTTP-only cookies on web, SecureStore on mobile)

2. **Access Control**:
   - Role-based permissions for admin features
   - Subscription-based access control for premium content
   - IP-based restrictions for admin portal

3. **Advanced Honeypot System (NEW)**:
   - 20+ fake admin/login pages for various systems (WordPress, phpMyAdmin, cPanel, etc.)
   - Interaction tracking and analysis for security intelligence
   - Geolocation tracking of suspicious activities
   - TOR and proxy detection capabilities
   - Progressive blocking of malicious actors

4. **Rate Limiting and DDoS Protection**:
   - Progressive rate limiting with increasing penalties
   - IP-based, client fingerprinting, and session-based tracking
   - Cloudflare DDoS protection
   - IP-based blocking for repeated violations

5. **Data Protection**:
   - TLS/SSL encryption for all connections
   - Sanitized inputs with custom validation
   - Parameterized database queries
   - Limited data exposure (principle of least privilege)

6. **Infrastructure Security**:
   - Container isolation
   - Regular security updates
   - Least privilege principle for service accounts
   - Network segmentation in Docker

7. **Monitoring and Auditing**:
   - Comprehensive request logging
   - Failed authentication tracking
   - Admin action auditing
   - Automated suspicious activity detection

### CSRF Protection Implementation

```python
# backend/middleware/csrf_protection.py
import secrets
from flask import request, session, jsonify, abort
from functools import wraps

def generate_csrf_token():
    """Generate a secure CSRF token and store it in the session"""
    if 'csrf_token' not in session:
        session['csrf_token'] = secrets.token_hex(32)
    return session['csrf_token']

def csrf_protect(admin_only=True):
    """
    CSRF protection middleware for admin routes.
    """
    def decorator(f):
        @wraps(f)
        def decorated_function(*args, **kwargs):
            if request.method in ['POST', 'PUT', 'DELETE', 'PATCH']:

                if not admin_only or request.path.startswith('/cracked'):
                    token = request.headers.get('X-CSRF-TOKEN')
                    session_token = session.get('csrf_token')
                    
                    if not token or not session_token or token != session_token:
                        return jsonify({"error": "CSRF token validation failed"}), 403
            
            return f(*args, **kwargs)
        return decorated_function
    return decorator
```

### Honeypot System

The new honeypot system provides valuable security intelligence:

```python
def log_scan_attempt(path, method, params=None, data=None):
    """
    Log comprehensive details about the scan attempt to the database.
    """
    try:
        client_id = get_client_identifier()
        
        ip = request.headers.get('X-Forwarded-For', request.remote_addr)
        if ip and ',' in ip:
            ip = ip.split(',')[0].strip()
        
        user_agent = request.headers.get('User-Agent', '')
        
        # 1. Reverse DNS lookup for additional intelligence
        hostname = None
        try:
            hostname = socket.gethostbyaddr(ip)[0]
        except:
            hostname = None
        
        # 2. Check for port scanning attempts
        is_port_scan = any(scan_term in path.lower() for scan_term in [
            'port', 'scan', 'nmap', 'masscan', 'shodan', 'censys'
        ])
        
        # 3. Check for common vulnerability scanners in user agent
        ua_lower = user_agent.lower() if user_agent else ""
        scanner_signs = ['nmap', 'nikto', 'sqlmap', 'acunetix', 'nessus', 
                        'zap', 'burp', 'whatweb', 'qualys', 'openvas']
        is_scanner = any(sign in ua_lower for sign in scanner_signs)
        
        # 4. Check for suspicious request parameters
        suspicious_params = False
        if params and request.args:
            param_checks = ['sleep', 'benchmark', 'exec', 'eval', 'union', 
                          'select', 'update', 'delete', 'insert', 'script']
            for param, value in request.args.items():
                if any(check in value.lower() for check in param_checks):
                    suspicious_params = True
                    break
        
        # Parse the user agent string for more details
        ua_info = {}
        try:
            if user_agent:
                parsed_ua = user_agents.parse(user_agent)
                ua_info = {
                    "browser": {
                        "family": parsed_ua.browser.family,
                        "version": parsed_ua.browser.version_string
                    },
                    "os": {
                        "family": parsed_ua.os.family,
                        "version": parsed_ua.os.version_string
                    },
                    "device": {
                        "family": parsed_ua.device.family,
                        "brand": parsed_ua.device.brand,
                        "model": parsed_ua.device.model
                    },
                    "is_mobile": parsed_ua.is_mobile,
                    "is_tablet": parsed_ua.is_tablet,
                    "is_pc": parsed_ua.is_pc,
                    "is_bot": parsed_ua.is_bot
                }
        except Exception as e:
            ua_info = {"parse_error": str(e)}
        
        # Get ASN info
        asn_info = extract_asn_from_ip(ip)
        
        # Detect if it's a likely bot
        bot_indicators = detect_bot_patterns(user_agent, {
            "path": path,
            "method": method
        })
        
        # Check if using Tor or proxy
        is_tor_or_proxy = detect_tor_or_proxy(ip)
        
        # Extract all headers for analysis
        headers = {key: value for key, value in request.headers.items()}
        
        # Build the scan log document
        scan_log = {
            "clientId": client_id,
            "ip": ip,
            "path": path,
            "method": method,
            "timestamp": datetime.utcnow(),
            "user_agent": user_agent,
            "ua_info": ua_info,
            "asn_info": asn_info,
            "headers": headers,
            "query_params": dict(request.args) if params else None,
            "form_data": dict(request.form) if data else None,
            "json_data": request.get_json(silent=True) if data else None,
            "cookies": {key: value for key, value in request.cookies.items()},
            "is_tor_or_proxy": is_tor_or_proxy,
            "bot_indicators": bot_indicators,
            "hostname": hostname,
            "is_port_scan": is_port_scan,
            "is_scanner": is_scanner,
            "suspicious_params": suspicious_params,
            "notes": []
        }
        
        # Insert into database
        db.scanAttempts.insert_one(scan_log)
        
        # Return the client ID for potential further actions
        return client_id
        
    except Exception as e:
        logger.error(f"Error logging scan attempt: {str(e)}")
        logger.error(traceback.format_exc())
        return None
```

CertGames uses a containerized deployment architecture with Docker, orchestrated through docker-compose for simplified deployment and scaling.

### Environment-Specific Configurations (NEW)

The application now features dedicated configurations for both development and production environments:

#### Development Environment
- **Docker Compose**: `docker-compose.yml.dev` with volume mounting for hot-reloading
- **Dockerfiles**: Specialized `Dockerfile.dev` for both frontend and backend with development tools
- **NGINX Config**: Developer-friendly configuration with WebSocket proxying
- **uWSGI Settings**: Development-optimized settings

```yaml
# Development Docker Compose
services:
  backend:
    container_name: backend_service
    build:
      context: ./backend
      dockerfile: Dockerfile.dev
    ports:
      - "5000:5000"
    volumes:
      - ./backend:/app
      - ./nginx/logs:/var/log/nginx
      - ./backend/security/proxy_cache:/app/security/proxy_cache
      - ./backend/security/geoip_db:/app/security/geoip_db  
    env_file:
      - .env
    networks:
      - xploitcraft_network
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:5000/health"]
      interval: 120s
      timeout: 10s
      retries: 3
      start_period: 40s
    depends_on:
      - redis

  frontend:
    container_name: frontend_service_dev
    build:
      context: ./frontend/my-react-app
      dockerfile: ops/Dockerfile.dev
    volumes:
      - ./frontend/my-react-app:/app
      - /app/node_modules
    env_file:
      - .env
    ports:
      - "3000:3000"
    networks:
      - xploitcraft_network
    restart: unless-stopped
```

#### Production Environment
- **Docker Compose**: Production-optimized `docker-compose.yml`
- **Dockerfiles**: Minified production builds with `Dockerfile.prod`
- **NGINX Config**: Performance-tuned with caching and security headers
- **uWSGI Settings**: Production-ready configuration for high throughput

```yaml
# Production Docker Compose
services:
  backend:
    container_name: backend_service
    build:
      context: ./backend
      dockerfile: Dockerfile.prod
    ports:
      - "5000:5000"
    volumes:
      - ./backend/security/proxy_cache:/app/security/proxy_cache
      - ./backend/security/geoip_db:/app/security/geoip_db    
    env_file:
      - .env
    networks:
      - xploitcraft_network
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:5000/health"]
      interval: 120s
      timeout: 10s
      retries: 3
      start_period: 40s
    depends_on:
      - redis

  frontend_builder:
    container_name: frontend_builder
    build:
      context: ./frontend/my-react-app
      dockerfile: ops/Dockerfile.prod
    volumes:
      - react_build:/app/build  
    networks:
      - xploitcraft_network
    restart: "no"  
```

### NGINX Configuration

Sample of the production NGINX configuration:

```
server {
    listen 80;
    listen [::]:80;
    server_name _; 

    # API proxy - direct to backend
    location /api/ {
        proxy_pass http://backend:5000/;
        proxy_http_version 1.1;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }

    # WebSocket support for Socket.IO
    location /api/socket.io/ {
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        
        proxy_pass http://backend:5000/api/socket.io/;
        
        proxy_buffering off;
        proxy_cache off;
        proxy_redirect off;
        
        # WebSocket timeouts
        proxy_read_timeout 86400; # 24 hours
        proxy_connect_timeout 7d;
        proxy_send_timeout 7d;
    }

    # Static assets
    location ~* \.(js|css|png|jpg|jpeg|gif|ico|svg|woff|woff2|ttf|eot)$ {
        root /usr/share/nginx/html;
        expires 30d;
        add_header Cache-Control "public, max-age=2592000";
        try_files $uri =404;
    }

    # Main SPA routes
    location / {
        root /usr/share/nginx/html;
        index index.html;
        try_files $uri $uri/ /index.html;
        
        # Security headers
        add_header X-Frame-Options "SAMEORIGIN" always;
        add_header X-Content-Type-Options "nosniff" always;
        add_header X-XSS-Protection "1; mode=block" always;
        add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
        add_header Referrer-Policy "strict-origin-when-cross-origin" always;
    }
}
```

### uWSGI Configuration (NEW)

The application now uses uWSGI instead of Gunicorn for better performance:

```ini
[uwsgi]
# Flask application
module = app:app

# Server settings
http-socket = 0.0.0.0:5000
master = true
processes = 4  

# Async settings 
async = 1000 
gevent = 1000
thunder-lock = true

# WebSocket support
http-websockets = true
http-auto-chunked = true
http-keepalive = true

# Performance settings
buffer-size = 65535  
socket-timeout = 60
harakiri = 60
post-buffering = 8192

# Keep-alive settings
http-keepalive = 30

# Resource limits
reload-on-rss = 7500
evil-reload-on-rss = 10000

# gevent stability settings
lazy-apps = true
need-app = true

# Logging
memory-report = true
log-4xx = true
log-5xx = true
```

### Deployment Process

1. **Development**: Code is developed locally with feature branches
2. **Testing**: Automated testing in GitHub Actions
3. **Build**: Docker images are built and tagged
4. **Deployment**: Docker Compose deployment script
5. **Verification**: Automated health checks post-deployment
6. **Monitoring**: Continuous monitoring of performance metrics

### Infrastructure as Code

The entire infrastructure is defined in code for reproducibility, with separate configurations for development and production environments.

## Performance Optimizations

CertGames employs multiple performance optimization techniques to ensure a fast, responsive experience for users.

### Backend Optimizations

1. **uWSGI Server (NEW)**: Replaced Gunicorn with uWSGI for better performance and connection handling

2. **Database Indexing**: Strategic indexes on MongoDB collections for common query patterns

3. **Caching Strategy**:
   - Redis for session data and API responses
   - Multi-level caching (memory, Redis, database)
   - Conditional ETag-based caching

4. **Asynchronous Processing**:
   - Celery for long-running tasks
   - Response streaming for AI-generated content
   - WebSockets for real-time updates

5. **Efficient Database Access**:
   - Batch operations for bulk updates
   - Projection queries to retrieve only needed fields
   - Connection pooling with PyMongo

6. **Load Optimization**:
   - NGINX compression and caching
   - Content preloading and lazy loading
   - Resource prioritization

### Frontend Optimizations

1. **Code Splitting**: Dynamic imports reduce initial bundle size

2. **Lazy Loading**: Components and assets loaded only when needed

3. **State Management**: Optimized Redux store with selective persistence

4. **Rendering Optimization**:
   - React.memo for component memoization
   - Virtualized lists for large data sets
   - CSS optimizations with critical path rendering

5. **Network Efficiency**:
   - GraphQL-like request batching
   - Debounced API calls
   - Progressive image loading

### Mobile Optimizations

1. **Native Performance**:
   - React Native gesture handler for fluid animations
   - Native module bridging for performance-critical features
   - Memory management with component lifecycle hooks

2. **Offline Support**:
   - AsyncStorage for data persistence
   - Queue-based synchronization for offline actions
   - Optimistic UI updates

3. **Battery Efficiency**:
   - Reduced background processing
   - Efficient location services usage
   - Network batching to minimize radio usage

### Testing Tools and Frameworks

- **Unit Testing**: Jest, React Testing Library, PyTest
- **Integration Testing**: Supertest, Redux Mock Store, MongoDB Memory Server
- **End-to-End Testing**: Cypress, Detox (for React Native)
- **Performance Testing**: Locust, Lighthouse, React Profiler
- **Security Testing**: OWASP ZAP, npm audit, Snyk, Bandit

### Test Automation

Automated testing is integrated into the development workflow:

1. **Pre-commit Hooks**: Linting and unit tests before commits
2. **CI Pipeline**: Full test suite runs on GitHub Actions
3. **Deployment Gates**: Tests must pass before deployment
4. **Scheduled Scans**: Regular security and performance testing
5. **Monitoring**: Continuous verification in production

### Testing Examples

```javascript
// Example React component test
describe('PortfolioForm Component', () => {
  test('submits resume text and preferences', async () => {
    const mockOnGenerationStart = jest.fn();
    const mockOnGenerationComplete = jest.fn();
    
    render(
      <PortfolioForm 
        userId="test-user-id"
        onGenerationStart={mockOnGenerationStart}
        onGenerationComplete={mockOnGenerationComplete}
        onError={jest.fn()}
      />
    );
    
    // Fill in form fields
    fireEvent.change(screen.getByLabelText(/resume text/i), {
      target: { value: 'Test resume content' }
    });
    
    fireEvent.click(screen.getByLabelText(/modern/i));
    fireEvent.click(screen.getByLabelText(/professional/i));
    
    // Submit form
    fireEvent.click(screen.getByRole('button', { name: /generate portfolio/i }));
    
    // Check that onGenerationStart was called
    expect(mockOnGenerationStart).toHaveBeenCalled();
    
    // Verify API call
    await waitFor(() => {
      expect(global.fetch).toHaveBeenCalledWith(
        '/api/portfolio/generate-stream',
        expect.objectContaining({
          method: 'POST',
          headers: expect.objectContaining({
            'Content-Type': 'application/json'
          }),
          body: JSON.stringify({
            resume_text: 'Test resume content',
            preferences: expect.objectContaining({
              template_style: 'modern',
              color_scheme: 'professional'
            })
          })
        })
      );
    });
  });
});
```

```python
# Example Flask API test
def test_portfolio_generation(client, monkeypatch):
    # Mock Gemini API call
    def mock_generate_portfolio(*args, **kwargs):
        return {
            "public/index.html": "<html><body>Test</body></html>",
            "src/index.js": "import React from 'react';",
            "src/App.js": "function App() { return <div>Test</div>; }"
        }
    
    monkeypatch.setattr("Clients.Gemini.gemini_helper.generate_portfolio", mock_generate_portfolio)
    
    # Send test request
    response = client.post(
        '/portfolio/generate-stream',
        json={
            'resume_text': 'Test resume',
            'preferences': {
                'template_style': 'modern',
                'color_scheme': 'professional'
            }
        },
        headers={'X-User-Id': 'test-user-id'}
    )
    
    # Check response
    assert response.status_code == 200
    assert response.json['success'] == True
    assert response.json['status'] == 'processing'
    
    # Check database entry
    portfolio = db.portfolios.find_one({'user_id': ObjectId('test-user-id')})
    assert portfolio is not None
    assert len(portfolio['components']) >= 3
```

## Future Development Roadmap

CertGames is actively evolving with several initiatives in progress:

1. **Android Application**: Currently in development to expand mobile reach

2. **Game-like Learning Tools**:
   - PBQ (Performance-Based Question) cybersecurity training games
   - Advanced scenario generation with adaptive difficulty
   - Personalized learning paths

3. **Expanded Content**:
   - Resume builder
   - Interactive penetration testing simulation environment
   - Hands-on "Hack the Box"-style challenges using dummy websites I have created
   - Video course integration directly into the platform

4. **Infrastructure Improvements**:
   - Enhanced monitoring and alerting
   - Automated scaling based on demand
   - Regional distribution for improved latency
   - Advanced caching strategies

5. **Community Features**:
   - Collaborative learning tools
   - Peer review system for practice assignments
   - Mentorship connections
   - Community Forum

### New Features in Development

1. **Portfolio Showcase**: Allow users to share and browse each other's AI-generated portfolios
2. **Adaptive Learning Paths**: Personalized exam preparation based on performance data
3. **AI Interview Preparation**: Practice responses to technical interview questions
4. **Certification Roadmap Planner**: Career progression recommendations
5. **Enhanced Security Simulations**: Real-world scenario practice

## Current Platform Statistics

- **Total Users**: 508 (108 paid subscribers, 400 free tier)
- **Content Library**: 130+ certification practice tests across 12 certification paths with 13,000 practice questions across all certifications
- **Response Time**: Average API response time under 30ms
- **Uptime**: 99.97% uptime since launch
- **Mobile Engagement**: 65% of premium users access via both web and iOS app
- **Portfolio Generation**: Average generation time of 3-5 minutes, with 92% success rate
- **Security Detection**: Honeypot system has identified and blocked over 500 potential threats

## Contact & Support

- **General Inquiries**: inquiry@certgames.com
- **Support**: support@certgames.com
- **Developer Contact**: dev@certgames.com
- **Phone**: 443-510-0866
- **LinkedIn**: [CertGames Company Page](https://www.linkedin.com/company/certgames/)

---

# License

*This codebase is Open-Source* 
-
*© 2025 CertGames | © 2025 AngelaMoss*
-
*Developed and Designed by ~/Carter-perez-dev*
--
*This README was created for the CertGames repository family*
-
*Last updated - @5/19/25 16:52:00*
------
*[Privacy Policy](https://certgames.com/privacy)*  😎  *[Terms of Service](https://certgames.com/terms)*
----
*"My confidence is powerful. I recognize myself as exceptional. I recognize myself as exceptional. I recognize myself as exceptional."*
     --One of the good ones...
