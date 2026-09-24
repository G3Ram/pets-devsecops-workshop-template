# Optional shelter end-to-end tests

This directory contains Playwright end-to-end tests for the Tailspin Shelter website.

These are an optional maintainer extension, not participant setup. Start the learner workshop at [the bundled guide](../../../content/devsecops/0-setup.md); its required build/test work runs in Actions. Do not run the commands below as part of core Codespaces prework.

## Why it matters

Browser tests exercise the real frontend/API interaction that mocked unit tests do not cover.

## Test Files

- `homepage.spec.ts` - Tests for the main homepage functionality
- `about.spec.ts` - Tests for the about page
- `dog-details.spec.ts` - Tests for individual dog detail pages
- `api-integration.spec.ts` - Tests for API integration and error handling

## Running Tests

### Prerequisites

Make sure you have installed dependencies:
```bash
npm install
```

You also need Python 3 with Flask dependencies installed:
```bash
pip install -r ../server/requirements.txt
```

### Running Tests

```bash
# Run all tests
npm run test:e2e

# Run tests with UI mode (for debugging)
npm run test:e2e:ui

# Run tests in headed mode (see browser)
npm run test:e2e:headed

# Debug tests
npm run test:e2e:debug
```

## Test Architecture

Tests run against the real Flask server with a separate test database seeded with deterministic data. When Playwright starts, it:

1. Seeds a test database (`e2e_test_dogshelter.db` in the server directory) with known dogs and breeds
2. Starts the Flask server using the test database
3. Starts the Astro dev server pointing at the Flask server
4. Runs all e2e tests against the live application

From the client root, the test data is defined in `../server/utils/seed_test_database.py`.

## Test Coverage

The tests cover the following core functionality:

### Homepage Tests
- Page loads with correct title and content
- Dog list displays properly

### About Page Tests
- About page content displays correctly
- Navigation back to homepage works

### Dog Details Tests
- Navigation from homepage to dog details
- Full dog details display correctly
- Navigation back from dog details to homepage
- Handling of invalid dog IDs

### API Integration Tests
- Dogs render correctly on the homepage
- Dog details render correctly
- 404 handling for non-existent dogs
- Navigation from card to detail page

## Configuration

Tests are configured in `../playwright.config.ts` and automatically start the Flask and Astro servers before running tests.

The tests run against:
- Client (Astro): http://localhost:4321
- Server (Flask): http://localhost:5100

## Checkpoint and resources

For separately approved maintainer testing, inspect the Playwright report and keep forwarded ports private. This is not a production deployment. See [Playwright documentation](https://playwright.dev/docs/intro).