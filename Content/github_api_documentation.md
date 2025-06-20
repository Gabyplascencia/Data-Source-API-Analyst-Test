# GitHub API Documentation Used
This documentation details the main GitHub REST API endpoints used during task development, as well as key considerations for their consumption.

---

## Authentication

A **Personal Access Token (PAT)** is required to authenticate requests to the GitHub API. Include the following headers in each request:

```http
Authorization: Bearer <TOKEN>
Accept: application/vnd.github+json
X-GitHub-Api-Version: 2022-11-28
```
---

## Search Public Repositories

**Endpoint:**

**Description:**  
Performs a search query to find public repositories using specific keywords or filters.

**Common query parameters:**

| Parameter | Description                          |
|-----------|--------------------------------------|
| `q`       | Search query (e.g., keywords, language) |
| `sort`    | Sort order (e.g., stars, forks)      |
| `order`   | Sorting direction (`asc` or `desc`)  |

**Example request:**

https://api.github.com/search/repositories?q=data+language:python&sort=stars&order=desc

---

## Retrieve Commits from a Repository

 **Endpoint:**
 
 **Description:**  
Retrieves a list of commits from a specific repository.

**Optional query parameters:**

| Parameter | Description                  |
|-----------|------------------------------|
| `sha`     | Commit SHA or branch name    |
| `path`    | File path to filter commits  |
| `since`   | Start date (ISO 8601 format) |
| `until`   | End date (ISO 8601 format)   |

**Example:**

https://api.github.com/repos/pandas-dev/pandas/commits?per_page=100&page=1

---

## Retrieve File or Directory Content

**Endpoint:**

GET /repos/{owner}/{repo}/contents/{path}

**Description:**  
Returns the contents of a file or directory in a repository. If a file is requested, the response includes the content encoded in Base64.

**Example:**

https://api.github.com/repos/pandas-dev/pandas/contents/README.md

---

## Key Considerations

### Pagination
Most endpoints return 30 results per page by default. Use the following parameters to control pagination:

?per_page=100&page=1

### Rate Limits
- **Without authentication:** 60 requests/hour.
- **With token:** Up to 5,000 requests/hour.
- Use response headers to monitor limits:
  - `X-RateLimit-Limit`
  - `X-RateLimit-Remaining`
  - `X-RateLimit-Reset`

---

## Common Error Handling

- **401 Unauthorized:** Invalid or missing authentication token.
- **403 Rate Limit Exceeded:** Too many requests in a short time.
- **404 Not Found:** The requested resource does not exist or the path is incorrect.

---

## Official GitHub REST API Documentation

[https://docs.github.com/en/rest](https://docs.github.com/en/rest)
