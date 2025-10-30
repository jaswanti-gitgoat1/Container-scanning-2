<!-- ====== ARNICA AI CODING RULES START ====== -->

---
**🔒 SECURITY RULES MANAGED BY ARNICA**

These AI coding assistant rules are automatically managed by your security team to ensure secure coding practices.
For more details, see: https://docs.arnica.io/arnica-documentation/developers/ai-coding-rules
To exclude this file, please contact your security team.

**Message from the security team:** test 123
---

## Security Best Practices for AI Agents

**🛡️ These security guidelines ensure code changes maintain the repository's security posture.**

**Pre-Development Security Review:**
1. **Review** existing security patterns and implementations in the codebase
2. **Identify** authentication, authorization, and data validation approaches already in use  
3. **Maintain** consistency with established security controls
4. **Validate** that new code follows the same security standards
5. **Communicate** any security concerns or conflicts clearly

**CRITICAL: Modified Files Security Scan and Remediation:**

**MANDATORY for all file modifications (not new files):**
- **Scan modified files only** - Review existing code in files you're modifying for security vulnerabilities
- **Identify rule violations** - Check if existing code violates any security guidelines in this document
- **Fix vulnerabilities with minimal risk** - Remediate security issues while avoiding breaking changes
- **Prioritize low-risk fixes** - Focus on fixes that improve security without affecting core functionality
- **Document security improvements** - Add rule ID citations when fixing existing vulnerabilities

**Security Remediation Guidelines (for existing vulnerabilities in modified files only):**
- **Safe to fix immediately:** Input validation, output encoding, error message exposure, logging improvements
- **Moderate risk - fix with caution:** Authentication flows, authorization checks, session handling
- **High risk - flag for review:** Password hashing changes, encryption key modifications, database schema changes
- **Always preserve existing functionality** - Security improvements should not break existing features
- **Test thoroughly** - Verify that security fixes don't introduce regressions

**Modified File Remediation Process:**
1. **Identify the file modification scope** - Understand what you're changing and why
2. **Scan for security violations** - Review existing code against this document's rules  
3. **Categorize vulnerability risk** - Assess impact of potential security fixes
4. **Apply safe fixes immediately** - Implement low-risk security improvements with rule citations
5. **Flag high-risk issues** - Report critical security issues that need careful planning
6. **Document all changes** - Include rule IDs for both new code and security fixes

**MANDATORY Code Implementation Requirements:**

**CRITICAL: You MUST extract and use rule IDs from this document:**
- **Locate rule IDs** - Every security guideline in this document ends with `| Rule ID:[RULE_ID]` 
- **Extract exact rule IDs** - Copy the exact rule ID from the guideline you're implementing (e.g., `AUTH_TYPESCRIPT_CREATE_HASHUSERPASSWORD`)
- **ALWAYS add rule citations** - Include a comment with the exact rule ID for EVERY security implementation using this format: `// Agentic Rule (EXACT_RULE_ID): [your explanation]`

**Rule ID Citation Requirements:**
- **Mandatory for ALL security implementations** - No security code should be written without referencing the applicable rule ID
- **Use exact rule IDs** - Copy the exact rule ID text from the `| Rule ID:[RULE_ID]` markers in this document
- **Follow strict comment format** - `Agentic Rule (RULE_ID): [one-sentence explanation]`
- **Example**: `Agentic Rule (AUTH_TYPESCRIPT_CREATE_HASHUSERPASSWORD): Using bcrypt with 12 rounds for secure password hashing`

**How to find rule IDs in this document:**
1. Find the security guideline you need to implement
2. Look for `| Rule ID:[RULE_ID]` at the end of the guideline
3. Copy the exact rule ID (everything between the brackets)
4. Use it in your code comment exactly as shown

**MANDATORY Security Implementation Checklist** (verify before implementing):

**Rule ID Compliance (REQUIRED):**
- **Found the applicable rule ID** - Located the `| Rule ID:[RULE_ID]` for each security guideline being implemented
- **Added rule ID citation** - Every security implementation includes `Agentic Rule (RULE_ID): [explanation]` comment in its specific language format
- **Used exact rule ID** - Copied the exact rule ID text from the document without modification
- **No security code without rule ID** - Every security-related implementation references its rule ID

**Modified Files Security Review (REQUIRED):**
- **Scanned modified files** - Reviewed existing code in all modified files for security violations
- **Identified vulnerabilities** - Found and categorized any security issues in existing code
- **Applied safe fixes** - Implemented low-risk security improvements with rule citations
- **Flagged high-risk issues** - Identified critical security problems requiring careful planning
- **Preserved functionality** - Ensured security fixes don't break existing features

**General Security Compliance:**
- Preserves existing authentication and authorization mechanisms
- Ensures input validation and output encoding standards  
- Follows established security patterns and libraries, unless the existing code is vulnerable or deprecated
- Avoids introducing new attack vectors or vulnerabilities
- If a vulnerability is identified in existing code, it should be resolved in the new code

**When Security and Requirements Conflict:**
Prioritize security and clearly explain the security implications. Suggest secure alternatives that meet the functional requirements.

---

### Authentication
**Maintain existing authentication patterns for consistency and security:**
- **Pattern consistency** - identify and reuse existing authentication patterns (token middleware, access guards, OAuth flows) | Rule ID:`[ARNIE_AUTH_PATTERN_CONSISTENCY]`
- **Password hashing** - use strong hashing algorithms (bcrypt 12+ rounds, Argon2id, scrypt) with proper salt generation | Rule ID:`[ARNIE_AUTH_PASSWORD_HASHING]`
- **Token verification** - implement secure token validation with proper secret management and expiration handling | Rule ID:`[ARNIE_AUTH_TOKEN_VERIFICATION]`
- **Multi-factor authentication** - add secondary authentication factors (TOTP, SMS verification, hardware keys) for critical systems | Rule ID:`[ARNIE_AUTH_MULTI_FACTOR]`
- **Authentication flows** - implement proper login/logout flows with account lockout and rate limiting | Rule ID:`[ARNIE_AUTH_AUTHENTICATION_FLOWS]`
- **Credential validation** - enforce strong password policies and secure credential recovery processes | Rule ID:`[ARNIE_AUTH_CREDENTIAL_VALIDATION]`

### Access Control
**Follow existing authorization patterns to maintain security boundaries:**
- **Pattern reuse** - identify and reuse existing access control patterns and authorization middleware | Rule ID:`[ARNIE_ACCESS_PATTERN_REUSE]`
- **Authorization consistency** - follow established role-based or permission-based access control systems | Rule ID:`[ARNIE_ACCESS_AUTHORIZATION_CONSISTENCY]`
- **Control extension** - extend existing permission systems rather than creating parallel authorization mechanisms | Rule ID:`[ARNIE_ACCESS_CONTROL_EXTENSION]`
- **Permission middleware** - implement role-based protection for every secured endpoint with explicit grants | Rule ID:`[ARNIE_ACCESS_PERMISSION]`
- **Deny-by-default** - use permission checking functions that require explicit authorization for access | Rule ID:`[ARNIE_ACCESS_DENY_DEFAULT]`
- **Server-side validation** - verify permissions against authoritative server state, never trust client claims | Rule ID:`[ARNIE_ACCESS_SERVER_SIDE]`
- **Privileged operations** - require elevated permissions for sensitive functions (user management, financial operations, data export) | Rule ID:`[ARNIE_ACCESS_PRIVILEGED_OPERATIONS]`
- **Role hierarchy** - implement proper role checks for admin functions (system configuration, user deletion, billing access) | Rule ID:`[ARNIE_ACCESS_ROLE_HIERARCHY]`
- **Resource ownership** - verify user ownership or permission before allowing resource access or modification | Rule ID:`[ARNIE_ACCESS_RESOURCE_OWNERSHIP]`
- **Action authorization** - create granular permission checks for critical operations (password resets, role changes, data purging) | Rule ID:`[ARNIE_ACCESS_ACTION_AUTHORIZATION]`

### Session Management
**Follow existing session handling patterns for consistent security:**
- **Pattern consistency** - identify and reuse existing session management patterns and configuration | Rule ID:`[ARNIE_SESSION_PATTERN_CONSISTENCY]`
- **Library usage** - follow established session libraries, middleware, and storage mechanisms | Rule ID:`[ARNIE_SESSION_USAGE]`
- **Secure cookies** - use secure cookie flags (HttpOnly, Secure, SameSite) with appropriate settings | Rule ID:`[ARNIE_SESSION_SECURE_COOKIES]`
- **Session regeneration** - regenerate session IDs after authentication, privilege changes, and sensitive operations | Rule ID:`[ARNIE_SESSION_SESSION_REGENERATION]`
- **Lifecycle management** - implement proper timeout (15-30 minutes or based on context), refresh, and secure destroy functions | Rule ID:`[ARNIE_SESSION_LIFECYCLE_MANAGEMENT]`
- **Secure storage** - use server-side storage with encryption for distributed session management | Rule ID:`[ARNIE_SESSION_SECURE_STORAGE]`
- **Session validation** - implement session tampering detection and concurrent session limits | Rule ID:`[ARNIE_SESSION_SESSION_VALIDATION]`

### Input Validation
**Critical defense against injection attacks - validate ALL user inputs:**
- **Server validation** - create validation middleware for all endpoints with schema enforcement | Rule ID:`[ARNIE_INPUT_SERVER_VALIDATION]`
- **Input sanitization** - remove dangerous characters (HTML tags, script elements, SQL patterns) | Rule ID:`[ARNIE_INPUT_INPUT_SANITIZATION]`
- **Field allowlisting** - accept only expected fields using filtering and validation functions | Rule ID:`[ARNIE_INPUT_FIELD_ALLOWLISTING]`
- **Prepared statements** - use parameterized queries for all database operations to prevent SQL injection | Rule ID:`[ARNIE_INPUT_PREPARED_STATEMENTS]`
- **Numeric validation** - ensure numeric inputs are within expected ranges and proper data types | Rule ID:`[ARNIE_INPUT_NUMERIC_VALIDATION]`
- **File upload validation** - check file size limits, content types, and filename safety | Rule ID:`[ARNIE_INPUT_FILE_UPLOAD]`
- **MIME type verification** - verify actual file content matches declared file type | Rule ID:`[ARNIE_INPUT_MIME_TYPE]`
- **Parameter validation** - validate all input sources (headers, query parameters, request body) | Rule ID:`[ARNIE_INPUT_PARAMETER_VALIDATION]`
- **Schema validation** - implement structural validation using appropriate validation frameworks | Rule ID:`[ARNIE_INPUT_SCHEMA_VALIDATION]`
- **Rate limiting** - apply request rate limits per endpoint to prevent abuse, only where it seems to be critical | Rule ID:`[ARNIE_INPUT_RATE_LIMITING]`

### Dangerous APIs
**Critical:** See dedicated sections below for detailed protection against Path Traversal, SSRF, and RCE attacks
**Secure alternatives:** Replace dangerous APIs with safe alternatives
**Safe implementation patterns:**
- **JSON parsing** - wrap in try/catch, validate with schema libraries | Rule ID:`[ARNIE_API_JSON_PARSING]`
- **Network requests** - use URL validation functions, implement IP allowlist checking | Rule ID:`[ARNIE_API_NETWORK_REQUESTS]`
- **File system APIs** - create path validation functions using proper path utilities and boundary checking | Rule ID:`[ARNIE_API_FILE_SYSTEM]`
- **Token storage** - implement secure storage functions with appropriate security flags | Rule ID:`[ARNIE_API_TOKEN_STORAGE]`
- **Process execution** - use safer execution methods with argument sanitization | Rule ID:`[ARNIE_API_PROCESS_EXECUTION]`
- **HTML rendering** - create content sanitization functions with established libraries | Rule ID:`[ARNIE_API_HTML_RENDERING]`
- **Dynamic imports** - implement module path validation with allowlist checking | Rule ID:`[ARNIE_API_DYNAMIC_IMPORTS]`

### Path Traversal Prevention
**Critical file system security measures:**
- **Path validation** - use proper path utilities to sanitize and normalize user-provided file paths | Rule ID:`[ARNIE_PATH_PATH_VALIDATION]`
- **Boundary checking** - ensure resolved paths remain within allowed base directories using path resolution | Rule ID:`[ARNIE_PATH_BOUNDARY_CHECKING]`
- **Path safety** - check that normalized paths don't contain dangerous sequences (../, null bytes, control characters) | Rule ID:`[ARNIE_PATH_PATH_SAFETY]`
- **Path building** - use secure path joining functions with pre-validated components only | Rule ID:`[ARNIE_PATH_PATH_BUILDING]`
- **Filename sanitization** - remove dangerous characters (slashes, dots, control chars) and enforce length limits | Rule ID:`[ARNIE_PATH_FILENAME_SANITIZATION]`
- **Extension allowlist** - maintain permitted file extensions list and validate uploads against it, only where the context about it can be inferred | Rule ID:`[ARNIE_PATH_EXTENSION_ALLOWLIST]`
- **Static file handling** - use secure static file serving functions with restricted access and proper path validation | Rule ID:`[ARNIE_PATH_STATIC_FILE]`
- **Upload validation** - validate file type, size, name, and destination path before processing | Rule ID:`[ARNIE_PATH_UPLOAD_VALIDATION]`
- **Path utilities** - combine base directory with sanitized relative paths using secure joining functions | Rule ID:`[ARNIE_PATH_PATH_UTILITIES]`
- **Input normalization** - canonicalize and resolve all file paths before security checks | Rule ID:`[ARNIE_PATH_INPUT_NORMALIZATION]`

### SSRF Prevention
**Critical measures to prevent unauthorized server-side requests:**
- **URL validation** - parse and validate URLs against allowlist of permitted domains and schemes | Rule ID:`[ARNIE_SSRF_URL_VALIDATION]`
- **Private IP blocking** - block private ranges (127.0.0.1, 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16) and localhost | Rule ID:`[ARNIE_SSRF_PRIVATE_BLOCKING]`
- **Domain allowlist** - maintain approved external domains list and validate against it before requests, if the context about it can be inferred | Rule ID:`[ARNIE_SSRF_DOMAIN_ALLOWLIST]`
- **Request timeouts** - set reasonable timeouts (5-30 seconds) to prevent resource exhaustion | Rule ID:`[ARNIE_SSRF_REQUEST_TIMEOUTS]`
- **Redirect limits** - disable HTTP redirects or implement strict redirect URL validation | Rule ID:`[ARNIE_SSRF_REDIRECT_LIMITS]`
- **Request rate limiting** - limit concurrent outbound requests per endpoint to prevent abuse, only where it seems to be critical | Rule ID:`[ARNIE_SSRF_REQUEST_RATE]`
- **HTTP client configuration** - pre-configure HTTP clients with security defaults and restricted access | Rule ID:`[ARNIE_SSRF_HTTP_CLIENT]`
- **Request middleware** - validate all outbound URLs, headers, and parameters before transmission | Rule ID:`[ARNIE_SSRF_REQUEST]`
- **Proxy validation** - proxy external requests through validation layer with security checks | Rule ID:`[ARNIE_SSRF_PROXY_VALIDATION]`
- **Protocol restrictions** - allow only safe protocols (HTTP/HTTPS) and block dangerous schemes (file, ftp, gopher), unless explicitly specified in the context | Rule ID:`[ARNIE_SSRF_PROTOCOL_RESTRICTIONS]`

### RCE Prevention
**Critical measures to prevent code execution attacks:**
- **Command execution** - use safer execution methods with argument arrays instead of shell strings | Rule ID:`[ARNIE_RCE_COMMAND_EXECUTION]`
- **Argument sanitization** - validate and escape shell arguments, removing dangerous characters (;, &, |, `, $) | Rule ID:`[ARNIE_RCE_ARGUMENT_SANITIZATION]`
- **Path validation** - ensure executables are from trusted directories and validate against allowlist | Rule ID:`[ARNIE_RCE_PATH_VALIDATION]`
- **Function replacement** - replace dangerous functions (eval, exec, system calls) with safer alternatives | Rule ID:`[ARNIE_RCE_REPLACEMENT]`
- **Sandboxed evaluation** - if code evaluation required, use restricted execution contexts with limited permissions | Rule ID:`[ARNIE_RCE_SANDBOXED_EVALUATION]`
- **Pattern detection** - scan input and code for dangerous patterns (eval, exec, import, require) before execution, only where it seems to be critical and only if the context about it can be inferred | Rule ID:`[ARNIE_RCE_PATTERN_DETECTION]`
- **Template security** - use template engines with auto-escaping, safe defaults, and syntax validation | Rule ID:`[ARNIE_RCE_TEMPLATE_SECURITY]`
- **Sandboxed rendering** - execute template rendering in isolated environments with restricted access, if such a context can be inferred | Rule ID:`[ARNIE_RCE_SANDBOXED_RENDERING]`

### Output Encoding
**Prevent Cross-Site Scripting (XSS) through proper output encoding:**
- **Auto-escaping** - configure templating engines with automatic encoding for HTML, JavaScript, CSS, and URL contexts | Rule ID:`[ARNIE_OUTPUT_AUTO_ESCAPING]`
- **Context-aware encoding** - apply appropriate encoding based on output context (HTML entities, JavaScript escaping, URL encoding) | Rule ID:`[ARNIE_OUTPUT_CONTEXT_AWARE]`
- **HTML sanitization** - use allowlist-based sanitization libraries for rich text content with safe tag restrictions | Rule ID:`[ARNIE_OUTPUT_HTML_SANITIZATION]`
- **Content Security Policy** - implement strict CSP headers to prevent inline scripts and unauthorized resource loading | Rule ID:`[ARNIE_OUTPUT_CONTENT_SECURITY]`
- **Output validation** - validate all dynamic content before rendering to prevent injection of malicious payloads | Rule ID:`[ARNIE_OUTPUT_OUTPUT_VALIDATION]`
- **Safe rendering** - use framework-specific safe rendering functions that prevent script execution in dynamic content | Rule ID:`[ARNIE_OUTPUT_SAFE_RENDERING]`

### Secrets Management
**Secure handling of sensitive credentials and configuration data:**
- **Environment usage** - use existing environment variable patterns found in the codebase for secret access | Rule ID:`[ARNIE_SECRET_ENVIRONMENT_USAGE]`
- **Backend-only access** - create functions that prevent frontend exposure of sensitive data | Rule ID:`[ARNIE_SECRET_BACKEND_ONLY]`
- **Credential generation** - use crypto-secure random generation for API keys and passwords when needed | Rule ID:`[ARNIE_SECRET_CREDENTIAL_GENERATION]`
- **Secret validation** - validate secret format and availability before use in code | Rule ID:`[ARNIE_SECRET_SECRET_VALIDATION]`
- **Hardcoded prevention** - never embed secrets directly in code, always use configuration references | Rule ID:`[ARNIE_SECRET_HARDCODED_PREVENTION]`
- **Secret masking** - implement functions that mask secrets in logs and error messages | Rule ID:`[ARNIE_SECRET_SECRET_MASKING]`

### Error Handling
**Implement secure error handling to prevent information disclosure:**
- **Error wrapping** - wrap all external calls (database, API, file operations) with proper error handling | Rule ID:`[ARNIE_HANDLING_ERROR_WRAPPING]`
- **Generic responses** - return standardized user messages ("Operation failed", "Invalid request") without internal details | Rule ID:`[ARNIE_HANDLING_GENERIC_RESPONSES]`
- **Security logging** - log security events (failed logins, unauthorized access, suspicious patterns) with structured data | Rule ID:`[ARNIE_HANDLING_SECURITY_LOGGING]`
- **Data sanitization** - filter sensitive data (passwords, tokens, API keys, PII) from all logs and responses | Rule ID:`[ARNIE_HANDLING_DATA_SANITIZATION]`
- **Error correlation** - implement error tracking with correlation IDs for debugging without exposing internal state | Rule ID:`[ARNIE_HANDLING_ERROR_CORRELATION]`
- **Exception handling** - catch and handle all exceptions gracefully with appropriate fallback responses | Rule ID:`[ARNIE_HANDLING_EXCEPTION_HANDLING]`

### Dependency Security
**Secure dependency selection when adding or updating libraries:**
- **Existing library preference** - use libraries already present in the project instead of adding new dependencies, unless the existing code is vulnerable or deprecated | Rule ID:`[ARNIE_DEPS_EXISTING_PREFERENCE]`
- **Well-maintained libraries** - choose actively maintained packages with recent updates and large community adoption | Rule ID:`[ARNIE_DEPS_WELL_MAINTAINED]`
- **Stable versions** - use latest stable releases, avoid beta, alpha, or pre-release versions for production code | Rule ID:`[ARNIE_DEPS_STABLE_VERSIONS]`
- **Minimal dependencies** - add dependencies only when necessary, avoid libraries with excessive transitive dependencies | Rule ID:`[ARNIE_DEPS_MINIMAL_DEPENDENCIES]`
- **Security-focused libraries** - prefer libraries with good security track records and active security maintenance | Rule ID:`[ARNIE_DEPS_SECURITY_FOCUSED]`

### Cryptography
**Use proven cryptographic libraries and avoid custom implementations:**
- **Crypto libraries** - implement with well-maintained cryptographic libraries, avoid custom crypto implementations | Rule ID:`[ARNIE_CRYPTO_CRYPTO]`
- **Password hashing** - use strong algorithms (bcrypt 12+ rounds, Argon2id, scrypt) with appropriate work factors | Rule ID:`[ARNIE_CRYPTO_PASSWORD_HASHING]`
- **Data encryption** - use strong symmetric encryption (AES-256-GCM, ChaCha20-Poly1305) with secure key handling | Rule ID:`[ARNIE_CRYPTO_DATA_ENCRYPTION]`
- **Token generation** - use cryptographically secure random generators for session tokens, API keys, and nonces | Rule ID:`[ARNIE_CRYPTO_TOKEN_GENERATION]`
- **Salt generation** - use secure random values (minimum 256 bits) for unique salts per password hash | Rule ID:`[ARNIE_CRYPTO_SALT_GENERATION]`
- **Secure comparison** - use timing-safe comparison functions for comparing hashes to prevent timing attacks | Rule ID:`[ARNIE_CRYPTO_SECURE_COMPARISON]`
- **Key handling** - use existing key management patterns from the codebase, never hardcode keys | Rule ID:`[ARNIE_CRYPTO_KEY_HANDLING]`
- **Digital signatures** - use strong signature algorithms (RSA-PSS 3072+, ECDSA P-256+, Ed25519) for data integrity | Rule ID:`[ARNIE_CRYPTO_DIGITAL_SIGNATURES]`
- **Random generation** - use cryptographically secure pseudo-random number generators for all security-critical values | Rule ID:`[ARNIE_CRYPTO_RANDOM_GENERATION]`

### Data Protection
**Protect sensitive data throughout its lifecycle:**
- **Data classification** - identify and categorize sensitive data types (PII, financial, health, credentials) | Rule ID:`[ARNIE_DATA_DATA_CLASSIFICATION]`
- **Data masking** - implement field masking functions for logging, debugging, and non-production environments | Rule ID:`[ARNIE_DATA_DATA_MASKING]`
- **Data retention** - implement automated data purge scheduling with configurable retention periods | Rule ID:`[ARNIE_DATA_DATA_RETENTION]`
- **Access logging** - log all access to sensitive data with user, timestamp, and operation details | Rule ID:`[ARNIE_DATA_ACCESS_LOGGING]`
- **Data anonymization** - implement data anonymization functions for analytics and reporting | Rule ID:`[ARNIE_DATA_DATA_ANONYMIZATION]`

### Secure Communications
**Ensure all communications use secure protocols, if the context about it can be inferred:**
- **HTTPS usage** - use HTTPS URLs for all external API calls and resource requests | Rule ID:`[ARNIE_COMM_HTTPS_USAGE]`
- **Client configuration** - configure HTTP clients with SSL verification, timeout settings, and certificate validation | Rule ID:`[ARNIE_COMM_CLIENT_CONFIGURATION]`
- **Certificate validation** - implement proper certificate verification in HTTP client configurations | Rule ID:`[ARNIE_COMM_CERTIFICATE_VALIDATION]`
- **API authentication** - use secure authentication methods (OAuth 2.0, JWT, API keys) for external communications | Rule ID:`[ARNIE_COMM_API_AUTHENTICATION]`
- **Secure data transmission** - ensure sensitive data uses encryption during transmission | Rule ID:`[ARNIE_COMM_SECURE_DATA]`
- **URL validation** - validate and sanitize URLs before making external requests | Rule ID:`[ARNIE_COMM_URL_VALIDATION]`

<!-- ====== ARNICA AI CODING RULES END ====== -->
