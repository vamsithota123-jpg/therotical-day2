# therotical-day2
1. What are the primitive and non-primitive data types in JavaScript?

JavaScript has primitive types: string, number, boolean, null, undefined, symbol, and bigint.
Non-primitive (reference) types include object, array, and function.
Primitive types store actual values, while reference types store memory addresses.
Primitives are immutable; reference types are mutable.

Difference & Memory:
Primitives are stored in stack memory and copied by value.
Reference types are stored in heap memory and copied by reference.

2. Explain type coercion in JavaScript

Type coercion is JavaScript’s automatic or manual conversion of values from one data type to another.
Implicit coercion happens automatically (e.g., "5" + 2 → "52").
Explicit coercion is done using functions like Number(), String(), or Boolean().

== vs ===:
== compares values after coercion, while === compares both value and type without coercion.

3. What is NaN? How do you check if a value is NaN?

NaN stands for Not-a-Number, representing an invalid numeric result (e.g., 0 / 0).
NaN === NaN returns false because NaN is not equal to any value, including itself.
Use Number.isNaN(value) for accurate checking.

isNaN vs Number.isNaN:
isNaN() performs type coercion and may give incorrect results.
Number.isNaN() checks strictly and is the recommended approach.

1. What is HTTPS? How does it differ from HTTP?

HTTPS is the secure version of HTTP that encrypts data using SSL/TLS.
HTTP sends data in plain text, making it vulnerable to attacks.
HTTPS ensures confidentiality, integrity, and authentication.
It uses port 443, while HTTP uses 80.

2. Explain SSL/TLS. What is the SSL handshake process?

SSL/TLS are security protocols that encrypt communication between client and server.
The SSL handshake establishes a secure session before data transfer.
Steps include client hello, server certificate exchange, key generation, and session creation.
After handshake, all data is encrypted.

3. What is encryption? Explain symmetric vs asymmetric encryption.

Encryption converts plain text into cipher text to protect data.
Symmetric encryption uses a single shared key (fast, less secure for key exchange).
Asymmetric encryption uses a public-private key pair (more secure, slower).
TLS uses both: asymmetric for key exchange, symmetric for data transfer.

4. What are certificates? What is a Certificate Authority (CA)?

A digital certificate verifies a website’s identity and public key.
It ensures the server is trustworthy.
A Certificate Authority (CA) is a trusted entity that issues and validates certificates.
Browsers trust certificates signed by known CAs.

5. What is the difference between authentication and authorization?

Authentication verifies who the user is (login).
Authorization determines what the user can access.
Authentication happens first, followed by authorization.
Example: logging in vs accessing admin features.

6. Explain session-based authentication. How do sessions work?

In session-based authentication, the server stores user state in memory or a database.
After login, a session ID is generated and stored in a cookie.
Each request sends the session ID to identify the user.
It works well for server-rendered apps but doesn’t scale easily.

7. What are cookies? What are their security attributes?

Cookies are small pieces of data stored in the browser.
HttpOnly prevents access via JavaScript (XSS protection).
Secure sends cookies only over HTTPS.
SameSite prevents CSRF by restricting cross-site requests.

8. What is token-based authentication? How does it differ from session-based auth?

Token-based authentication uses tokens (like JWT) stored on the client.
The server does not store session state, making it stateless.
It scales well for APIs and microservices.
Unlike sessions, tokens are sent in headers, not cookies.

1. What are functional and class components?

In React, class components are ES6 classes that use lifecycle methods and this.state.
Functional components are plain JavaScript functions that return JSX.
Earlier, functional components were stateless, but Hooks changed that.
Today, functional components are the standard approach.

Hooks impact:
React Hooks allow functional components to manage state and side effects.
This removed the need for class components in most cases.

Performance:
Functional components are generally more performant due to simpler syntax and fewer overheads.
They also work better with React optimizations like memoization.

2. What is the difference between props and state?

Props are read-only data passed from parent to child components.
State is mutable and managed within the component itself.
Props control component configuration, while state controls dynamic behavior.

Follow-ups:
Props cannot be modified inside a child component.
Both prop changes and state changes can trigger re-renders.

3. How does React decide when to re-render a component?

React re-renders a component when its state or props change.
It uses a virtual DOM diffing process to update only necessary parts.
If the new state value is the same as the old one, React may skip re-render.

Optimization:
React.memo prevents re-rendering when props haven’t changed.
It’s useful for optimizing pure functional components.

4. Explain the component lifecycle (mount → update → unmount)

Mounting is when a component is created and inserted into the DOM.
Updating happens when props or state change.
Unmounting occurs when the component is removed from the DOM.

Hooks mapping:
useEffect(() => {}, []) → componentDidMount
useEffect(() => {}) → componentDidUpdate
Cleanup function → componentWillUnmount

Cleanup importance:
Without cleanup, memory leaks and unexpected behavior can occur,
especially with timers, subscriptions, or event listeners.
