



# /frontend Structure and File Explanations

### `ops/` - Operations Files

*   **`Dockerfile.audit`**: Defines a Docker environment specifically for auditing application dependencies using `npm audit`, helping to identify security vulnerabilities in packages.
*   **`Dockerfile.dev`**: Configures a Docker container tailored for the development environment. It includes tools like `nodemon` and `react-scripts` for features like hot reloading and running the development server.
*   **`Dockerfile.prod`**: Specifies a multi-stage Docker build process to create an optimized and minimized production build of the React application, ready for deployment.

### `public/` - Public Assets

*   **`assets/manifest.json`**: The web app manifest file. It provides metadata for the application, enabling Progressive Web App (PWA) features by defining icons, start URL, theme colors, and display mode.
*   **`index.html`**: The main HTML entry point for the React application. It sets up essential metadata, favicons, font links, and contains the root `div` element where the React app is rendered.
*   **`robots.txt`**: Instructs web crawlers (like search engine bots) on which pages or sections of the site should or should not be crawled or indexed, managing SEO behavior.
*   **`sitemap.xml`**: Provides a map of the publicly accessible pages on the site. This helps search engines like Google discover and index the website's content more effectively.

### `src/` - Source Code

#### `AppSupport/`

*   **`global.css`**: Contains global CSS styles, resets, and utility classes applied across the entire application. This includes base HTML/body styling, scrollbar customizations, and the site-wide loading spinner animation.
*   **`reportWebVitals.js`**: A utility to measure and report various web vital metrics (like CLS, FCP, LCP, TTFB, INP) to the backend API. This helps monitor the application's performance from the user's perspective, particularly if the user is authenticated.

#### `components/` - Reusable UI Components & Pages

##### `cracked/` - Admin Dashboard

This directory contains all components and logic related to the admin dashboard.

*   **`modals/`**:
    *   **`ConfirmModal.css`**: Styles for the `ConfirmModal.js` component, defining the visual appearance of the modal backdrop, content area, message text, and confirmation/cancel buttons.
    *   **`ConfirmModal.js`**: A JavaScript utility function that programmatically creates and displays a confirmation modal. It returns a Promise that resolves if the user confirms or rejects if the user cancels or dismisses the modal.
*   **`styles/tabstyles/`**: This subdirectory houses individual CSS files, each dedicated to styling a specific tab within the 'Cracked' admin dashboard. This approach ensures a consistent yet distinct visual appearance for different management sections.
    *   `ActivityLogsTab.css`: Styles for the Activity Logs tab.
    *   `C2Tab.css`: Extensive styling for the Command & Control (C2) tab, including system lists, dashboards, and control panels.
    *   `CredentialsTab.css`: Styles for the Credentials Management tab, covering tables, filter panels, and credential detail views.
    *   `DailyTab.css`: Styles for the Daily PBQ (Performance-Based Question) management tab, including form elements and preview modals.
    *   `DbShellTab.css`: Styles for the Database Shell tab, specifically for displaying query results in a preformatted block.
    *   `HealthCheckTab.css`: Styles for the API Health Check monitoring tab, including status cards and informational sections.
    *   `HoneypotTab.css`: Styles for the Honeypot monitoring tab, including charts, activity lists, and detailed interaction views.
    *   `HtmlInteractionsTab.css`: Styles for the HTML Interactions monitoring tab, covering statistics cards, tables, and detail views.
    *   `LogIp.css`: Styles for the User Request Monitoring tab, including controls, tables, and expanded detail views.
    *   `NewsletterTab.css`: Styles for the Newsletter management tab, including campaign details and HTML previews.
    *   `OverviewTab.css`: Styles for the main Overview dashboard tab, including status panels and metric cards.
    *   `PerformanceTab.css`: Styles for the Performance Monitoring tab, including metric cards, charts, and benchmark tables.
    *   `RateLimitsTab.css`: Styles for the Rate Limits monitoring tab, including endpoint cards and usage bars.
    *   `RequestLogsTab.css`: Styles for the Request Logs tab, focusing on table display and filtering controls.
    *   `RevenueTab.css`: Styles for the Revenue dashboard tab, including stat cards and chart containers.
    *   `ServerMetricsTab.css`: Styles for the Server Metrics monitoring tab, including system info cards and metric grids.
    *   `SupportTab.css`: Styles for the Support Management tab, covering thread lists, chat messages, and input areas.
    *   `TestsTab.css`: Styles for the Test Management tab, primarily for table display and editing inputs.
    *   `ToolsTab.css`: Styles for the External Tools dashboard tab, focusing on the grid layout of tool cards.
    *   `UsersTab.css`: Styles for the User Management tab, including pagination, tables, and modal dialogs for user details and confirmations.
*   **`styles/CrackedAdminDashboard.css`**: Defines the overall layout and core styling for the 'Cracked' admin dashboard. This includes the sidebar, main content area, and common UI elements like cards, forms, tables, and status indicators, with responsive adjustments.
*   **`styles/CrackedAdminLogin.css`**: Provides the specific styling for the admin login page. It includes background effects (grid, particles, glow), card layout, form elements, and support for multiple visual themes to enhance the login experience.
*   **`tabs/`**: Contains the React components for each individual tab within the admin dashboard.
    *   **`ActivityLogsTab.js`**: Admin tab for viewing security and activity logs, including regular failed login attempts and admin access logs. Features filtering and CSV export functionality.
    *   **`C2Tab.js`**: A comprehensive Command & Control (C2) admin tab for real-time monitoring and interaction with connected systems. It includes a dashboard, system selection, command execution, credentials display, and utilizes Socket.IO for live updates.
    *   **`CredentialsTab.js`**: Admin tab for managing and viewing credentials harvested through C2 operations. It features advanced filtering, sorting, pagination, a detailed credential view with sensitive data masking, and data export capabilities.
    *   **`DailyTab.js`**: Admin tab for managing Daily Performance-Based Questions (PBQs). It allows creation and deletion of daily challenges, including a preview feature for the questions.
    *   **`DbShellTab.js`**: Admin tab providing a read-only shell interface to query the application's database collections. Users can specify a collection, apply text-based filters, and limit the number of results.
    *   **`HealthChecksTab.js`**: Admin tab for monitoring the backend API's health status. It displays operational status, response times, and allows manual health checks with an auto-refresh feature.
    *   **`HoneypotTab.js`**: Admin tab for monitoring honeypot interactions. It displays statistics, charts of activity (top paths, IPs), and detailed logs of interactions with various honeypot pages, offering overview and detailed views.
    *   **`HtmlInteractionsTab.js`**: Admin tab for monitoring user interactions with specific HTML honeypot elements. It provides an overview with stats and charts, detailed interaction logs, and individual interaction details with risk assessment.
    *   **`LogIp.js`**: Admin tab for detailed monitoring of user requests, capturing IP addresses, geolocations, and user identifiers. Features advanced filtering, sorting, pagination, request grouping by identifier type, and statistical overviews.
    *   **`NewsletterTab.js`**: Admin tab for managing newsletter campaigns. It allows for creating new campaigns, sending test emails, viewing subscriber lists, and managing sent campaigns.
    *   **`OverviewTab.js`**: The main admin dashboard overview tab. It presents a high-level summary of key application metrics like user counts, test attempts, system performance, and revenue, with links to more detailed sections.
    *   **`PerformanceTab.js`**: Admin tab for monitoring application performance. It includes database metrics, web vitals, error rates, and benchmarks, with historical data charts for trend analysis.
    *   **`RateLimitsTab.js`**: Admin tab for monitoring API rate limits per endpoint and user. It displays usage summaries, charts comparing endpoint usage, and a detailed table of individual rate limit statuses.
    *   **`RequestLogsTab.js`**: Admin tab for viewing API request logs. It allows filtering logs by path, method, or IP address to help monitor server traffic and identify potential issues.
    *   **`RevenueTab.js`**: Admin tab for tracking revenue metrics. It displays key figures like Monthly Recurring Revenue (MRR), new subscribers, all-time revenue, platform distribution (Stripe vs. Apple), and recent signup/cancellation feeds.
    *   **`ServerMetricsTab.js`**: Admin tab for displaying real-time server metrics. It shows CPU usage, memory usage, disk space, network traffic, and top processes, along with historical charts for trend analysis.
    *   **`SupportTab.js`**: Admin interface for managing user support threads. It allows admins to view conversations, reply to users, close threads, and initiate new threads for users, with real-time updates via Socket.IO.
    *   **`TestsTab.js`**: Admin tab for managing practice tests. It allows viewing a list of tests, editing test names, and deleting tests across different certification categories.
    *   **`ToolsTab.js`**: Admin tab providing a dashboard of quick links to various external tools and services used for application development, marketing, infrastructure management, and social media.
    *   **`UsersTab.js`**: Admin tab for user management. It allows searching, viewing user details, editing user data (username, coins, level, subscription status), resetting passwords, and deleting user accounts with a two-step confirmation process.
*   **`CrackedAdminDashboard.js`**: The main component for the admin dashboard. It handles navigation between different admin tabs (e.g., Overview, Users, Tests) and provides the overall layout and structure for administrative tasks.
*   **`CrackedAdminLoginPage.js`**: Provides the login interface specifically for administrators. It supports key-based login, Google OAuth, handles error display, and integrates CSRF token management for secure authentication.
*   **`csrfHelper.js`**: A utility module for handling CSRF (Cross-Site Request Forgery) protection. It provides functions to get and set CSRF tokens, and a wrapped `fetch` function (`adminFetch`) that automatically includes the CSRF token in headers for secure admin API requests.

##### `css/` - General Component CSS

*   **`footer.css`**: Defines the styling for the site-wide footer component, including link appearance and copyright text.
*   **`QuestionLimitBanner.css`**: Styles the banner displayed to free users, indicating their remaining practice question limit. It includes progress bar styling and an upgrade button.
*   **`test.css`**: A comprehensive CSS file that styles the global test-taking interface. It covers test lists, question display, option buttons, progress bars, result overlays, and various interactive elements within the test environment.
*   **`UpgradePrompt.css`**: Styles the modal that appears to prompt users to upgrade to a premium subscription when they attempt to access features or content restricted to premium users.

##### `GlobalTest/`

*   **`GlobalTestList.js`**: A reusable component for displaying a list of practice tests for a specific certification category. It fetches and displays user attempt data, manages test lengths, and handles navigation to individual tests.
*   **`GlobalTestPage.js`**: The core component for rendering and managing a practice test session. It handles question display (including shuffling), answer submission, scoring, progress tracking, review mode, exam mode functionality, and integrates with user data like XP and coins.

##### `pages/` - Application Pages

*   **`AchievementPage/`**:
    *   `assets/AchievementPage.css`: Styles for the Achievement Gallery page, including the header, filter controls, and the visual presentation of individual achievement cards.
    *   `assets/AchievementToast.css`: CSS for the toast notifications that appear when a user unlocks an achievement, ensuring they match the site's theme.
    *   `assets/AchievementToast.js`: A utility function to display styled toast notifications for newly unlocked achievements, incorporating the achievement's icon, title, and description.
    *   `AchievementPage.js`: Displays all available achievements and indicates which ones the user has unlocked. It includes functionality for filtering achievements by category and sorting them.
*   **`AnalogyPage/`**:
    *   `assets/AnalogyHub.css`: Styles for the Analogy Hub page, defining the appearance of input fields for concepts, selection dropdowns for analogy type and category, and the output area for the generated analogy.
    *   `AnalogyHub.js`: An interactive tool page where users can input concepts and select an analogy type (single, comparison, triple) and category (e.g., real-world, video games) to generate analogies, streaming results from the backend.
*   **`auth/`**: Contains components related to user authentication.
    *   `css/`: CSS files for styling individual authentication forms and elements.
        *   `CreateUsernameForm.css`: Styles the form where new OAuth users choose their initial username, including input fields and visual feedback.
        *   `ErrorDisplay.css`: Styles for a component that displays authentication-related error messages to the user.
        *   `ForgotPassword.css`: Styles for the "Forgot Password" page, including the email input field and submission button.
        *   `Login.css`: Styles the user login page, covering input fields, login buttons, and social login options.
        *   `PasswordRequirements.css`: Styles the component that dynamically displays password strength requirements and their validation status.
        *   `Register.css`: Styles the user registration page, including form inputs, password requirements display, and terms agreement checkbox.
        *   `ResetPassword.css`: Styles for the "Reset Password" page, where users enter and confirm their new password.
    *   `CreateUsernameForm.js`: A form specifically for new users, typically redirected here after OAuth signup, to create their unique username. It includes client-side validation and communicates with the backend to set the username.
    *   `ErrorDisplay.js`: A simple reusable component designed to display a list of error messages, typically used within authentication forms to provide user feedback.
    *   `ForgotPassword.js`: Provides a page where users who have forgotten their password can request a reset link by submitting their email address.
    *   `Login.js`: Handles user login functionality using username/email and password, or through social OAuth providers like Google and Apple. It interacts with the Redux store to manage user authentication state and token storage.
    *   `OAuthSuccess.js`: Component that handles the redirect after a successful OAuth login (e.g., Google, Apple). It verifies the user, fetches necessary data, and navigates them to the appropriate next step, such as creating a username or accessing their profile.
    *   `PasswordRequirements.js`: A UI component that displays password complexity requirements (length, character types) and visually indicates whether the entered password meets each criterion.
    *   `Register.js`: Allows new users to create an account by providing a username, email, and password. It includes password strength validation, terms and conditions agreement, and then navigates to the subscription page.
    *   `ResetPassword.js`: Page where users can set a new password after clicking a password reset link (typically received via email) and verifying the associated token.
*   **`common/`**: Shared UI components used across various pages.
    *   `common.css`: Contains shared CSS for common utility components, likely including styles for loading spinners and error messages if not overridden elsewhere.
    *   `ErrorMessage.js`: A reusable component for displaying error messages in a consistent style, often with an optional dismiss button.
    *   `LoadingSpinner.js`: A reusable component to display a visual loading indicator, typically a spinner animation, with an optional message.
*   **`DailyPage/`**:
    *   `assets/DailyCyberBrief.css`: Styles for the Daily Cyber Brief newsletter subscription page, including the header, feature display, and the email subscription form.
    *   `DailyCyberBrief.js`: A page where users can subscribe to or unsubscribe from the "Daily Cyber Brief" newsletter, which provides daily cybersecurity intelligence.
*   **`DailyStation/`**:
    *   `assets/DailyStation.css`: Styles the Daily Station page, defining the appearance of the daily bonus claim section and the daily question/challenge interface, including result displays and countdown timers.
    *   `assets/SupportAskAnythingPage.css`: Styles for the "Ask Anything" support chat interface. (Note: This seems to be a duplicate path and likely belongs in `SupportPage/assets/`)
    *   `DailyStationPage.js`: Presents users with a daily bonus (coins) to claim and a daily challenge question to answer. It manages claim timers, question submission logic (premium feature), and displays results and explanations.
*   **`games/`**: Contains various interactive learning games.
    *   **`CipherChallenge/`**:
        *   `assets/css/`: Contains CSS files for the Cipher Challenge game.
            *   `CipherChallenge.css`: Main styles for the Cipher Challenge game layout, header, sidebar, and main content areas, ensuring a cohesive look.
            *   `CipherDisplay.css`: Styles for the component that displays the encrypted ciphertext. It includes specific formatting for different cipher types, like Morse code legends.
            *   `CipherHints.css`: Styles for the hint unlocking section, including the appearance of locked and unlocked hints, and the coin cost display.
            *   `CipherInfoModal.css`: Styles the modal that provides educational information about different cipher types, including tabs and content formatting.
            *   `CipherInput.css`: Styles the user input area for submitting deciphered solutions and the feedback messages.
            *   `CipherTools.css`: Styles the cipher analysis tools sidebar, including buttons for selecting tools and the display area for tool output.
            *   `CongratulationsModal.css`: Styles the modal displayed upon completing a level in the Cipher Challenge, including trophy icons and reward displays.
            *   `LevelSelector.css`: Styles the interface for selecting levels and specific challenges within the game, indicating locked/unlocked status and completion progress.
        *   `assets/CipherDisplay.js`: A component responsible for displaying the encrypted message (ciphertext). It can format the text based on the cipher type (e.g., grouping binary, showing Morse code) and handle symbolic ciphers as images.
        *   `assets/CipherHints.js`: Manages and displays hints for the current cipher challenge. Users can unlock hints using in-game coins, and this component handles the unlocking logic and UI.
        *   `assets/CipherInfoModal.js`: A modal component that provides detailed educational information about various cipher types (e.g., Caesar, Atbash). It uses tabs for navigation and explains the history, mechanics, and provides examples for each cipher.
        *   `assets/CipherInput.js`: Provides the text area where users can input their deciphered solution for the current cipher challenge and submit it for validation.
        *   `assets/CipherTools.js`: A sidebar component offering various cipher analysis tools like frequency analysis, Caesar shift utilities, and binary/hex decoders to assist users in decoding messages.
        *   `assets/CongratulationsModal.js`: A modal component displayed when a user successfully completes all challenges in a Cipher Challenge level. It shows rewards earned (XP, coins) and announces the unlocking of the next level.
        *   `assets/LevelSelector.js`: Component that allows users to select different levels and specific challenges within the Cipher Challenge game. It visually indicates locked/unlocked status and completion progress for each level and challenge.
        *   `CipherChallenge.js`: The main orchestrator for the Cipher Challenge game. It manages game state, challenge progression, user solutions, hints, and integrates all sub-components (display, input, tools, modals) to provide the complete game experience.
    *   **`IncidentResponder/`**:
        *   `assets/css/`: CSS for the Incident Responder game.
            *   `GameInstructions.css`: Styles for the modal that displays detailed instructions on how to play the Incident Responder game.
            *   `IncidentResponder.css`: Main CSS file for the Incident Responder game, defining theme variables, layout for scenario selection, stage display, action choices, and results modals.
        *   `assets/DifficultySelector.js`: A UI component that allows players to choose the difficulty level (e.g., Easy, Medium, Hard) for Incident Responder scenarios, affecting game parameters like time limits.
        *   `assets/GameInstructions.js`: A modal component providing detailed instructions on how to play the Incident Responder game. It covers the game overview, gameplay mechanics, scoring system, and objectives.
        *   `assets/ScenarioIntro.js`: Displays the introductory information for a selected Incident Responder scenario. This includes an overview of the incident, the player's role, specific objectives, and helpful tips before starting the game.
        *   `assets/ScenarioResults.js`: Presents the final results after a player completes an Incident Responder scenario. It shows the player's score, response rating, rewards earned (XP, coins), any achievements unlocked, and a timeline of actions taken.
        *   `assets/ScenarioStage.js`: Renders a single stage within an Incident Responder scenario. It displays the current situation, available actions for the player to choose, and provides feedback on the chosen action, including points awarded and explanations.
        *   `IncidentResponder.js`: The core component for the Incident Responder game. It manages the overall game flow, from scenario and difficulty selection through timed decision-making stages, to displaying the final results and player rewards.
    *   **`PhishingPhrenzy/`**:
        *   `assets/css/`: CSS for the Phishing Phrenzy game.
            *   `GameOverModal.css`: Styles the modal displayed at the end of a Phishing Phrenzy game, showing the player's score, high score, rating, and options to play again or return to the menu.
            *   `PhishingCard.css`: Provides base styling for the cards that display phishing examples. This file also contains responsive media queries applicable to all PhishingCard variants.
            *   `PhishingCard2.css` to `PhishingCard5.css`: These CSS files contain specific styles for different types of phishing example cards (e.g., documents, payment confirmations, tech support scams). Each file tailors the visual presentation for its respective card content, building upon `PhishingCard.css`.
            *   `PhishingPhrenzy.css`: Main styles for the Phishing Phrenzy game interface, including the header, game statistics (timer, score, streak), answer buttons, and feedback messages.
        *   `assets/cardTypeNames.js`: A JavaScript module that exports a mapping of internal phishing card type IDs (e.g., 'email', 'website') to their user-friendly display names (e.g., 'Email Message', 'Website').
        *   `assets/GameOverModal.js`: A modal component displayed when the Phishing Phrenzy game session ends. It shows the player's final score, their high score, a performance rating, a random phishing tip, and options to play again or return to the menu.
        *   `assets/PhishingCard.js`: A versatile component responsible for rendering different types of phishing examples (email, website, SMS, app download, QR code, social media post, etc.). It dynamically displays content based on the provided item data for the PhishingPhrenzy game.
        *   `PhishingPhrenzy.js`: The main game logic component for Phishing Phrenzy. It manages the game state (idle, playing, gameOver), fetches and displays phishing examples one by one, processes user answers (legitimate or phishing), and updates the score, timer, and streak accordingly.
    *   **`ThreatHunter/`**:
        *   `assets/css/`: CSS for the Threat Hunter game.
            *   `GameInstructions.css`: Styles for the modal that displays detailed instructions on how to play the Threat Hunter game, including game flow and scoring.
            *   `ThreatHunter.css`: Main CSS file for the Threat Hunter game. It defines theme variables and styles for the overall layout, log viewer, analysis tools panel, and results modal.
        *   `assets/AnalysisTools.js`: A component providing a panel for players to document detected threats during the Threat Hunter game. It allows users to select threat types from predefined options and add descriptions.
        *   `assets/GameInstructions.js`: A modal component providing detailed instructions on how to play the Threat Hunter game. It explains the game flow, use of tools, common threat types, and the scoring system.
        *   `assets/LogViewer.js`: A crucial component for displaying and interacting with log files in the Threat Hunter game. It supports tabbing between different logs, searching within logs, syntax highlighting for log entries, and allows users to flag suspicious lines.
        *   `assets/ScenarioSelector.js`: Allows players to select a Threat Hunter scenario based on threat type (e.g., malware, intrusion) and difficulty level (e.g., easy, medium, hard).
        *   `assets/ThreatControls.js`: Displays game status information such as the number of flagged lines and detected threats, along with the button to submit the analysis for scoring in the Threat Hunter game.
        *   `assets/ThreatResultsModal.js`: A modal component that displays the detailed results after a Threat Hunter scenario is completed. It shows the player's score, rating, correctly identified threats, missed threats, false positives, rewards earned, and any new achievements unlocked.
        *   `ThreatHunter.js`: The main component for the Threat Hunter game. It manages the game lifecycle from scenario selection, log display via `LogViewer`, threat analysis using `AnalysisTools`, to submission and display of results in `ThreatResultsModal`.
*   **`GRCpage/`**:
    *   `assets/GRC.css`: Styles for the GRC (Governance, Risk, and Compliance) Wizard page. It defines the appearance of parameter selection controls (dropdowns, sliders) and the display area for the generated GRC questions and their explanations.
    *   `GRC.js`: An interactive tool page, the "GRC Wizard," designed for learning about Governance, Risk, and Compliance. Users can select a GRC category (e.g., Regulation, Risk Management) and difficulty level to generate practice questions with detailed explanations.
*   **`ios/`**: iOS-specific legal pages.
    *   `assets/AppleLegalPages.css`: Specific CSS styling tailored for the display of legal documents (Privacy Policy, Terms of Service) when viewed within the iOS app's web view, ensuring a clean, readable, and native-like format.
    *   `PrivacyPolicyIOS.js`: Displays the Privacy Policy specifically formatted and intended for viewing within the iOS application environment.
    *   `TermsOfServiceIOS.js`: Displays the Terms of Service specifically formatted and intended for viewing within the iOS application environment.
*   **`LeaderboardPage/`**:
    *   `assets/LeaderboardPage.css`: Styles for the Leaderboard page, including the header, search/filter controls, the list of ranked players, and special styling for top-ranked users.
    *   `LeaderboardPage.js`: Fetches and displays the global leaderboard, showing player rankings based on XP. It includes features like searching for users, pagination (load more) to view more rankings, and highlighting for top players.
*   **`Legal/`**: General web legal pages.
    *   `assets/LegalPages.css`: Provides common styling for the web versions of legal documents like the Privacy Policy and Terms ofService. It ensures readability, a professional appearance, and includes a table of contents for easy navigation.
    *   `PrivacyPolicy.js`: Displays the website's Privacy Policy, detailing how user data is collected, used, stored, and protected, along with user rights regarding their data.
    *   `TermsOfService.js`: Displays the website's Terms of Service, outlining the rules, regulations, user responsibilities, and limitations of liability for using the platform.
*   **`Portfolio/`**:
    *   `assets/CodeEditor.js`: A React component that wraps the Monaco Editor, providing a rich code editing experience with syntax highlighting, auto-indentation, and error checking. It's used within the Portfolio feature for users to edit their generated portfolio code.
    *   `assets/DeploymentMonitor.js`: A component used to monitor the status of a portfolio deployment task. It polls the backend for updates and displays the progress or completion/failure states of the deployment.
    *   `assets/portfolio.css`: Contains all styling for the Portfolio Creator page. This includes styles for the multi-step form, template and color scheme selection cards, code editor interface, live preview area, and deployment sections.
    *   `assets/PortfolioDeployment.js`: Manages the deployment of a user's generated portfolio to Vercel. It requires GitHub and Vercel tokens for authorization, guides the user through the deployment process, and displays success or error messages.
    *   `assets/PortfolioForm.js`: A multi-step form component that guides users through the creation of their professional portfolio. Steps include template selection, color scheme choice, feature selection (e.g., projects, skills), and resume content input with basic analysis.
    *   `assets/PortfolioList.js`: Displays a list of the user's previously created and saved portfolios. It allows users to select a portfolio for editing/viewing, delete portfolios, and includes search and sorting functionalities.
    *   `assets/PortfolioPreview.js`: Allows users to preview the code of their generated portfolio and make edits. It features a file explorer to navigate through project files and a code editor (`CodeEditor.js`) for modifications, along with error display and auto-fix suggestions.
    *   `PortfolioPage.js`: The main page for the Portfolio Creator feature. It orchestrates the different views (create new, list existing, preview/edit, deploy) and manages the overall state and data flow for portfolio generation and deployment.
*   **`ResourcesPage/`**:
    *   `assets/Resources.css`: Styles for the Resources Hub page, including the header, search and filter controls, and the layout for displaying resource items in grid or list view.
    *   `Resources.js`: A curated hub providing users with a collection of cybersecurity learning resources. It includes links to tools, articles, videos, courses, and official documentation, categorized and searchable for easy access.
*   **`ScenarioPage/`**:
    *   `assets/attacks.js`: A JavaScript module that exports a large, predefined array of attack type names. This list is likely used to populate dropdown menus or generate varied content within the Scenario Sphere tool.
    *   `assets/ScenarioSphere.css`: Styles for the Scenario Sphere page. This CSS defines the appearance of parameter selection controls (dropdowns, sliders) and the display area for the generated cybersecurity scenarios and their interactive questions.
    *   `ScenarioSphere.js`: An interactive tool page named "Scenario Sphere" that generates realistic cybersecurity scenarios. Users can select parameters like industry, attack type, and attacker skill level, and the tool produces a scenario narrative along with follow-up questions to test understanding.
*   **`ShopPage/`**:
    *   `assets/ShopPage.css`: Styles for the in-app Shop page. It defines the visual appearance of item cards for avatars and XP boosts, purchase buttons, user currency/level display, and tab navigation.
    *   `ShopPage.js`: Displays items available for purchase using in-game currency (coins), such as user avatars and XP boosts. It handles item filtering by type, sorting, purchase logic, and equipping avatars, interacting with the Redux store for user and shop data.
*   **`StatsPage/`**:
    *   `assets/StatsPage.css`: Styles for the user's Performance Dashboard page. This includes styling for summary cards, various chart containers (line, bar, radar), detailed statistical breakdowns, and certification readiness meters.
    *   `StatsPage.js`: Presents a comprehensive overview of the user's performance statistics. It includes test scores, category performance, certification readiness assessments, leaderboard rank history, and various charts for visual data representation.
*   **`store/`**: Redux store configuration and state slices.
    *   `slice/achievementsSlice.js`: Redux slice responsible for managing the state of all available achievements in the application. It includes an async thunk to fetch the list of achievements from the backend.
    *   `slice/cipherChallengeSlice.js`: Redux slice that manages the state for the Cipher Challenge game. This includes the list of challenges, user progress, completed challenges, unlocked hints, and handles API interactions for submitting solutions and unlocking hints.
    *   `slice/incidentResponderSlice.js`: Redux slice for managing the Incident Responder game state. It handles scenarios, current game progress, selected actions, score, results, and bookmarking of scenarios, interacting with the backend for game data.
    *   `slice/phishingPhrenzySlice.js`: Redux slice that manages the state for the Phishing Phrenzy game. It includes fetching and shuffling phishing examples, tracking game status (idle, playing, finished), score, high score, and communicating with the backend to submit results and award XP/coins.
    *   `slice/shopSlice.js`: Redux slice for managing the state of shop items. Its primary responsibility is to fetch the list of available items (avatars, boosts) from the backend for display in the shop.
    *   `slice/threatHunterSlice.js`: Redux slice for managing the Threat Hunter game state. This includes fetching log scenarios, tracking the current game progress, handling analysis submission, and storing game results.
    *   `slice/userSlice.js` (Highly Important): The core Redux slice for managing all user-specific data and authentication state. It handles user registration, login (including JWT and refresh tokens), fetching and updating profile information (XP, coins, level, avatar), tracking achievements, purchased items, subscription status, and freemium usage limits. It also includes logic for daily bonuses and password changes.
    *   `store.js` (Highly Important): Configures the main Redux store for the application. It combines all the different state slices (user, achievements, games, shop, etc.) into a single, centralized global state manager using `configureStore` from Redux Toolkit.
*   **`subscription/`**: Components for managing user subscriptions.
    *   `css/`: CSS files for styling subscription-related pages.
        *   `StripeCheckout.css`: Styles the loading page displayed to the user while they are being redirected to Stripe's secure payment platform.
        *   `SubscriptionCancel.css`: Styles the page shown when a user cancels the subscription process or if the payment fails, guiding them on next steps.
        *   `SubscriptionPage.css`: Styles the main subscription page where users can view different plans (Free, Premium), compare features, and choose to subscribe.
        *   `SubscriptionSuccess.css`: Styles the confirmation page displayed after a user successfully subscribes or completes a new free account registration.
    *   `StripeCheckout.js`: Handles the initiation of a Stripe checkout session. It makes a backend request to create a session and then redirects the user to Stripe's secure payment page to complete the transaction.
    *   `SubscriptionCancel.js`: A page displayed if a user cancels the Stripe checkout process or if there's an issue with the payment. It informs the user that no charge was made and provides options to try again or go back.
    *   `SubscriptionPage.js`: Displays available subscription plans (e.g., Free and Premium) with their respective features and pricing. It handles new user registration data (if applicable) and initiates the Stripe checkout process when a user chooses to subscribe to a premium plan.
    *   `SubscriptionSuccess.js`: A confirmation page shown after a user successfully completes a subscription payment or a new free account registration. It verifies the session status and guides the user on the next steps, such as proceeding to their profile.
*   **`SupportPage/`**:
    *   `assets/SupportAskAnythingPage.css`: Styles the "Ask Anything" support chat interface. This includes styling for the list of support threads, individual message bubbles for user and admin, and the message input area.
    *   `SupportAskAnythingPage.js`: Provides a real-time chat interface for users to create support threads and communicate with administrators. It uses Socket.IO for live messaging and displays existing conversations.
*   **`tests/`**: Contains components for various certification practice tests. Each sub-directory typically includes a `TestList.js` and `TestPage.js`.
    *   **General `TestList.js` (e.g., `aplus/APlusTestList.js`)**: A component that utilizes the `GlobalTestList.js` to display a list of practice tests specifically tailored for its respective certification category (e.g., A+ Core 1).
    *   **General `TestPage.js` (e.g., `aplus/APlusTestPage.js`)**: Acts as a router for its specific certification (e.g., A+ Core 1). If a `testId` is present in the URL, it renders the `GlobalTestPage.js` component for that particular test; otherwise, it displays the corresponding `TestList.js` component.
        *   `aplus/APlusTestList.js`, `aplus/APlusTestPage.js`: For CompTIA A+ Core 1 (1101) tests.
        *   `aplus2/AplusCore2TestList.js`, `aplus2/APlusCore2TestPage.js`: For CompTIA A+ Core 2 (1102) tests.
        *   `awscloud/AWSCloudTestList.js`, `awscloud/AWSCloudTestPage.js`: For AWS Cloud Practitioner (CLE-C02) tests.
        *   `casp/CaspPlusTestList.js`, `casp/CaspPlusTestPage.js`: For CompTIA Security-X (CAS-005) / CASP+ tests.
        *   `cissp/CisspTestList.js`, `cissp/CisspTestPage.js`: For (ISC)² CISSP tests.
        *   `cloudplus/CloudPlusTestList.js`, `cloudplus/CloudPlusTestPage.js`: For CompTIA Cloud+ (CV0-004) tests.
        *   `cysa/CySAPlusTestList.js`, `cysa/CySAPlusTestPage.js`: For CompTIA CySA+ (CS0-003) tests.
        *   `dataplus/DataPlusTestList.js`, `dataplus/DataPlusTestPage.js`: For CompTIA Data+ (DA0-001) tests.
        *   `linuxplus/LinuxPlusTestList.js`, `linuxplus/LinuxPlusTestPage.js`: For CompTIA Linux+ (XK0-005) tests.
        *   `nplus/NPlusTestList.js`, `nplus/NetworkPlusTestPage.js`: For CompTIA Network+ (N10-009) tests.
        *   `penplus/PenPlusTestList.js`, `penplus/PenPlusTestPage.js`: For CompTIA PenTest+ (PT0-003) tests.
        *   `secplus/SecurityPlusTestList.js`, `secplus/SecurityPlusTestPage.js`: For CompTIA Security+ (SY0-701) tests.
        *   `serverplus/ServerPlusTestList.js`, `serverplus/ServerPlusTestPage.js`: For CompTIA Server+ (SK0-005) tests.
*   **`UserPage/`**:
    *   `assets/UserProfile.css`: Styles the User Profile page. This includes the header section (avatar, username, level, XP, coins), navigation tabs, and content areas for overview, achievements, items, and account settings.
    *   `UserProfile.js`: Displays the user's profile information, including stats (XP, level, coins), unlocked achievements, and purchased items. It also provides access to account settings where users can change their username, email, password, and theme preferences.
*   **`XploitcraftPage/`**:
    *   `assets/evasionTechniquesList.js`: A JavaScript module that exports a predefined array of strings, each representing an evasion technique example (e.g., "URL Encoding," "Base64 Encoding"). This list is used to populate options in the XploitCraft tool.
    *   `assets/vulnerabilitiesList.js`: A JavaScript module that exports a predefined array of strings, each representing a common cybersecurity vulnerability example (e.g., "SQL Injection," "XSS"). This list is used to populate options in the XploitCraft tool.
    *   `assets/Xploitcraft.css`: Styles for the XploitCraft page, defining the appearance of input fields for selecting vulnerabilities and evasion techniques, the generate button, and the output area where generated payloads and explanations are displayed.
    *   `Xploitcraft.js`: An interactive tool page named "XploitCraft." It allows users to select a vulnerability and an evasion technique to generate example payloads and detailed explanations of how they work, utilizing Socket.IO for streaming results.

##### `SEO/` - Search Engine Optimization

*   **`SEOHelmet.js`**: A reusable React component that utilizes `react-helmet` to dynamically manage document head tags. It allows setting page titles, meta descriptions, canonical URLs, and Open Graph tags for improved SEO and social sharing.
*   **`StructuredData.js`**: A component that uses `react-helmet` to inject JSON-LD (JavaScript Object Notation for Linked Data) structured data into the page head. This helps search engines better understand the content and context of web pages.

##### `Sidebar/` - Navigation Sidebar

*   **`assets/Sidebar.css`**: Styles for the application's main navigation sidebar. This includes styling for its collapsed and expanded states, links, icons, group headers, and sublists, ensuring a consistent look and feel across themes.
*   **`Sidebar.js`**: The main navigation sidebar component for the application. It provides links to various pages and features like profile, games, tools, and practice tests, with collapsible sections for better organization.

##### `utils/` - Utility Components & Functions

*   **`colorMapping.js`**: A JavaScript module that maps achievement IDs to specific color codes (hex values). This is likely used for dynamically styling achievement icons or related UI elements with unique colors.
*   **`Footer.js`**: A simple reusable React component that renders the site-wide footer. It typically includes links to home, privacy policy, terms of service, and copyright information.
*   **`FormattedQuestion.js`**: A utility component designed for rendering question text that may contain complex formatting. It handles Markdown-like syntax for code blocks (with syntax highlighting via `highlight.js`), inline code, tables, and ASCII diagrams, ensuring they are displayed correctly.
*   **`iconMapping.js`**: A JavaScript module that maps achievement IDs to corresponding React FontAwesome icons. This allows for visually representing different achievements with unique icons throughout the application.
*   **`ProtectedRoute.js`** (Highly Important): A higher-order component (HOC) or wrapper component used to protect routes that require user authentication and/or a premium subscription. It checks the user's login status and subscription level, redirecting unauthenticated users to the login page or showing an upgrade prompt if a premium feature is accessed without an active subscription.
*   **`QuestionLimitBanner.js`**: A banner component specifically displayed to free-tier users. It shows their remaining count of practice questions and includes a progress bar and a prompt to upgrade for unlimited access.
*   **`ScrollToTop.js`**: A utility component that automatically scrolls the window to the top whenever the route (URL path) changes. This ensures a consistent user experience, especially when navigating between long pages.
*   **`SubscriptionErrorHandler.js`**: A utility, likely a custom hook or a component providing context, designed to centralize the handling of API errors related to subscription status. It can display an `UpgradePrompt` when a premium feature is accessed by a non-premium user.
*   **`UpgradePrompt.js`** (Important): A modal component displayed to users when they attempt to access a premium feature without an active subscription, or when they've exhausted usage limits (e.g., free questions). It explains the benefits of upgrading and provides a button to navigate to the subscription page.

---

#### Root `src/` Files

*   **`api.js`**: Configures and exports an Axios instance for making API calls to the backend. It includes interceptors to automatically add JWT (JSON Web Tokens) to authorization headers and handle token refresh logic if an access token expires, ensuring seamless authenticated requests.
*   **`App.js`** (Very Important): The main application component. It sets up the overall page structure, including the `Sidebar` and `ToastContainer`, and defines all the client-side routing using `react-router-dom`. It also initializes global states like theme and fetches initial user data if a `userId` is present.
*   **`index.js`**: The entry point for the React application. It renders the root `App` component into the `div#root` element in `public/index.html` and wraps the `App` with the Redux `Provider` (to make the store available) and `BrowserRouter` (to enable routing).

### Root Project Files

*   **`.babelrc`**: Babel configuration file. It specifies presets (`@babel/preset-env` for modern JavaScript compatibility, `@babel/preset-react` for JSX) and plugins (`@emotion` for Emotion styling library support) used for transpiling JavaScript and JSX code.
*   **`.eslintignore`**: Specifies directories and files that ESLint (a code linter) should ignore during its analysis, such as `node_modules` and build artifacts.
*   **`.gitignore`**: Specifies intentionally untracked files and directories that Git (version control system) should ignore. This typically includes dependencies (`node_modules`), build outputs (`build`), and environment-specific files (`.env.local`).
*   **`craco.config.js`**: Configuration file for CRACO (Create React App Configuration Override). It's used here to customize the default Webpack configuration provided by Create React App, specifically to allow module imports from outside the `src/` directory.
*   **`eslint.config.mjs`**: ESLint configuration file using the newer ESM (ECMAScript Modules) format. It defines linting rules, plugins (like `eslint-plugin-react`), and recommended configurations to maintain code quality and consistency.
*   **`package.json`**: The heart of the Node.js project, defining project metadata (name, version), listing all dependencies (packages required for the app to run) and devDependencies (tools for development), and specifying scripts for common tasks like starting the development server (`start`), building the application (`build`), and running tests (`test`).
