# Authentication

#### Requirements

- Relational Database (e.g. PostgreSQL)

#### Checklist

- [ ] Users can sign-up
  - GET /sign-up
  - POST /sign-up
    - Content Type: application/json
    - Body: { email, password }
- [ ] Users can sign-in
  - GET /sign-in
  - POST /sign-in
    - Content Type: application/json
    - Body: { email, password }
- [ ] Users can sign-out
  - POST /sign-out
    - Content Type: application/json
    - Body: {}