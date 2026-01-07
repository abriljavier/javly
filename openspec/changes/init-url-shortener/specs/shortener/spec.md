## ADDED Requirements

### Requirement: URL Shortening
The system SHALL accept a valid URL from the user and return a unique shortened code.

#### Scenario: Successfully shorten a URL
- **WHEN** a user submits "https://google.com"
- **THEN** the system returns a short code (e.g., "ab12cd")
- **AND** the code is persisted in the database linked to the original URL

#### Scenario: Invalid URL
- **WHEN** a user submits "not-a-url"
- **THEN** the system returns an error message indicating invalid format

### Requirement: URL Redirection
The system SHALL redirect users who visit a short link to the original long URL.

#### Scenario: Redirect existing link
- **WHEN** a user visits "/ab12cd"
- **AND** "ab12cd" exists in the database
- **THEN** the user is redirected to "https://google.com" (307 Temporary Redirect)

#### Scenario: Link not found
- **WHEN** a user visits "/unknown"
- **THEN** the system displays a 404 Not Found page
