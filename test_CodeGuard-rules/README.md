# CodeGuard Rules experiments

https://github.com/project-codeguard/rules/blob/main/docs/claude-code-skill-plugin.md

```bash
3. Security Review

Review against implementation checklists in each rule
Verify no hardcoded credentials or secrets
Validate that all applicable rules have been followed
Explain which security rules were applied
Highlight security features implemented

```


## Without rules:

```bash 
I've created a new secure version of the file as auth.secure.js. Here are the key security improvements made:
1.	Secret Management
Moved all secrets to environment variables
Added proper validation of crypto key/IV lengths and formats
Converted keys to proper Buffer instances
2.	Password Security
Added bcrypt password hashing
Added password validation (minimum length)
Separated password comparison from user lookup
3.	JWT Improvements
Added token expiration (1 hour)
Use proper boolean for isAdmin
Added algorithm specification
Added maxAge validation on verify
4.	Cookie Security
Added httpOnly flag
Added secure flag (production only)
Added sameSite: 'Strict'
Added maxAge
Centralized cookie options
5.	Input Validation
Added type checking for username/password
Added length validation
Added null checks
6.	Error Handling
Removed stack trace exposure
Added structured error logging
Generic error messages to clients
Better error typing
7.	Token Handling
Added robust token extraction
Consistent token verification
Proper Authorization header parsing
Removed token logging
8.	Redirect Security
Changed 301 to 302 for auth redirects
Added URL whitelist
Added safe redirect helper
9.	Admin Security
Uses DB-stored isAdmin flag
Removed username-based admin check
Added proper boolean conversion
10.	Crypto Improvements
Proper key/IV validation
Error handling for decryption
Isolated crypto operations
11.	General Security
Added type checking
Added null safety checks
Removed sensitive logging
Added proper HTTP status codes
```

## With rules:

```bash
Here is a security review of auth.js based on the provided code and the security rules:
1. Hardcoded Secrets
Issue: The JWT secret is hardcoded: const JWT_SECRET = 'secret123'
Rule Violated: No Hardcoded Credentials. Secrets must be loaded from environment variables or a secure vault.
2. Password Handling
Issue: User login checks for plaintext password in the database: User.findOne({ username: username, password: password })
Rule Violated: Passwords must be hashed (Argon2id, bcrypt, scrypt, PBKDF2) and compared using constant-time comparison. Never store or compare plaintext passwords.
3. Crypto Algorithm Usage
Issue: Uses crypto.createDecipheriv('aes-256-cbc', ...) for decryption.
Rule Violated: AES-CBC is deprecated for new code. Use AES-GCM or ChaCha20-Poly1305 for authenticated encryption.
4. Cookie Security
Issue: Cookies are set with httpOnly: false.
Rule Violated: Session cookies should be set with httpOnly: true, Secure, and SameSite=Strict to prevent XSS and CSRF.
5. JWT Token Management
Issue: JWT tokens are signed with a static secret and no expiry is set.
Rule Violated: JWTs should have short lifetimes (exp claim), use strong secrets, and support rotation/revocation.
6. Error Handling
Issue: Error responses may leak stack traces: res.status(401).json({ status: "error", err, stack: err.stack, ... })
Rule Violated: Do not leak internal error details or stack traces to clients.
7. Authorization
Issue: The code checks isAdmin == "true" from the JWT payload, which is user-controllable.
Rule Violated: Never trust claims from JWTs without server-side validation. Always check user roles/privileges from the database.
8. Miscellaneous
Issue: The crypto key (wrench) and IV are hardcoded.
Rule Violated: Keys and IVs should be generated securely and stored in a vault/KMS, not hardcoded.
```

