# Authentication

## Requirements

- Relational Database (e.g. PostgreSQL)
- Web Server (e.g. Express.js, Koa.js, uWebSockets.js)

## Core Features

#### Users can sign-up

- GET /sign-up
- POST /sign-up
  - Content Type: application/json
  - Body: { name, email, password }
- Server-side: validate email
- Server-side: validate password
- Server-side: use 

#### Users can sign-in

- GET /sign-in
- POST /sign-in
  - Content Type: application/json
  - Body: { email, password }

#### Users can view their account

- GET /account

#### Users can sign-out

- POST /sign-out
  - Content Type: application/json
  - Body: { }

## Improvements

#### Users can recover their account

- GET /recovery
- POST /recovery/send-recovery-link
  - Content Type: application/json
  - Body: { email }
- GET /recovery?email=user@example.com&recovery_code=recovery_code
- POST /recovery/send-recovery-link
  - Content Type: application/json
  - Body: { email, recovery_code, password }

#### Users can update their account

- POST /account/update-name
  - Content Type: application/json
  - Body: { name }
- POST /account/update-password
  - Content Type: application/json
  - Body: { current_password, new_password }

#### Use simple fields for names

- https://www.w3.org/International/questions/qa-personal-names

#### Use Unicode Case-Folding

- https://www.w3.org/TR/charmod-norm/#definitionCaseFolding
- https://github.com/joshxyzhimself/modules/blob/main/casefold.mjs
- https://github.com/joshxyzhimself/modules/blob/main/casefold.test.mjs

#### Use Unicode Normalization with NFKC


```
NFKC is the preferred form for identifiers, especially where there are security concerns.
```

- https://www.w3.org/TR/charmod-norm/#unicodeNormalization
- https://unicode.org/faq/normalization.html
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize

#### Use Latacora's Password Handling Recommendations

```
Latacora, 2018: In order of preference, use scrypt, argon2, bcrypt, and then if nothing else is available PBKDF2.
```

- https://latacora.micro.blog/2018/04/03/cryptographic-right-answers.html#password-handling

#### Use OWASP's Authentication Checklist

- https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html