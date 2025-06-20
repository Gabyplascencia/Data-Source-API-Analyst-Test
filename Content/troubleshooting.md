#  Troubleshooting Guide – GitHub API

This guide provides quick solutions for common issues encountered while working with the GitHub API.

---

##  401 Unauthorized

**Possible causes:**
- Invalid or expired token.
- Missing or incorrectly formatted headers.

**Solution:**
- Verify that the token is valid and has appropriate scopes.
- Use correct header format:

Authorization: Bearer <TOKEN>


---

##  403 Rate Limit Exceeded

**Possible causes:**
- The hourly request limit was exceeded.

**Solution:**
- Wait until the rate limit resets.
- Use multiple tokens or authenticated requests when possible.
- Monitor response headers:


X-RateLimit-Limit
X-RateLimit-Remaining
X-RateLimit-Reset

**Python example:**

```python
if response.status_code == 403:
    print("Rate limit reached. Try again later.")

## 404 Not Found

** Possible causes:**
- Repository or file does not exist.
- Mistyped path.

**Solution:**
 Check the owner, repo, and path values.

## Pagination Issues

**Symptom:**
- You only see part of the data (e.g., 30 results, even though there are more).

**Solution:**
- Use pagination with: 
?per_page=100&page=N

- Loop through pages until an empty response is received.

## Best Practices

- Always test endpoints using Postman or similar tools before implementing in code.

- Validate all responses using response.status_code.

- Document your API usage, logic, and edge cases clearly.


