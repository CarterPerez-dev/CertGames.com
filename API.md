# ROUTES
---
## Main Application Routes (`/test` prefix)

1.  `GET /test/user/<user_id>` - Retrieves a user's profile information by their ID.
2.  `POST /test/user` - Registers a new user account. Expects username, email, password.
3.  `POST /test/login` - Handles user authentication and login. Expects username/email and password.
4.  `POST /test/token/refresh` - Refreshes JWT access token using a valid refresh token.
5.  `POST /test/logout` - Logs out the currently authenticated user by invalidating their JWT.
6.  `POST /test/user/<user_id>/add-xp` - Adds a specified amount of experience points (XP) to a user's account.
7.  `POST /test/user/<user_id>/add-coins` - Adds a specified amount of coins to a user's account.
8.  `GET /test/user/<user_id>/usage-limits` - Retrieves the current usage limits (e.g., remaining practice questions) for a free-tier user.
9.  `POST /test/user/<user_id>/decrement-questions` - Decrements the practice question counter for free-tier users.
10. `POST /test/user/change-username` - Allows an authenticated user to change their username.
11. `POST /test/user/change-email` - Allows an authenticated user to change their email address.
12. `POST /test/user/change-password` - Allows an authenticated user to change their password (requires old password).
13. `DELETE /test/user/<user_id>/delete` - Deletes a user account and associated data.

## Shop & Achievements Routes (`/test` prefix)

14. `GET /test/shop` - Retrieves a list of all available items from the in-game shop.
15. `POST /test/shop/purchase/<item_id>` - Processes the purchase of a shop item for a user.
16. `POST /test/shop/equip` - Allows a user to equip a purchased avatar item.
17. `GET /test/achievements` - Retrieves a list of all available achievements in the system.

## Test & Quiz Routes (`/test` prefix)

18. `GET /test/tests/<test_id>` - Fetches a specific test (quiz) by its numerical ID.
19. `GET /test/tests/<category>/<test_id>` - Fetches a specific test (quiz) by its category and numerical ID.
20. `GET /test/attempts/<user_id>/<test_id>` - Retrieves a user's ongoing or last completed test attempt for a specific test.
21. `POST /test/attempts/<user_id>/<test_id>` - Creates or updates a user's test attempt, saving progress.
22. `POST /test/attempts/<user_id>/<test_id>/finish` - Marks a user's test attempt as finished and processes final scores/awards.
23. `GET /test/attempts/<user_id>/list` - Lists all test attempts (paginated) for a given user.
24. `POST /test/user/<user_id>/submit-answer` - Submits an answer for a question during a practice test and awards XP/coins if correct (non-exam mode).
25. `POST /test/attempts/<user_id>/<test_id>/answer` - Updates a single answer within an existing test attempt.
26. `POST /test/attempts/<user_id>/<test_id>/position` - Updates the user's current question index in a test attempt.

## Daily Features Routes (`/test` prefix)

27. `POST /test/user/<user_id>/daily-bonus` - Allows a user to claim their daily login bonus (coins).
28. `GET /test/daily-question` - Retrieves the daily GRC question for the authenticated user.
29. `POST /test/daily-question/answer` - Submits an answer for the daily GRC question and awards coins.

## Leaderboard Routes

30. `GET /test/leaderboard` - Retrieves the main user leaderboard, paginated, showing top users by level/XP.
31. `GET /public-leaderboard/board` - Retrieves a public version of the leaderboard with a longer cache, suitable for marketing sites.

## Flashcard Routes (`/flashcard` prefix)

32. `GET /flashcard/categories` - Retrieves all flashcard categories (certification vaults).
33. `GET /flashcard/category/<category_id>` - Retrieves flashcards for a specific category, paginated.
34. `POST /flashcard/save` - Toggles saving/unsaving a flashcard to a user's favorites.
35. `GET /flashcard/saved/<user_id>` - Retrieves a user's saved (favorite) flashcards.
36. `POST /flashcard/record-progress` - Records user interaction with flashcards (viewed, answered, session completed) and awards XP/coins.
37. `GET /flashcard/stats/<user_id>` - Retrieves flashcard usage statistics for a user, including per-category progress.
38. `POST /flashcard/difficulty` - Allows a user to set a personal difficulty rating (easy, medium, hard) for a specific flashcard.
39. `GET /flashcard/difficulty/<user_id>` - Retrieves all flashcard difficulty ratings set by a user, optionally filtered by category.
40. `POST /flashcard/progress/<user_id>` - Saves the user's current progress (e.g., last viewed card index) for a flashcard category.
41. `GET /flashcard/progress/<user_id>` - Retrieves the user's saved progress for one or all flashcard categories.

## OAuth Routes (`/oauth` prefix)

42. `GET /oauth/login/google` - Initiates the Google OAuth login flow, redirecting the user to Google's authentication page.
43. `GET /oauth/auth/google` - Handles the callback from Google after user authentication, processes user data, and redirects.
44. `GET /oauth/login/apple` - Initiates the Sign in with Apple OAuth flow.
45. `POST /oauth/auth/apple` - Handles the callback from Apple after user authentication (via form post). (GET on this route redirects to `/oauth/login/apple`)
46. `POST /oauth/login/apple/mobile` - Handles Sign in with Apple specifically for mobile clients using an identity token.
47. `POST /oauth/verify-google-token` - Verifies a Google access token provided directly (e.g., from a mobile app).
48. `GET /oauth/admin-login/google` - Initiates a Google OAuth login flow specifically for the admin dashboard.
49. `GET /oauth/admin-auth/google` - Handles the callback for admin Google login, verifying admin authorization.
50. `GET /oauth/github` - Initiates GitHub OAuth flow to link a user's GitHub account.
51. `GET /oauth/github/callback` - Handles the callback from GitHub after authorization.
52. `GET /oauth/github/token` - Retrieves the stored GitHub OAuth token for the authenticated user.

## Password Reset Routes (`/password-reset` prefix)

53. `POST /password-reset/request-reset` - Initiates the password reset process by sending a reset link to the user's email.
54. `GET /password-reset/verify-token/<token>` - Verifies if a given password reset token is valid and not expired.
55. `POST /password-reset/reset-password` - Allows a user to reset their password using a valid token and a new password.

## AI Tool Routes

### Scenario Generator (`/scenario` prefix)
56. `POST /scenario/stream_scenario` - Generates a security scenario based on input parameters (industry, attack type, etc.) and streams the output text.
57. `POST /scenario/stream_questions` - Generates interactive questions based on a provided scenario text and streams the output JSON.

### GRC Question Generator (`/grc` prefix)
58. `POST /grc/stream_question` - Generates a GRC (Governance, Risk, Compliance) question based on category and difficulty, streaming the output JSON.

### XploitCraft Payload Generator (`/payload` prefix)
59. `POST /payload/generate_payload` - Generates conceptual exploit payload examples based on vulnerability/evasion technique, with streaming support.

### Analogy Generator (`/analogy` prefix)
60. `POST /analogy/stream_analogy` - Generates an analogy comparing cybersecurity concepts and streams the output text.

### Portfolio Generator (Gemini) (`/portfolio` prefix)
61. `POST /portfolio/generate-stream` - Initiates portfolio generation based on resume text and preferences, with progress updates handled separately.
62. `GET /portfolio/status/generation` - Checks the status of an ongoing or recently completed portfolio generation task for the user.
63. `POST /portfolio/fix-error` - Attempts to fix errors in a specific component of a generated portfolio.
64. `POST /portfolio/deploy` - Initiates the deployment of a generated portfolio to Vercel via GitHub.
65. `GET /portfolio/deploy/status/<task_id>` - Checks the status of a specific portfolio deployment task.
66. `GET /portfolio/list` - Lists all portfolios created by the authenticated user.
67. `GET /portfolio/<portfolio_id>` - Retrieves the details and components of a specific portfolio.
68. `POST /portfolio/create-file` - Creates a new file within a specified portfolio's components.
69. `POST /portfolio/update-file` - Updates the content of an existing file within a portfolio.
70. `POST /portfolio/delete-file` - Deletes a file from a specified portfolio.
71. `DELETE /portfolio/<portfolio_id>` - Deletes an entire portfolio and its associated data.

## Subscription Routes (`/subscription` prefix)

72. `POST /subscription/create-checkout-session` - Creates a Stripe Checkout session for initiating a new subscription.
73. `GET /subscription/config` - Returns public Stripe configuration details (publishable key, price ID).
74. `GET /subscription/subscription-status` - Checks and returns the current subscription status for a given user.
75. `GET /subscription/session-status` - Checks the status (e.g., complete, open) of a specific Stripe Checkout session.
76. `POST /subscription/webhook` - Endpoint for Stripe to send webhook events (payment success, subscription updates, etc.).
77. `POST /subscription/cancel-subscription` - Allows an authenticated user to request cancellation of their Stripe subscription.
78. `GET /subscription/check-flow` - Checks if the current user session is part of an OAuth sign-up flow that includes subscription.
79. `POST /subscription/clear-temp-data` - Clears temporary registration data stored during the checkout process for new users.
80. `POST /subscription/verify-receipt` - Verifies an Apple App Store receipt to validate/update a user's subscription status.
81. `POST /subscription/apple-subscription` - Processes a new Apple subscription activated via a mobile app using receipt data.
82. `POST /subscription/restore-purchases` - Handles requests to restore Apple App Store purchases using receipt data.
83. `POST /subscription/apple-webhook` - Endpoint for Apple to send Server-to-Server notifications about subscription events.
84. `GET /subscription/apple-webhook` - Verification endpoint for Apple to confirm webhook URL validity.

## Game Routes

### Phishing Phrenzy (`/phishing` prefix)
85. `GET /phishing/examples` - Retrieves phishing and legitimate email/SMS/website examples for the game, with smart shuffling.
86. `POST /phishing/submit-score` - Submits a player's score for the Phishing Phrenzy game.
87. `GET /phishing/leaderboard` - Retrieves the leaderboard for the Phishing Phrenzy game.

### Cipher Challenge (`/cipher` prefix)
88. `GET /cipher/challenges` - Retrieves all cipher challenges, including user progress.
89. `POST /cipher/submit` - Submits a solution for a cipher challenge.
90. `POST /cipher/unlock-hint` - Allows a user to unlock a hint for a cipher challenge using in-game coins.

### Threat Hunter (`/threat-hunter` prefix)
91. `GET /threat-hunter/scenarios` - Retrieves metadata for all available log analysis scenarios.
92. `POST /threat-hunter/start-scenario` - Starts a log analysis scenario and returns full data including logs.
93. `POST /threat-hunter/submit-analysis` - Submits a user's analysis of logs for scoring.

### Incident Response (`/incident` prefix)
94. `GET /incident/scenarios` - Retrieves all available incident response scenarios.
95. `POST /incident/start` - Starts a specific incident response scenario.
96. `POST /incident/action` - Processes a user's action within an incident response scenario stage.
97. `POST /incident/complete` - Marks an incident response scenario as complete and calculates results.
98. `POST /incident/bookmark` - Toggles the bookmark status for an incident response scenario.
99. `GET /incident/bookmarks/<user_id>` - Retrieves all scenarios bookmarked by a user.

## Support Routes (`/support` prefix)

100. `GET /support/my-chat` - Retrieves a list of all support chat threads for the authenticated user.
101. `POST /support/my-chat` - Creates a new support chat thread for the authenticated user.
102. `GET /support/my-chat/<thread_id>` - Retrieves messages and details for a specific support thread.
103. `POST /support/my-chat/<thread_id>` - Posts a message to a specific support thread.
104. `POST /support/my-chat/<thread_id>/close` - Allows a user to close their own support thread.

## Public Newsletter Routes (`/newsletter` prefix)

105. `POST /newsletter/subscribe` - Subscribes an email address to the newsletter.
106. `POST /newsletter/unsubscribe` - Unsubscribes an email address using the email itself.
107. `GET /newsletter/unsubscribe/<token>` - Unsubscribes an email address using a unique token from an email link.

## Contact Form Routes (`/contact-form` prefix)

108. `POST /contact-form/submit` - Handles submissions from the public contact form.

## Admin Routes (`/cracked` prefix)

### General Admin
109. `GET /cracked/request-logs/nginx` - (Admin) Retrieves recent Nginx access logs.
110. `GET /cracked/request-logs/api` - (Admin) Retrieves recent API request logs recorded by the application.
111. `POST /cracked/login` - (Admin) Authenticates an admin user via password or OAuth (Google).
112. `POST /cracked/logout` - (Admin) Logs out the currently authenticated admin user.
113. `GET /cracked/dashboard` - (Admin) Retrieves aggregated statistics for the admin dashboard.
114. `GET /cracked/performance` - (Admin) Retrieves application performance metrics and history.
115. `GET /cracked/web-vitals` - (Admin) Retrieves collected Web Vitals metrics.
116. `POST /cracked/report-web-vitals` - (Admin Frontend) Endpoint for frontend to report Web Vitals.
117. `GET /cracked/recent-errors` - (Admin) Retrieves recent application errors.
118. `GET /cracked/activity-logs` - (Admin) Retrieves audit log entries (focus on failed attempts).
119. `GET /cracked/db-logs` - (Admin) Retrieves database performance sample logs.
120. `POST /cracked/db-shell/read` - (Admin) Executes read-only database queries (Superadmin only).
121. `GET /cracked/health-checks` - (Admin) Retrieves results from periodic API health checks.
122. `GET /cracked/api-health-check` - (Admin) Performs a live health check on API and database.
123. `GET /cracked/server-metrics` - (Admin) Retrieves current server resource usage statistics.
124. `GET /cracked/rate-limits` - (Admin) Displays current rate limit usage data.
125. `GET /cracked/csrf-token` - (Admin) Generates and returns a CSRF token for admin actions.
126. `GET /cracked/admin-access-logs` - (Admin) Retrieves logs specific to admin login attempts.
127. `GET /cracked/user-requests` - (Admin) Retrieves data on unique user requests with cooldown.

### User Management (Admin)
128. `GET /cracked/users` - (Admin) Lists registered users with filtering, pagination, and search.
129. `POST /cracked/users/<user_id>/toggle-subscription` - (Admin) Manually activates/deactivates a user's subscription.
130. `PUT /cracked/users/<user_id>` - (Admin) Updates user fields (username, coins, XP, etc.).
131. `DELETE /cracked/users/<user_id>` - (Admin) Deletes a user account (Supervisor role required).
132. `POST /cracked/users/<user_id>/reset-password` - (Admin) Resets a user's password (Supervisor role required).

### Support Management (Admin)
133. `GET /cracked/supportThreads` - (Admin) Lists all support threads.
134. `GET /cracked/supportThreads/<thread_id>` - (Admin) Retrieves a specific support thread.
135. `POST /cracked/supportThreads/<thread_id>/reply` - (Admin) Replies to a support thread.
136. `POST /cracked/supportThreads/<thread_id>/close` - (Admin) Closes a support thread.
137. `DELETE /cracked/supportThreads/clear-closed` - (Admin) Deletes all closed support threads (Supervisor role required).
138. `POST /cracked/supportThreads/createFromAdmin` - (Admin) Creates a new support thread for a user.

### Test Management (Admin)
139. `GET /cracked/tests` - (Admin) Lists all tests/quizzes.
140. `POST /cracked/tests` - (Admin) Creates a new test/quiz (Supervisor role required).
141. `PUT /cracked/tests/<test_id>` - (Admin) Updates an existing test/quiz (Supervisor role required).
142. `DELETE /cracked/tests/<test_id>` - (Admin) Deletes a test/quiz (Supervisor role required).
143. `PUT /cracked/tests/<test_id>/update-name` - (Admin) Updates the name of a test (Supervisor role required).

### Daily Question Management (Admin)
144. `GET /cracked/daily` - (Admin) Lists all daily PBQ questions.
145. `POST /cracked/daily` - (Admin) Creates a new daily PBQ (Supervisor role required).
146. `PUT /cracked/daily/<obj_id>` - (Admin) Updates an existing daily PBQ (Supervisor role required).
147. `DELETE /cracked/daily/<obj_id>` - (Admin) Deletes a daily PBQ (Supervisor role required).

### Newsletter Management (Admin)
148. `POST /cracked/newsletter/create` - (Admin) Creates a new draft newsletter campaign (Supervisor role required).
149. `GET /cracked/newsletter/<campaign_id>` - (Admin) Retrieves details of a specific newsletter campaign.
150. `POST /cracked/newsletter/send/<campaign_id>` - (Admin) Sends a newsletter campaign to subscribers (Supervisor role required).
151. `GET /cracked/newsletter/subscribers` - (Admin) Retrieves a list of all newsletter subscribers.
152. `GET /cracked/newsletter/campaigns` - (Admin) Retrieves a list of all newsletter campaigns.
153. `DELETE /cracked/newsletter/<campaign_id>` - (Admin) Deletes a newsletter campaign (Supervisor role required).

### Revenue & Subscription Analytics (Admin)
154. `GET /cracked/revenue/overview` - (Admin) Provides an overview of revenue and subscription metrics.
155. `GET /cracked/revenue/signups` - (Admin) Shows daily signup counts for the last 7 days.
156. `GET /cracked/revenue/cancellation` - (Admin) Displays metrics related to subscription cancellations.
157. `GET /cracked/revenue/recent-signups` - (Admin) Lists the most recently subscribed users.

## Honeypot Routes

### Honeypot Admin & Analytics (`/honeypot` prefix)
158. `GET /honeypot/analytics` - (Admin) Returns general analytics about honeypot activity.
159. `POST /honeypot/log-interaction` - (Internal) Endpoint for honeypot pages to log client-side interactions.
160. `GET /honeypot/detailed-stats` - (Admin) Returns more detailed statistics about honeypot activity.
161. `GET /honeypot/interactions` - (Admin) Views honeypot interaction logs with pagination and filtering.
162. `GET /honeypot/interactions/<interaction_id>` - (Admin) Gets detailed information for a specific honeypot interaction.
163. `GET /honeypot/combined-analytics` - (Admin) Returns combined analytics from `scanAttempts` and `honeypot_interactions` collections.
164. `GET /honeypot/html-interactions` - (Admin) Retrieves HTML page interaction logs with filtering and pagination.
165. `GET /honeypot/html-interactions/stats` - (Admin) Gets statistics about HTML page interactions.
166. `GET /honeypot/html-interactions/<interaction_id>` - (Admin) Gets details of a specific HTML page interaction.

### Honeypot Decoy Pages (Various Prefixes or No Prefix)
167. **Dynamic Honeypot Pages** (GET, POST) - Numerous routes like `/wp-admin`, `/admin/login`, `/phpmyadmin`, `/system/verify`, `/cpanel`, etc., are dynamically registered to serve various fake admin/login pages based on common scan paths. These are handled by `honeypot_pages_bp` and include templates like `admin-login.html`, `wp-dashboard.html`, `database-dashboard.html`, the `stepX.html` redirection series, etc.
168. `/<path:path>` (GET, POST) - Catch-all route that attempts to categorize the path and serve an appropriate honeypot page or a generic login page.

### Honeypot C2 (Command & Control) (`/c2` prefix) (Optional-- not currently implemented, it is an addition to the honeypot)
169. `POST /c2/analytics/collect` - (Implant) C2 primary endpoint for implants to send data, disguised as analytics.
170. `POST /c2/metrics/push` - (Implant) C2 fallback endpoint for implants, disguised as metrics collection.
171. `POST /c2/payload/store` - (Implant) Endpoint for implants to send harvested credentials or other exfiltrated data.
172. `POST /c2/scenario/fetch` - (Implant) Endpoint for implants to poll for new commands from the C2 server.
173. `POST /c2/scenario/submit` - (Implant) Endpoint for implants to submit the results of executed commands.
174. `GET /c2/metrics/pixel.gif` - (Implant) Tracking pixel endpoint for implants to beacon back basic data.
175. `GET /c2/c2/sessions` - (Admin) Lists all active C2 sessions (implant check-ins).
176. `GET /c2/c2/sessions/<session_id>` - (Admin) Retrieves detailed information for a specific C2 session.
177. `GET /c2/c2/sessions/<session_id>/credentials` - (Admin) Retrieves all credentials harvested by a specific C2 session.
178. `POST /c2/c2/sessions/<session_id>/command` - (Admin) Queues a new command to be sent to a specific C2 implant.
179. `GET /c2/c2/commands/<command_id>/results` - (Admin) Retrieves the results for a previously issued command.
180. `GET /c2/c2/credentials` - (Admin) Retrieves all credentials harvested by all C2 implants.
181. `GET /c2/c2/dashboard` - (Admin) Gets summary statistics for the C2 dashboard (active sessions, credentials, commands).

## Miscellaneous & System Routes

182. `GET /.well-known/apple-app-site-association` - Serves the Apple App Site Association file for Universal Links.
183. `GET /avatars/<path:filename>` - Serves avatar images.
184. `GET /health` - Basic health check endpoint for the backend.
185. `GET /api/<path:path>` (GET, POST) - Nginx-proxied catch-all that routes to the honeypot handler. (This primarily serves as an entry point for honeypot interactions when requests are prefixed with `/api/` by Nginx, then internally routed.)
------------
