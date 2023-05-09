Here's a low-level design for a login system that uses OTP:

- User enters their username and requests to log in.
    - Mobile and email address can be used as username
- Server generates an OTP and sends it to the user's registered phone number or email address.
    - The OTP generated shall be of 6 digits
- User enters the OTP and sends it to the server.
- Server validates the OTP and creates a session for the user.
- User is logged in and can access their account.
- Here's a more detailed breakdown of the components involved:

**User Interface:** This is the interface that the user interacts with, where they enter their mobile number/email address and OTP. 

**Authentication Server:** This is the server that generates and verifies OTPs. It receives login requests from the user interface and generates OTPs to send to the user's phone or email address. It also receives OTPs from the user and validates them.

**Database:** This is where user information is stored, including usernames, passwords (hashed and salted), phone numbers, and email addresses. It also stores information about sessions, such as session IDs and expiration times.

**SMS/Email Gateway:** This is the service that sends the OTP to the user's phone number or email address. The server sends the OTP to the gateway, which then sends it to the user.

**Session Management:** Once the user is authenticated, the server creates a session for them, which is stored in the database. The session includes a session ID and an expiration time. The session ID is returned to the user interface, which uses it to make subsequent requests to the server.

**OTP Generation:** The server generates OTPs using a random number generator and sends them to the user's phone number or email address. The OTP is typically a 6-digit number.

**OTP Validation:** The server validates OTPs by comparing them to the OTP that was generated for the user. If the OTP is valid, the user is authenticated and a session is created. If the OTP is invalid, the user is not authenticated.

**Session Expiration:** Sessions have an expiration time to prevent unauthorized access. When a session expires, the user is automatically logged out and must log in again to access their account.

Overall, the design of an OTP-based login system involves a number of different components working together to ensure that users can securely log in to their accounts.
