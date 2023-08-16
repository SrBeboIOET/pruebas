# Authentication Process Guide
This guide explains the authentication and authorization process within the application through a series of steps. 
This process ensures that authenticated users have appropriate access to resources and functions in the application.

## Workflow of Authentication Process
![image](https://github.com/SrBeboIOET/pruebas/assets/135857180/d5f8c1d7-9b52-41b1-8d56-59d61764ea58)

### Step 1: Authentication Request
- The application sends a GET request to the authentication service in the backend via the route /auth/login/snack-app.
### Step 2: Authorization with Google OAuth 2.0
- The backend authentication service receives the request and utilizes Google OAuth 2.0 to authorize the access token.
- Google OAuth 2.0 verifies the user's credentials and sends the access token to the backend authentication service.
### Step 3: User Verification
- The backend authentication service verifies whether the user has previously logged in.
- If the user has previously logged in, their status is checked. If the user is new, a new user profile is created, and a session is established in the current request.
### Step 4: Session Creation and Access
- The backend authentication service generates a session cookie containing relevant user information.
- With the session cookie established, the user can access the authenticated application.
### Keep in mind:

- **Security:** Ensure all communication is over HTTPS to protect data in transit.
- **Token Validation:** Thoroughly validate received tokens to prevent tampering.
- **Token Expiration Handling:** Properly handle token expiration and refresh tokens to avoid unauthorized access.
- **User Consent:** Always obtain explicit user consent before accessing their data.
- **Sensitive Data:** Do not store sensitive data like passwords directly in cookies; use unique session identifiers.
- **Session Management:** Manage sessions securely and store tokens safely on the server.
- **Error Handling:** Implement clear error messages to guide users and prevent unexpected issues.
- **OAuth 2.0 Best Practices:** Follow [best practices](https://developers.google.com/identity/protocols/oauth2/resources/best-practices?hl=es-419) for token validation and secure storage.
- **User Data Protection:** Protect user data, especially sensitive information, to prevent breaches.
- **Logout Mechanism:** Provide a secure logout mechanism to prevent session hijacking.
- **Regulatory Compliance:** Ensure compliance with relevant regulations like GDPR to avoid legal consequences.

## Workflow of Authorization Process
