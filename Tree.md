# Web App & IOS App Structure
---
# 5/19/2025
---
```ruby
.
├── README.MD
├── Stack
│   └── Architecture
│       ├── API
│       │   └── routes.md
│       ├── Trees
│       │   ├── Flask.md
│       │   ├── React.md
│       │   └── Root.md
│       └── diagrams
│           ├── AI-Integration.png
│           ├── Auth-flow.png
│           ├── Deployment.png
│           ├── Shared-Logic-Pattern.png
│           ├── Unit-Testing.png
│           └── api-architecture.png
├── backend
│   ├── AI_helpers
│   │   ├── __init__.py
│   │   ├── analogy_stream_helper.py
│   │   ├── grc_stream_helper.py
│   │   ├── scenario_helper.py
│   │   └── xploitcraft_helper.py
│   ├── Celery
│   │   ├── __init__.py
│   │   └── celery_app.py
│   ├── Clients
│   │   ├── Gemini.py
│   │   ├── OpenAI.py
│   │   └── __init__.py
│   ├── Dockerfile.dev
│   ├── Dockerfile.prod
│   ├── app.py
│   ├── models
│   │   ├── __init__.py
│   │   ├── newsletter.py
│   │   ├── password_reset.py
│   │   └── users.py
│   ├── mongodb
│   │   ├── __init__.py
│   │   └── database.py
│   ├── requirements.txt
│   ├── routes
│   │   ├── AI
│   │   │   ├── __init__.py
│   │   │   ├── analogy_routes.py
│   │   │   ├── gemini_routes.py
│   │   │   ├── grc_routes.py
│   │   │   ├── scenario_routes.py
│   │   │   └── xploit_routes.py
│   │   ├── Auth
│   │   │   ├── __init__.py
│   │   │   ├── oauth_routes.py
│   │   │   └── password_reset_routes.py
│   │   ├── Subscription
│   │   │   ├── __init__.py
│   │   │   └── subscription_routes.py
│   │   ├── __init__.py
│   │   ├── games
│   │   │   ├── __init__.py
│   │   │   ├── cipher_routes.py
│   │   │   ├── incident_routes.py
│   │   │   ├── phishing_routes.py
│   │   │   └── threat_hunter_routes.py
│   │   ├── info
│   │   │   ├── __init__.py
│   │   │   └── contact_form.py
│   │   └── main
│   │       ├── __init__.py
│   │       ├── achievements_routes.py
│   │       ├── blueprint.py
│   │       ├── daily_question_routes.py
│   │       ├── flashcard_routes.py
│   │       ├── leaderboard_routes.py
│   │       ├── newsletter_routes.py
│   │       ├── shop_routes.py
│   │       ├── support_routes.py
│   │       ├── test_attempt_routes.py
│   │       ├── test_routes.py
│   │       ├── unlock.py
│   │       └── user_routes.py
│   ├── security
│   │   ├── __init__.py
│   │   ├── admin
│   │   │   ├── __init__.py
│   │   │   ├── admin_newsletter_routes.py
│   │   │   └── admin_routes.py
│   │   ├── geoip_db
│   │   ├── helpers
│   │   │   ├── __init__.py
│   │   │   └── unhackable.py
│   │   ├── honeypot
│   │   │   ├── C2
│   │   │   │   ├── __init__.py
│   │   │   │   ├── c2_routes.py
│   │   │   │   └── payloads
│   │   │   │       └── security-diagnostic.js
│   │   │   ├── __init__.py
│   │   │   ├── helpers
│   │   │   │   ├── __init__.py
│   │   │   │   ├── geo_db_updater.py
│   │   │   │   └── proxy_detector.py
│   │   │   ├── honeypot.py
│   │   │   ├── honeypot_pages.py
│   │   │   ├── honeypot_routes.py
│   │   │   └── templates
│   │   │       ├── honeypot
│   │   │       │   ├── admin-dashboard.html
│   │   │       │   ├── admin-login.html
│   │   │       │   ├── cloud-dashboard.html
│   │   │       │   ├── cms-dashboard.html
│   │   │       │   ├── cpanel-dashboard.html
│   │   │       │   ├── database-dashboard.html
│   │   │       │   ├── debug-console.html
│   │   │       │   ├── devops-dashboard.html
│   │   │       │   ├── ecommerce-dashboard.html
│   │   │       │   ├── filesharing-dashboard.html
│   │   │       │   ├── forum-dashboard.html
│   │   │       │   ├── framework-dashboard.html
│   │   │       │   ├── generic-login.html
│   │   │       │   ├── generic-page.html
│   │   │       │   ├── iot-dashboard.html
│   │   │       │   ├── mail-dashboard.html
│   │   │       │   ├── mobile-api.html
│   │   │       │   ├── monitoring-dashboard.html
│   │   │       │   ├── phpmyadmin-dashboard.html
│   │   │       │   ├── remote-access-dashboard.html
│   │   │       │   ├── shell.html
│   │   │       │   └── wp-dashboard.html
│   │   │       └── redirection
│   │   │           ├── step1.html
│   │   │           ├── step10.html
│   │   │           ├── step11.html
│   │   │           ├── step12.html
│   │   │           ├── step13.html
│   │   │           ├── step14.html
│   │   │           ├── step15.html
│   │   │           ├── step2.html
│   │   │           ├── step3.html
│   │   │           ├── step4.html
│   │   │           ├── step5.html
│   │   │           ├── step6.html
│   │   │           ├── step7.html
│   │   │           ├── step8.html
│   │   │           └── step9.html
│   │   ├── middleware
│   │   │   ├── __init__.py
│   │   │   ├── csrf_protection.py
│   │   │   ├── jwt_auth.py
│   │   │   └── subscription_check.py
│   │   ├── proxy_cache
│   │   │   ├── proxies.json
│   │   │   └── tor_nodes.json
│   │   └── rate_limiters
│   │       ├── __init__.py
│   │       ├── ai_guard.py
│   │       ├── ai_utils.py
│   │       ├── global_rate_limiter.py
│   │       └── rate_limiter.py
│   ├── tasks
│   │   ├── __init__.py
│   │   ├── async_tasks.py
│   │   └── cleanup_tokens.py
│   ├── utils
│   │   ├── __init__.py
│   │   ├── apple_iap_verification.py
│   │   ├── deployment_service.py
│   │   └── email_sender.py
│   └── uwsgi.ini
├── docker-compose.yml
├── docker-compose.yml.dev
├── frontend
│   └── my-react-app
│       ├── craco.config.js
│       ├── eslint.config.mjs
│       ├── ops
│       │   ├── Dockerfile.audit
│       │   ├── Dockerfile.dev
│       │   └── Dockerfile.prod
│       ├── package-lock.json
│       ├── package.json
│       ├── public
│       │   ├── assets
│       │   │   ├── android-chrome-192x192.png
│       │   │   ├── android-chrome-512x512.png
│       │   │   ├── apple-touch-icon.png
│       │   │   ├── favicon-16x16.png
│       │   │   ├── favicon-32x32.png
│       │   │   ├── favicon.ico
│       │   │   ├── ios.png
│       │   │   └── manifest.json
│       │   ├── index.html
│       │   ├── robots.txt
│       │   ├── sitemap.xml
│       │   └── xp
│       │       ├── xp10.png
│       │       ├── xp100.png
│       │       ├── xp200.png
│       │       ├── xp25.png
│       │       └── xp50.png
│       └── src
│           ├── App.js
│           ├── AppSupport
│           │   ├── global.css
│           │   └── reportWebVitals.js
│           ├── api.js
│           ├── components
│           │   ├── GlobalTest
│           │   │   ├── GlobalTestList.js
│           │   │   └── GlobalTestPage.js
│           │   ├── SEO
│           │   │   ├── SEOHelmet.js
│           │   │   ├── StructuredData.js
│           │   │   └── og-default.jpg
│           │   ├── Sidebar
│           │   │   ├── Sidebar.js
│           │   │   └── assets
│           │   │       ├── Sidebar.css
│           │   │       └── sidebarlogo.png
│           │   ├── cracked
│           │   │   ├── CrackedAdminDashboard.js
│           │   │   ├── CrackedAdminLoginPage.js
│           │   │   ├── csrfHelper.js
│           │   │   ├── modals
│           │   │   │   ├── ConfirmModal.css
│           │   │   │   └── ConfirmModal.js
│           │   │   ├── styles
│           │   │   │   ├── CrackedAdminDashboard.css
│           │   │   │   ├── CrackedAdminLogin.css
│           │   │   │   └── tabstyles
│           │   │   │       ├── ActivityLogsTab.css
│           │   │   │       ├── C2Tab.css
│           │   │   │       ├── CredentialsTab.css
│           │   │   │       ├── DailyTab.css
│           │   │   │       ├── DbShellTab.css
│           │   │   │       ├── HealthCheckTab.css
│           │   │   │       ├── HoneypotTab.css
│           │   │   │       ├── HtmlInteractionsTab.css
│           │   │   │       ├── LogIp.css
│           │   │   │       ├── NewsletterTab.css
│           │   │   │       ├── OverviewTab.css
│           │   │   │       ├── PerformanceTab.css
│           │   │   │       ├── RateLimitsTab.css
│           │   │   │       ├── RequestLogsTab.css
│           │   │   │       ├── RevenueTab.css
│           │   │   │       ├── ServerMetricsTab.css
│           │   │   │       ├── SupportTab.css
│           │   │   │       ├── TestsTab.css
│           │   │   │       ├── ToolsTab.css
│           │   │   │       └── UsersTab.css
│           │   │   └── tabs
│           │   │       ├── ActivityLogsTab.js
│           │   │       ├── C2Tab.js
│           │   │       ├── CredentialsTab.js
│           │   │       ├── DailyTab.js
│           │   │       ├── DbShellTab.js
│           │   │       ├── HealthChecksTab.js
│           │   │       ├── HoneypotTab.js
│           │   │       ├── HtmlInteractionsTab.js
│           │   │       ├── LogIp.js
│           │   │       ├── NewsletterTab.js
│           │   │       ├── OverviewTab.js
│           │   │       ├── PerformanceTab.js
│           │   │       ├── RateLimitsTab.js
│           │   │       ├── RequestLogsTab.js
│           │   │       ├── RevenueTab.js
│           │   │       ├── ServerMetricsTab.js
│           │   │       ├── SupportTab.js
│           │   │       ├── TestsTab.js
│           │   │       ├── ToolsTab.js
│           │   │       └── UsersTab.js
│           │   ├── css
│           │   │   ├── QuestionLimitBanner.css
│           │   │   ├── UpgradePrompt.css
│           │   │   ├── footer.css
│           │   │   └── test.css
│           │   ├── pages
│           │   │   ├── AchievementPage
│           │   │   │   ├── AchievementPage.js
│           │   │   │   └── assets
│           │   │   │       ├── AchievementPage.css
│           │   │   │       ├── AchievementToast.css
│           │   │   │       └── AchievementToast.js
│           │   │   ├── AnalogyPage
│           │   │   │   ├── AnalogyHub.js
│           │   │   │   └── assets
│           │   │   │       ├── AnalogyHub.css
│           │   │   │       ├── backround1.jpg
│           │   │   │       └── loading2.png
│           │   │   ├── DailyPage
│           │   │   │   ├── DailyCyberBrief.js
│           │   │   │   └── assets
│           │   │   │       └── DailyCyberBrief.css
│           │   │   ├── DailyStation
│           │   │   │   ├── DailyStationPage.js
│           │   │   │   └── assets
│           │   │   │       ├── DailyStation.css
│           │   │   │       └── SupportAskAnythingPage.css
│           │   │   ├── GRCpage
│           │   │   │   ├── GRC.js
│           │   │   │   └── assets
│           │   │   │       └── GRC.css
│           │   │   ├── Info
│           │   │   │   ├── BlogPage.js
│           │   │   │   ├── BlogPostPage.js
│           │   │   │   ├── ContactPage.js
│           │   │   │   ├── DemosPage.js
│           │   │   │   ├── ExamsPage.js
│           │   │   │   ├── InfoPage.js
│           │   │   │   ├── PublicLeaderboardPage.js
│           │   │   │   ├── components
│           │   │   │   │   ├── InfoNavbar.js
│           │   │   │   │   ├── YouTubeEmbed.js
│           │   │   │   │   ├── navbarScrollUtils.js
│           │   │   │   │   └── videoConfig.js
│           │   │   │   ├── css
│           │   │   │   │   ├── BlogPage.css
│           │   │   │   │   ├── ContactPage.css
│           │   │   │   │   ├── DemosPage.css
│           │   │   │   │   ├── ExamsPage.css
│           │   │   │   │   ├── InfoNavbar.css
│           │   │   │   │   ├── InfoPage.css
│           │   │   │   │   └── PublicLeaderboardPage.css
│           │   │   ├── LeaderboardPage
│           │   │   │   ├── LeaderboardPage.js
│           │   │   │   └── assets
│           │   │   │       └── LeaderboardPage.css
│           │   │   ├── Legal
│           │   │   │   ├── PrivacyPolicy.js
│           │   │   │   ├── TermsOfService.js
│           │   │   │   └── assets
│           │   │   │       └── LegalPages.css
│           │   │   ├── Portfolio
│           │   │   │   ├── PortfolioPage.js
│           │   │   │   └── assets
│           │   │   │       ├── CodeEditor.js
│           │   │   │       ├── DeploymentMonitor.js
│           │   │   │       ├── PortfolioDeployment.js
│           │   │   │       ├── PortfolioForm.js
│           │   │   │       ├── PortfolioList.js
│           │   │   │       ├── PortfolioPreview.js
│           │   │   │       └── portfolio.css
│           │   │   ├── ResourcesPage
│           │   │   │   ├── Resources.js
│           │   │   │   └── assets
│           │   │   │       └── Resources.css
│           │   │   ├── ScenarioPage
│           │   │   │   ├── ScenarioSphere.js
│           │   │   │   └── assets
│           │   │   │       ├── ScenarioSphere.css
│           │   │   │       └── attacks.js
│           │   │   ├── ShopPage
│           │   │   │   ├── ShopPage.js
│           │   │   │   └── assets
│           │   │   │       ├── ShopPage.css
│           │   │   │       └── SupportAskAnythingPage.css
│           │   │   ├── StatsPage
│           │   │   │   ├── StatsPage.js
│           │   │   │   └── assets
│           │   │   │       └── StatsPage.css
│           │   │   ├── SupportPage
│           │   │   │   ├── SupportAskAnythingPage.js
│           │   │   │   └── assets
│           │   │   │       └── SupportAskAnythingPage.css
│           │   │   ├── UserPage
│           │   │   │   ├── UserProfile.js
│           │   │   │   └── assets
│           │   │   │       └── UserProfile.css
│           │   │   ├── XploitcraftPage
│           │   │   │   ├── Xploitcraft.js
│           │   │   │   └── assets
│           │   │   │       ├── Xploitcraft.css
│           │   │   │       ├── backround2.jpg
│           │   │   │       ├── evasionTechniquesList.js
│           │   │   │       ├── loading3.png
│           │   │   │       ├── logo5.png
│           │   │   │       └── vulnerabilitiesList.js
│           │   │   ├── auth
│           │   │   │   ├── CreateUsernameForm.js
│           │   │   │   ├── ErrorDisplay.js
│           │   │   │   ├── ForgotPassword.js
│           │   │   │   ├── Login.js
│           │   │   │   ├── OAuthSuccess.js
│           │   │   │   ├── PasswordRequirements.js
│           │   │   │   ├── Register.js
│           │   │   │   ├── ResetPassword.js
│           │   │   │   └── css
│           │   │   │       ├── CreateUsernameForm.css
│           │   │   │       ├── ErrorDisplay.css
│           │   │   │       ├── ForgotPassword.css
│           │   │   │       ├── Login.css
│           │   │   │       ├── PasswordRequirements.css
│           │   │   │       ├── Register.css
│           │   │   │       └── ResetPassword.css
│           │   │   ├── common
│           │   │   │   ├── ErrorMessage.js
│           │   │   │   ├── LoadingSpinner.js
│           │   │   │   └── common.css
│           │   │   ├── games
│           │   │   │   ├── CipherChallenge
│           │   │   │   │   ├── CipherChallenge.js
│           │   │   │   │   └── assets
│           │   │   │   │       ├── CipherDisplay.js
│           │   │   │   │       ├── CipherHints.js
│           │   │   │   │       ├── CipherInfoModal.js
│           │   │   │   │       ├── CipherInput.js
│           │   │   │   │       ├── CipherTools.js
│           │   │   │   │       ├── CongratulationsModal.js
│           │   │   │   │       ├── LevelSelector.js
│           │   │   │   │       └── css
│           │   │   │   │           ├── CipherChallenge.css
│           │   │   │   │           ├── CipherDisplay.css
│           │   │   │   │           ├── CipherHints.css
│           │   │   │   │           ├── CipherInfoModal.css
│           │   │   │   │           ├── CipherInput.css
│           │   │   │   │           ├── CipherTools.css
│           │   │   │   │           ├── CongratulationsModal.css
│           │   │   │   │           └── LevelSelector.css
│           │   │   │   ├── IncidentResponder
│           │   │   │   │   ├── IncidentResponder.js
│           │   │   │   │   └── assets
│           │   │   │   │       ├── DifficultySelector.js
│           │   │   │   │       ├── GameInstructions.js
│           │   │   │   │       ├── ScenarioIntro.js
│           │   │   │   │       ├── ScenarioResults.js
│           │   │   │   │       ├── ScenarioStage.js
│           │   │   │   │       ├── css
│           │   │   │   │       │   ├── GameInstructions.css
│           │   │   │   │       │   └── IncidentResponder.css
│           │   │   │   │       └── theme.mp3
│           │   │   │   ├── PhishingPhrenzy
│           │   │   │   │   ├── PhishingPhrenzy.js
│           │   │   │   │   └── assets
│           │   │   │   │       ├── GameOverModal.js
│           │   │   │   │       ├── PhishingCard.js
│           │   │   │   │       ├── cardTypeNames.js
│           │   │   │   │       └── css
│           │   │   │   │           ├── GameOverModal.css
│           │   │   │   │           ├── PhishingCard.css
│           │   │   │   │           ├── PhishingCard2.css
│           │   │   │   │           ├── PhishingCard3.css
│           │   │   │   │           ├── PhishingCard4.css
│           │   │   │   │           ├── PhishingCard5.css
│           │   │   │   │           └── PhishingPhrenzy.css
│           │   │   │   └── ThreatHunter
│           │   │   │       ├── ThreatHunter.js
│           │   │   │       └── assets
│           │   │   │           ├── AnalysisTools.js
│           │   │   │           ├── GameInstructions.js
│           │   │   │           ├── LogViewer.js
│           │   │   │           ├── ScenarioSelector.js
│           │   │   │           ├── ThreatControls.js
│           │   │   │           ├── ThreatResultsModal.js
│           │   │   │           └── css
│           │   │   │               ├── GameInstructions.css
│           │   │   │               └── ThreatHunter.css
│           │   │   ├── ios
│           │   │   │   ├── PrivacyPolicyIOS.js
│           │   │   │   ├── TermsOfServiceIOS.js
│           │   │   │   └── assets
│           │   │   │       └── AppleLegalPages.css
│           │   │   ├── store
│           │   │   │   ├── slice
│           │   │   │   │   ├── achievementsSlice.js
│           │   │   │   │   ├── cipherChallengeSlice.js
│           │   │   │   │   ├── incidentResponderSlice.js
│           │   │   │   │   ├── phishingPhrenzySlice.js
│           │   │   │   │   ├── shopSlice.js
│           │   │   │   │   ├── threatHunterSlice.js
│           │   │   │   │   └── userSlice.js
│           │   │   │   └── store.js
│           │   │   ├── subscription
│           │   │   │   ├── StripeCheckout.js
│           │   │   │   ├── SubscriptionCancel.js
│           │   │   │   ├── SubscriptionPage.js
│           │   │   │   ├── SubscriptionSuccess.js
│           │   │   │   └── css
│           │   │   │       ├── StripeCheckout.css
│           │   │   │       ├── SubscriptionCancel.css
│           │   │   │       ├── SubscriptionPage.css
│           │   │   │       └── SubscriptionSuccess.css
│           │   │   └── tests
│           │   │       ├── aplus
│           │   │       │   ├── APlusTestList.js
│           │   │       │   └── APlusTestPage.js
│           │   │       ├── aplus2
│           │   │       │   ├── APlusCore2TestPage.js
│           │   │       │   └── AplusCore2TestList.js
│           │   │       ├── awscloud
│           │   │       │   ├── AWSCloudTestList.js
│           │   │       │   └── AWSCloudTestPage.js
│           │   │       ├── casp
│           │   │       │   ├── CaspPlusTestList.js
│           │   │       │   └── CaspPlusTestPage.js
│           │   │       ├── cissp
│           │   │       │   ├── CisspTestList.js
│           │   │       │   └── CisspTestPage.js
│           │   │       ├── cloudplus
│           │   │       │   ├── CloudPlusTestList.js
│           │   │       │   └── CloudPlusTestPage.js
│           │   │       ├── cysa
│           │   │       │   ├── CySAPlusTestList.js
│           │   │       │   └── CySAPlusTestPage.js
│           │   │       ├── dataplus
│           │   │       │   ├── DataPlusTestList.js
│           │   │       │   └── DataPlusTestPage.js
│           │   │       ├── linuxplus
│           │   │       │   ├── LinuxPlusTestList.js
│           │   │       │   └── LinuxPlusTestPage.js
│           │   │       ├── nplus
│           │   │       │   ├── NPlusTestList.js
│           │   │       │   └── NetworkPlusTestPage.js
│           │   │       ├── penplus
│           │   │       │   ├── PenPlusTestList.js
│           │   │       │   └── PenPlusTestPage.js
│           │   │       ├── secplus
│           │   │       │   ├── SecurityPlusTestList.js
│           │   │       │   └── SecurityPlusTestPage.js
│           │   │       └── serverplus
│           │   │           ├── ServerPlusTestList.js
│           │   │           └── ServerPlusTestPage.js
│           │   └── utils
│           │       ├── Footer.js
│           │       ├── FormattedQuestion.js
│           │       ├── ProtectedRoute.js
│           │       ├── QuestionLimitBanner.js
│           │       ├── ScrollToTop.js
│           │       ├── SubscriptionErrorHandler.js
│           │       ├── UpgradePrompt.js
│           │       ├── colorMapping.js
│           │       └── iconMapping.js
│           └── index.js
├── nginx
│   ├── logs
│   │   ├── access.log
│   │   └── error.log
│   ├── nginx.conf
│   ├── sites-enabled
│   │   └── proxy.conf
│   └── sites-enabled-dev
│       └── proxy-dev.conf
└── redis
    └── redis.conf

133 directories, 519 files
```
# IOS APP STRUCTURE
```
.
├── CertGamesApp
│   ├── App.js
│   ├── app.json
│   ├── assets
│   │   ├── adaptive-icon.png
│   │   ├── apple-touch-icon.png
│   │   ├── default-avatar.png
│   │   ├── favicon.png
│   │   ├── fonts
│   │   │   ├── FiraCode-Regular.ttf
│   │   │   ├── Fira_Code
│   │   │   │   ├── OFL.txt
│   │   │   │   └── static
│   │   │   ├── Orbitron
│   │   │   │   └── OFL.txt
│   │   │   ├── Orbitron-Black.ttf
│   │   │   ├── Orbitron-Bold.ttf
│   │   │   ├── Orbitron-Medium.ttf
│   │   │   ├── Orbitron-Regular.ttf
│   │   │   ├── ShareTechMono-Regular.ttf
│   │   │   └── Share_Tech_Mono
│   │   │       └── OFL.txt
│   │   ├── icon.png
│   │   ├── logo.png
│   │   └── splash-icon.png
│   ├── babel.config.js
│   ├── eas.json
│   ├── index.js
│   ├── package-lock.json
│   ├── package.json
│   └── src
│       ├── api
│       │   ├── AppleSubscriptionService.js
│       │   ├── GoogleAuthService.js
│       │   ├── ResourcesService.js
│       │   ├── achievementService.js
│       │   ├── analogyService.js
│       │   ├── apiClient.js
│       │   ├── apiConfig.js
│       │   ├── authService.js
│       │   ├── contactService.js
│       │   ├── dailyStationService.js
│       │   ├── grcService.js
│       │   ├── leaderboardService.js
│       │   ├── newsletterService.js
│       │   ├── passwordResetService.js
│       │   ├── profileService.js
│       │   ├── scenarioService.js
│       │   ├── shopService.js
│       │   ├── supportService.js
│       │   ├── testService.js
│       │   └── xploitService.js
│       ├── components
│       │   ├── AchievementItem.js
│       │   ├── CustomHeaderComponent.js
│       │   ├── FormattedQuestion.js
│       │   ├── GlobalErrorHandler.js
│       │   ├── GradientCard.js
│       │   ├── NotificationOverlay.js
│       │   ├── PremiumFeaturePrompt.js
│       │   ├── PurchaseSuccessScreen.js
│       │   ├── QuestionLimitBanner.js
│       │   ├── ResourceItemComponent.js
│       │   ├── ResourcePremiumBanner.js
│       │   ├── ResourceRandomModal.js
│       │   ├── ResourcesCategoriesComponent.js
│       │   ├── TestProgressComponent.js
│       │   └── ThemeSelector.js
│       ├── constants
│       │   ├── achievementConstants.js
│       │   ├── resourcesConstants.js
│       │   ├── shop
│       │   │   └── shopConstants.js
│       │   ├── supportConstants.js
│       │   └── testConstants.js
│       ├── context
│       │   ├── NetworkContext.js
│       │   └── ThemeContext.js
│       ├── hooks
│       │   ├── useAchievements.js
│       │   ├── useLeaderboard.js
│       │   ├── usePremiumCheck.js
│       │   ├── useResources.js
│       │   ├── useShop.js
│       │   ├── useSupport.js
│       │   ├── useTest.js
│       │   ├── useUserData.js
│       │   └── useXpProgress.js
│       ├── navigation
│       │   ├── AppNavigator.js
│       │   ├── AuthNavigator.js
│       │   ├── MainNavigator.js
│       │   └── TestNavigator.js
│       ├── screens
│       │   ├── HomeScreen.js
│       │   ├── LeaderboardScreen.js
│       │   ├── auth
│       │   │   ├── CreateUsernameScreen.js
│       │   │   ├── ForgotPasswordScreen.js
│       │   │   ├── LoginScreen.js
│       │   │   ├── PrivacyPolicyScreen.js
│       │   │   ├── RegisterScreen.js
│       │   │   └── TermsScreen.js
│       │   ├── profile
│       │   │   ├── AchievementsScreen.js
│       │   │   ├── ProfileScreen.js
│       │   │   ├── SupportScreen.js
│       │   │   └── ThemeSettingsScreen.js
│       │   ├── shop
│       │   │   ├── ShopScreen.js
│       │   │   └── components
│       │   │       ├── AvatarItem.js
│       │   │       ├── BoostItem.js
│       │   │       └── ColorItem.js
│       │   ├── subscription
│       │   │   ├── SubscriptionScreenIOS.js
│       │   │   └── UpgradeSubscriptionScreen.js
│       │   ├── tests
│       │   │   ├── TestListScreen.js
│       │   │   ├── TestScreen.js
│       │   │   └── categories
│       │   │       ├── APlus2Screen.js
│       │   │       ├── APlusScreen.js
│       │   │       ├── AWSCloudScreen.js
│       │   │       ├── CaspPlusScreen.js
│       │   │       ├── CisspScreen.js
│       │   │       ├── CloudPlusScreen.js
│       │   │       ├── CySAPlusScreen.js
│       │   │       ├── DataPlusScreen.js
│       │   │       ├── LinuxPlusScreen.js
│       │   │       ├── NetworkPlusScreen.js
│       │   │       ├── PenPlusScreen.js
│       │   │       ├── SecurityPlusScreen.js
│       │   │       └── ServerPlusScreen.js
│       │   └── tools
│       │       ├── AnalogyHubScreen.js
│       │       ├── DailyStationScreen.js
│       │       ├── GRCScreen.js
│       │       ├── NewsletterScreen.js
│       │       ├── ResourcesScreen.js
│       │       ├── ScenarioSphereScreen.js
│       │       ├── XploitCraftScreen.js
│       │       ├── attackTypes.js
│       │       ├── xploit.js
│       │       └── xploits.js
│       ├── store
│       │   ├── index.js
│       │   └── slices
│       │       ├── achievementsSlice.js
│       │       ├── networkSlice.js
│       │       ├── shopSlice.js
│       │       └── userSlice.js
│       ├── styles
│       │   └── globalStyles.js
│       └── utils
│           ├── networkUtils.js
│           └── responsive.js
└── README.md

67 directories, 195 files                                           
```
