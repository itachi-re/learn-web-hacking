# Phase 0: Foundation (2-3 Weeks)

> **Goal**: Understand how web applications work at a fundamental level

Before exploiting vulnerabilities, you must understand the underlying technologies. This phase builds the essential knowledge required for effective web hacking.

---

## 📋 Learning Objectives

By the end of this phase, you should be able to:

- ✅ Explain the HTTP/HTTPS protocol in detail
- ✅ Analyze HTTP requests and responses
- ✅ Understand authentication mechanisms
- ✅ Explain Same-Origin Policy and CORS
- ✅ Describe how web applications are structured
- ✅ Work comfortably with JSON and APIs

---

## 📚 Week 1: HTTP Protocol Deep Dive

### Day 1-2: HTTP Basics

**Topics to Learn:**
- What is HTTP and how it works
- Request methods (GET, POST, PUT, DELETE, PATCH, OPTIONS, HEAD)
- HTTP versions (HTTP/1.1, HTTP/2, HTTP/3)
- Client-server architecture

**Resources:**
- [MDN: HTTP Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
- [PortSwigger: HTTP Basics](https://portswigger.net/web-security/getting-started)
- [HTTP Made Really Easy](https://www.jmarshall.com/easy/http/)

**Practical Exercise:**
```bash
# Use curl to make HTTP requests
curl -v https://example.com
curl -X POST https://httpbin.org/post -d "key=value"
curl -H "Custom-Header: Value" https://httpbin.org/headers
```

**Lab Practice:**
- PortSwigger: HTTP Basics Labs (ALL)

---

### Day 3-4: Request & Response Anatomy

**Topics to Learn:**
- HTTP Headers (User-Agent, Host, Referer, Content-Type, etc.)
- Request body formats (form data, JSON, XML)
- Status codes (1xx, 2xx, 3xx, 4xx, 5xx)
- Response headers (Set-Cookie, Location, Content-Type)

**Key Headers to Understand:**

| Header | Purpose | Example |
|--------|---------|---------|
| Host | Target domain | `Host: example.com` |
| User-Agent | Browser identity | `User-Agent: Mozilla/5.0...` |
| Cookie | Session data | `Cookie: session=abc123` |
| Content-Type | Body format | `Content-Type: application/json` |
| Authorization | Auth credentials | `Authorization: Bearer token` |

**Practical Exercise:**
```bash
# Analyze headers
curl -I https://example.com

# Send custom headers
curl -H "Accept: application/json" \
     -H "Authorization: Bearer token" \
     https://api.example.com/data
```

**Lab Practice:**
- Analyze 10 different websites using browser DevTools (Network tab)
- Identify all request/response headers
- Note different Content-Types used

---

### Day 5-7: Understanding URLs

**Topics to Learn:**
- URL structure (protocol, domain, path, query, fragment)
- Query parameters and their encoding
- URL encoding (%20, %3A, etc.)
- Absolute vs relative URLs

**URL Anatomy:**
```
https://example.com:443/path/to/resource?key=value&foo=bar#section
  |      |         |   |                |              |
protocol hostname port     path       query params   fragment
```

**Practical Exercise:**
```python
# Python URL parsing
from urllib.parse import urlparse, parse_qs

url = "https://example.com/search?q=web+hacking&page=2"
parsed = urlparse(url)
print(f"Scheme: {parsed.scheme}")
print(f"Domain: {parsed.netloc}")
print(f"Path: {parsed.path}")
print(f"Query: {parsed.query}")
print(f"Params: {parse_qs(parsed.query)}")
```

**Challenge:**
- Parse 10 different URLs manually
- Understand parameter injection points

---

## 📚 Week 2: Authentication & Sessions

### Day 8-10: Cookies & Sessions

**Topics to Learn:**
- What cookies are and how they work
- Session management
- Cookie attributes (Domain, Path, Secure, HttpOnly, SameSite)
- Session fixation and hijacking concepts

**Cookie Attributes:**

```
Set-Cookie: sessionId=abc123; 
            Domain=example.com; 
            Path=/; 
            Secure; 
            HttpOnly; 
            SameSite=Strict
```

| Attribute | Purpose | Security Impact |
|-----------|---------|-----------------|
| Secure | HTTPS only | Prevents interception |
| HttpOnly | No JavaScript access | Prevents XSS theft |
| SameSite | Cross-site restrictions | Prevents CSRF |

**Practical Exercise:**
1. Open browser DevTools → Application → Cookies
2. Analyze cookies on 5 major websites
3. Modify cookie values and observe behavior
4. Try accessing sites with expired/deleted cookies

**Lab Practice:**
- PortSwigger: Cookies & Sessions Labs

---

### Day 11-12: Authentication Mechanisms

**Topics to Learn:**
- Basic Authentication
- Form-based authentication
- Token-based authentication (JWT)
- OAuth 2.0 basics
- Multi-factor authentication (MFA)

**Authentication Flow Example:**
```
1. User enters credentials
2. Server validates
3. Server creates session/token
4. Server sends Set-Cookie or token
5. Client includes cookie/token in subsequent requests
6. Server validates cookie/token
```

**Practical Exercise:**
- Implement basic login in a test application
- Capture and analyze authentication requests in Burp Suite
- Understand token structure (JWT.io)

**Lab Practice:**
- PortSwigger: Authentication Labs (Apprentice level)

---

### Day 13-14: Authorization vs Authentication

**Critical Distinction:**

| Authentication | Authorization |
|----------------|---------------|
| "Who are you?" | "What can you do?" |
| Login process | Access control |
| Credentials check | Permission check |
| Fails → 401 | Fails → 403 |

**Topics to Learn:**
- Role-based access control (RBAC)
- Access control lists (ACLs)
- Horizontal vs vertical privilege escalation
- Common authorization flaws

**Practical Exercise:**
- Create a diagram showing auth vs authz flow
- Identify authorization checks in web applications
- Understand where access control fails

**Lab Practice:**
- PortSwigger: Access Control Labs (start with Apprentice)

---

## 📚 Week 3: Browser Security & APIs

### Day 15-17: Same-Origin Policy (SOP)

**Topics to Learn:**
- What is SOP and why it exists
- Origin definition (protocol + domain + port)
- SOP restrictions and exceptions
- How SOP prevents attacks

**Origin Examples:**
```
https://example.com:443       ← Origin 1
https://example.com:8080      ← Different (port)
https://api.example.com:443   ← Different (subdomain)
http://example.com:443        ← Different (protocol)
```

**Key Understanding:**
- JavaScript from one origin cannot read data from another origin
- SOP is the foundation of web security
- Understanding SOP is critical for XSS and CORS attacks

**Practical Exercise:**
```html
<!-- Test SOP in browser console -->
<script>
  // Try fetching from different origin
  fetch('https://api.github.com/users/github')
    .then(r => r.json())
    .then(d => console.log(d))
    .catch(e => console.error('SOP blocked:', e));
</script>
```

**Lab Practice:**
- PortSwigger: SOP Labs

---

### Day 18-19: Cross-Origin Resource Sharing (CORS)

**Topics to Learn:**
- What CORS is and how it works
- CORS headers (Access-Control-Allow-Origin, etc.)
- Preflight requests (OPTIONS)
- CORS misconfigurations

**CORS Headers:**
```
Access-Control-Allow-Origin: https://trusted.com
Access-Control-Allow-Methods: GET, POST
Access-Control-Allow-Headers: Content-Type
Access-Control-Allow-Credentials: true
```

**Practical Exercise:**
- Set up a simple CORS-enabled API
- Test CORS with different origins
- Identify misconfigured CORS on real sites

**Lab Practice:**
- PortSwigger: CORS Labs

---

### Day 20-21: RESTful APIs & JSON

**Topics to Learn:**
- REST principles
- JSON structure and parsing
- API authentication (API keys, Bearer tokens)
- Common API endpoints structure

**REST Conventions:**
```
GET    /api/users       → List all users
GET    /api/users/123   → Get user 123
POST   /api/users       → Create user
PUT    /api/users/123   → Update user 123
DELETE /api/users/123   → Delete user 123
```

**JSON Basics:**
```json
{
  "user": {
    "id": 123,
    "name": "John Doe",
    "email": "john@example.com",
    "roles": ["user", "admin"]
  }
}
```

**Practical Exercise:**
```python
import requests
import json

# GET request
response = requests.get('https://api.github.com/users/github')
data = response.json()
print(json.dumps(data, indent=2))

# POST request
payload = {"name": "test", "email": "test@example.com"}
response = requests.post('https://httpbin.org/post', json=payload)
print(response.status_code)
```

**Challenge:**
- Interact with 3 public APIs (GitHub, JSONPlaceholder, HTTPBin)
- Parse and manipulate JSON responses
- Understand API error responses

---

## 🛠 Tools to Install This Phase

```bash
# Browser with DevTools (Firefox/Chrome)
# Already installed

# Burp Suite Community Edition
sudo apt update
sudo apt install burpsuite

# curl for command-line HTTP
sudo apt install curl

# Python with requests library
pip3 install requests
```

---

## ✅ Phase 0 Checklist

Before moving to Phase 1, ensure you can:

- [ ] Explain HTTP request/response cycle
- [ ] Identify and modify HTTP headers
- [ ] Understand cookie attributes and security implications
- [ ] Differentiate authentication from authorization
- [ ] Explain Same-Origin Policy
- [ ] Understand CORS and its purpose
- [ ] Parse and manipulate JSON data
- [ ] Use Burp Suite to intercept HTTP traffic
- [ ] Use curl to craft HTTP requests
- [ ] Analyze web traffic in browser DevTools

---

## 📝 Phase 0 Project

**Build a Simple HTTP Logger**

Create a Python script that:
1. Makes HTTP requests to a target URL
2. Logs all request headers
3. Logs all response headers
4. Saves cookies
5. Displays response body

```python
import requests

def http_logger(url):
    response = requests.get(url)
    
    print("=== REQUEST HEADERS ===")
    print(response.request.headers)
    
    print("\n=== RESPONSE HEADERS ===")
    print(response.headers)
    
    print("\n=== COOKIES ===")
    print(response.cookies)
    
    print("\n=== RESPONSE BODY (first 200 chars) ===")
    print(response.text[:200])

if __name__ == "__main__":
    http_logger("https://example.com")
```

---

## 🎯 Next Steps

Once you complete Phase 0:
1. Review all concepts you learned
2. Create a cheat sheet of HTTP headers
3. Move to [Phase 1: Core Vulnerabilities](phase-1-core-vulnerabilities.md)

**Remember**: These fundamentals are crucial. Don't rush through this phase. Everything builds on this foundation.

---

[← Back to Main Guide](../README.md) | [Next: Phase 1 →](phase-1-core-vulnerabilities.md)