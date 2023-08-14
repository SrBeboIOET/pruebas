# Authentication Process Guide
This guide explains the authentication and authorization process within 
the application through a series of steps. This process ensures 
that authenticated users have appropriate access to resources and functions in the application.

## Step One: User Authentication
1. The process begins when a user attempts to authenticate within the application.
2. The application's user interface sends a request via **/authn/login/snack-app** to the backend's authentication service.

## Step Two: Session Cookie Generation
1. The authentication service processes the authentication request and verifies the user's credentials.
2. Once the credentials are verified, the authentication service generates a "session cookie" for the authenticated user.
3. This session cookie is used to identify the user in subsequent sessions.

## Step Three: User Information Retrieval
1. The backend application receives the session cookie from the authenticated user.
2. Using the session cookie, the backend makes a GET request via the **/users/** route to retrieve specific user information.

## Step Four: Function Access Verification
1. To ensure the user has access to specific functions, the backend makes a GET request to the authentication service.
2. The request is made through the **/has/access/company-app-name/get/users** route.
3. The authentication service verifies the session cookie and validates whether the user has access to the user information function.

## Step Five: User Session Validation
1. The authentication service validates the user's session.
2. If the user's session is not properly specified, the authentication service responds with a 401 error "Could not validate credentials" indicating invalid credentials.

## Step Six: User Status Check
1. If the user has a valid session and their access is verified, their status is then checked.
2. If the user is inactive, the authentication service sends a 403 error "User does not have enough permissions" to the application's backend.
3. The backend responds to the user interface with a "User does not have permissions" message, informing the user of insufficient permissions.

## Step Seven: Resource Access Verification
1. The authentication service utilizes the Open Policy Agent (OPA) to verify whether the user has access to the requested resources and functions.
2. OPA grants or denies user access based on defined access policies.

## Step Eight: Access Granting
1. If OPA grants user access, the authentication service provides access via the application's backend.
2. The backend can then proceed to process requests and grant access to requested resources.

## Step Nine: Results Display
1. Based on the granted access, the backend of the application displays user information within the user interface.
2. If the user lacks sufficient access, the backend responds with a "403 User does not have enough permissions" message, informing the user about the access restriction.

This authentication and authorization process ensures that authenticated users are appropriately granted access to application resources and functions, while those without necessary permissions are clearly notified of their restricted access.
