# CS360
# Steady Weight

App Requirements and Goals

Steady Weight is an Android weight tracking app designed to help users record daily weights, review previous entries, and work toward a personal goal. The app supports account creation, login, and a local SQLite database that saves each user’s information. Users can add, edit, and delete weight records, set a goal for weight loss or gain, and choose whether to enable SMS notifications when they reach that goal. My goal was to make tracking progress straightforward without adding unnecessary steps.

User Interface and User Needs

The app includes a login and account creation screen, a dashboard with a grid of weight records, an entry screen for weights and goals, and an SMS settings screen. The dashboard brings the user’s records and goal together so the most useful information is easy to find.

I kept users in mind by using clear labels, consistent navigation, input feedback, and confirmation before deleting a record. Users can also continue using the app if they decline SMS permission. These choices support the main purpose of the app while giving users control over their information and optional features.

Coding Approach

I approached development by breaking the requirements into smaller parts: account access, database storage, weight management, goal tracking, and SMS permissions. I separated database operations and account authentication from the main screen logic so each component had a clear responsibility.

I also used input validation, parameterized database queries, and salted password hashing. Database constraints prevent duplicate usernames and multiple weight entries for the same user and date. In future projects, I can apply this same approach by developing manageable features, separating responsibilities, and considering invalid input alongside the normal user flow.

Testing and Verification

During preparation, source code, XML layouts, and the SQLite schema were checked. An Android build was attempted, but the environment could not download Gradle, and an Android SDK and emulator were unavailable. Because of those limitations, successful compilation, emulator behavior, and SMS delivery were not confirmed in that environment.

The project includes an acceptance checklist covering account creation, incorrect passwords, adding and changing records, saved data, account separation, and both acceptance and denial of SMS permission. This process is important because reviewing code alone cannot confirm how an app behaves on a device. It also identified the remaining checks needed before considering the app fully verified.

Overcoming Challenges

One challenge was connecting goal tracking to an optional SMS feature without making that feature necessary for the app to work. I addressed this by checking both the user’s notification preference and Android’s permission status before attempting to send a message. Weight tracking remains available when SMS is disabled.

Another challenge was deciding which record should determine whether a goal has been reached. The app uses the latest dated weight so an older historical entry does not replace the user’s current progress. It also tracks notification status to reduce repeated messages for the same goal.

Strongest Component

The database component best demonstrates my knowledge and skills. It connects accounts to their own weight records and settings, supports creating, reading, updating, and deleting entries, and preserves information between sessions. Queries and changes are scoped to the logged-in user, which helps keep accounts separate.

This component brought together several parts of the course, including data modeling, persistent storage, input validation, and connecting a user interface to application logic. It gave the app a practical foundation for supporting its main user needs.
