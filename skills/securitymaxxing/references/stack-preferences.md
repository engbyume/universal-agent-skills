# Preferred web application stack

Apply these defaults when a new web product has no established stack. Existing project choices, current user direction, platform requirements, accessibility, and measured needs take precedence. Do not migrate an existing product only to match this list.

## Front end

- Prefer React with TypeScript for new web front ends. Use JavaScript where the project or integration calls for it.
- Use Tailwind CSS and shadcn/ui when they fit the product and design system.
- For hosting, compare AWS Amplify with the other cloud options. Prefer Amplify when AWS is the best functional and cost fit.
- Firecrawl is a page-extraction and crawl tool. It is not a front-end framework or hosting service.

## Back end and database

- Prefer Python, FastAPI, SQLAlchemy, and PostgreSQL for new web back ends.
- Use managed PostgreSQL within AWS, GCP, or Azure. Do not default to Supabase or a similar third-party all-in-one back-end platform.
- When AWS is the best fit, prefer RDS for PostgreSQL, ECR for container images, ECS for services, and a load balancer.
- Compare providers using the product's required features, website fit, operating effort, region, expected usage, and current official pricing. Choose the provider with the best fit and total cost for the product.

## Research and scraping

- Use Appify for general scraping and downloads when the tool is available and supports the target. Use Firecrawl for known-URL extraction, multi-page crawls, or extraction that replaces several ordinary page reads. Use ordinary web search for general research. Avoid duplicate runs.
- Before the first account-dependent Appify use, tell the user if sign-in is needed so they can authenticate through the official UI. Never ask for a password or token in chat.
- Estimate the planned Appify run and obtain approval before any specific paid usage. General willingness to pay is not approval for a specific charge.
- Keep API tokens in an approved environment or secrets manager. Never source a repository .env file.

## Analytics and observability

- Prefer PostHog for product analytics, Sentry for error monitoring, and Datadog for application and infrastructure observability.
- Add only the services the product needs. Avoid duplicate collection, unnecessary personal data, and overlapping paid features.

## Cloud access and spending

- For the first cloud account connection, tell the user before the account-dependent step so they can sign in through the official provider UI.
- Use current official documentation and pricing before choosing services. Do not provision paid resources or incur charges without approval for the specific scope and cost.
