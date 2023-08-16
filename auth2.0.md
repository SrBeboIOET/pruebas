# Authentication Process Guide
This guide explains the authentication and authorization process within the application through a series of steps. 
This process ensures that authenticated users have appropriate access to resources and functions in the application.

## Authentication Process
![image](https://github.com/ioet/internal-auth-service/raw/develop/diagrams/sequence_diagrams/authentication_flow.png)

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

## Authorization Process
![image](https://github.com/ioet/internal-auth-service/raw/develop/diagrams/sequence_diagrams/authorization_flow.png)
### Step 1: User Authentication
- The user interface initiates user authentication by sending an HTTP request to the auth service in the backend using the established domain in the application.
- The backend auth service generates a session cookie, and the user interface sends a GET request to the application backend to fetch user data.
### Step 2: Checking User Access
- The application backend sends a GET request to the backend auth service to determine whether the user has access or not.
- The backend auth service validates the user's session. If the user does not have a registered session in the application, a "401. Could not validate credentials" error is displayed, and the backend sends a session response to the user interface.
- If the user has a registered session, the user's status is verified by the backend auth service. If the user is inactive, a "403. User does not have enough permissions" error is sent to the application backend. The backend responds with "User does not have permissions."
- If the user is not inactive, the backend checks if the user has access to a specific resource using OPA (Open Policy Agent), which handles policies and permissions assigned to the user. The OPA defines what actions the user is allowed to perform on the requested resource.
### Step 3: Permission Verification
- The backend auth service informs the application backend whether the user has the necessary permissions.
- If the user has the required permissions, the application backend processes the request.
- If the user does not have the necessary permissions, a "403. User does not have enough permissions" error is sent from the backend to the user interface.
### Keep in mind:
- **User Authentication:** Ensure secure user authentication through the backend auth service.
- **Session Handling:** The backend auth service manages session cookies for authenticated users.
- **User Status:** Verify if the user is active or inactive to determine permission status.
- **Permissions Verification:** Use OPA to verify user permissions based on predefined policies.
- **Error Handling:** Properly handle errors and responses for unauthorized and inactive users.
- **Access Control:** The backend auth service ensures users have the right permissions for the requested resource.
- **Communication:** All communication between user interfaces and backend services should be secured (HTTPS).
- **Security:** Apply security measures to prevent unauthorized access and data breaches.

## What is Open Policy Agent [(OPA)](https://www.openpolicyagent.org/docs/latest/)?
Is an open-source, general-purpose policy engine that enables organizations to define and enforce policies across various aspects of their software systems. OPA provides a declarative language for expressing policies and a runtime environment for evaluating them against incoming requests or data.

OPA allows you to decouple policy logic from application code, making it easier to manage and update policies independently. It can be integrated into various layers of an application stack, such as microservices, APIs, and admission control in Kubernetes clusters. With OPA, you can define fine-grained access controls, authorization rules, and other policies, ensuring security and compliance across your system.

## How can I configure the permissions using OPA?
It depends on your project's structure and the conventions followed in your development environment, but generally, permissions are configured in a configuration file named data.yaml, in which you specify the application's name, roles, permissions, and the endpoints that each user type can access depending on their role.
