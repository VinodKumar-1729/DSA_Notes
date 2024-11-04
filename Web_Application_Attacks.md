
#### 1. Cross-Site Scripting (XSS)

**Definition:**  
Cross-Site Scripting (XSS) is a client-side code injection vulnerability where attackers inject malicious scripts into web pages that are viewed by unsuspecting users.

**Types of XSS:**
- **Stored XSS** (Persistent XSS):  
  - The malicious script is stored on the target server's database, such as in a comment field or user profile section.  
  - When other users access the page, the script executes, potentially stealing cookies, session tokens, or redirecting users to malicious sites.
  
- **Reflected XSS:**  
  - The attacker sends a specially crafted link to a user.  
  - When the user clicks on the link, the server “reflects” the script back in the HTTP response, executing it in the user's browser.
  
- **DOM-based XSS:**  
  - Affects the Document Object Model (DOM) on the client side, where the script does not involve server interaction directly.
  - The vulnerability is in the frontend JavaScript code, making it harder to detect with traditional server-side controls.

**Impact:**  
- Session hijacking, website defacement, redirection to malicious sites, and theft of user credentials.

**Prevention:**  
- **Input Validation:** Validate all user inputs for acceptable formats and characters.
- **Output Encoding:** Convert characters to prevent script execution.
- **Content Security Policy (CSP):** Restrict the sources from which scripts can be loaded, limiting the damage of XSS payloads.

**Advanced Exam Insight:**  
- **Security Headers:** Beyond CSP, use other security headers such as `X-XSS-Protection` (though legacy) and `X-Content-Type-Options` to add another layer of defense.
- **Scripting Libraries:** Leveraging libraries like `DOMPurify` can sanitize inputs for frontend frameworks.

---

#### 2. Cross-Site Request Forgery (CSRF)

**Definition:**  
CSRF occurs when an attacker tricks an authenticated user into performing unintended actions on a web application.

**Mechanism:**  
- The attacker crafts a request that triggers an action (e.g., transferring funds).
- If the user is authenticated on the target site, the action may execute without their knowledge or consent, leveraging the user’s trust in the legitimate application.

**Impact:**  
- Can lead to unauthorized actions, such as financial transactions, data modifications, or changes to user settings.

**Prevention:**  
- **Anti-CSRF Tokens:** Unique tokens that verify the request’s origin.
- **HTTP Referer Header Validation:** Check that requests originate from trusted sources.
- **SameSite Cookie Attribute:** Restricts cookies to first-party contexts, minimizing cross-site access.

**Advanced Exam Insight:**  
- **Double Submit Cookie Pattern:** Another CSRF mitigation where an additional cookie is sent with every request and compared with a token in the HTTP request.
- **Origin Header Check:** More secure than Referer, as it confirms the source of the request if available.

---

#### 3. Injection Attacks

**Definition:**  
Injection attacks involve sending untrusted data to an interpreter as part of a command or query, often manipulating or altering application behavior.

**Types of Injection Attacks:**
- **SQL Injection (SQLi):**  
  - SQL code is inserted into a query to manipulate the database.
  - Example: Logging in as an administrator without knowing the password by entering a crafted SQL statement.
  
- **Command Injection:**  
  - Injects system commands, manipulating the host OS through a vulnerable application.
  
- **XML Injection:**  
  - Manipulates XML data processing to alter application behavior, such as unauthorized access or privilege escalation.

**Impact:**  
- Data theft, loss of data integrity, unauthorized access, or even system compromise.

**Prevention:**  
- **Prepared Statements:** Parameterized queries that avoid executing raw SQL commands.
- **ORM Frameworks:** Abstract away database interactions to prevent direct manipulation.
- **Input Validation:** Restrict inputs to expected data formats and lengths.

**Advanced Exam Insight:**  
- **Blind SQL Injection:** A technique where the attacker infers data based on true/false responses, making it stealthier and harder to detect.
- **Second-Order SQL Injection:** Attackers insert harmful code in non-executed locations, which only activates later when the data is used in other queries.

---

#### 4. Distributed Denial-of-Service (DDoS)

**Definition:**  
DDoS attacks are coordinated from multiple sources, overwhelming the server with traffic and disrupting legitimate access.

**Mechanism:**  
- Attackers use botnets (a network of compromised devices) to generate high traffic volume, depleting server resources and causing downtime.

**Impact:**  
- Can result in extended downtime, financial loss, and potential data loss, especially for businesses with service-based models.

**Prevention:**  
- **Rate Limiting:** Restricts the number of requests per user.
- **Content Delivery Networks (CDN):** CDNs cache and distribute content, reducing direct traffic to the server.
- **Traffic Analysis Tools:** Monitor and mitigate suspicious activity patterns, like spikes or repeated requests from unusual locations.

**Advanced Exam Insight:**  
- **Application Layer (Layer 7) DDoS:** Targets specific application services, requiring more sophisticated filtering.
- **DDoS-as-a-Service:** Some attackers rent out botnets, allowing others to launch attacks, highlighting the need for layered DDoS defenses.

---

#### 5. Brute Force Attack

**Definition:**  
Brute force attacks are attempts to gain unauthorized access by systematically guessing passwords or encryption keys.

**Mechanism:**  
- Attackers try every possible password or key until the correct one is found, often automated to speed up the process.

**Impact:**  
- Compromises accounts or systems, potentially leading to unauthorized access to sensitive data.

**Prevention:**  
- **Strong Password Policies:** Require complex passwords with a mix of characters.
- **Account Lockout Policies:** Lock accounts after repeated failed login attempts.
- **Multi-Factor Authentication (MFA):** Adds a layer of security, often making brute-force attacks impractical.

**Advanced Exam Insight:**  
- **Credential Stuffing:** Using previously stolen credentials in brute-force style across multiple accounts.
- **Dictionary Attack:** A specific brute-force method that uses common words and phrases instead of random characters, highlighting the importance of unique passwords.

---

### Additional Web Application Attack Defense Mechanisms

- **Web Application Firewalls (WAFs):** Filters and monitors HTTP traffic to and from a web application, defending against multiple attack vectors.
- **Secure Development Lifecycle (SDLC):** Integrating security at each stage of development to preemptively address vulnerabilities.
- **Regular Security Audits and Penetration Testing:** Identifies existing vulnerabilities before they are exploited in a live environment.
