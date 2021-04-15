# Configuration

Most of the configuration for environments is established in helm templates within `./helm`.

## Environment Variables

| Variable | Description | Example |
|:---------|:------------|:--------|
| `DJANGO_SETTINGS_MODULE` | Django Setting module path | `django_settings.settings.dev`
| `ENABLE_DEBUG_MODE` | Enable Django's debug features. `Y` or `N` | `Y`
| `ENABLE_DEBUG_TOOLBAR` | Enable the `django-debug-toolbar` plugin. `Y` or `N` | `N`
| `DB_TYPE` | Database type. Either `sqlite`, `postgres`, or `N/A` | `postgres`
| `WAIT_FOR_DB` | The container should wait for a database to be available before continuing. `Y` or `N` | `Y`
| `DB_HOST` | Postgres server host to connect to  | `nhsuk-dev.database.windows.net`
| `DB_NAME` | Postgres database name | `nhsuk-cms`
| `DB_USER` | Postgres database username | `wagtail`
| `DB_PASS` | Postgres database password | `N!ce'n'S3cUr3`
| `CREATE_SUPERUSER` | Create a wagtail superuser user. `Y` or `N` | `N`
| `WAGTAIL_USER` | Wagtail superuser user | `wagtail`
| `WAGTAIL_PASS` | Wagtail superuser password | `wagtail`
| `AZURE_ACCOUNT_NAME` | Azure storage account used to store media | `betastore`
| `AZURE_ACCOUNT_KEY` | Azure storage account key, need to access above account
| `AZURE_CONTAINER` | Which Azure container to use | `dev`
| `AZURE_PRIVATE_ENDPOINT` | HTTP endpoint used for uploading assets to blob storage | `https://dev.blob.core.windows.net`
| `AZURE_PUBLIC_ENDPOINT` | HTTP endpoint to serve public assets through | `https://assets.nhs.uk`
| `AZURE_SSL` | Use SSL for blob storage connection. Should always be `Y` unless local blob emulation is being used. `Y` or `N` | `Y`
| `AZURE_AD_CLIENT_ID`  | Azure AD Client ID used for oauth. No azure login button will show if this variable is undefined
| `AZURE_AD_CLIENT_KEY` | Azure AD Client Key used for oauth
| `WAIT_FOR_MIGRATIONS` | The container should wait for database migrations to be complete before continuing. `Y` or `N` | `Y`
| `RUN_MIGRATIONS` | Run DB migration. `Y` or `N` | `Y` |
| `HOST` | Domain on which to serve the nhs.uk site | `nhsuk.localhost`
| `BANNER_API_URL` | API URL for the site-wide banner |
| `BANNER_TEST_API_URL` | API URL for the site-wide banner for testing new banner configs |
| `SUGGESTIONS_TEST_HOST` | Domain to fetch auto-suggest search results from (only needed in test environments)
| `SEARCH_TEST_HOST` | Domain to fetch search results from (only needed in test environments)
| `REDIS_URL` | Overrides the default Redis URL if set | `redis://redis:6379`
| `DEVELOPER_PORTAL_ENDPOINT` | URL endpoint for notifying dev.api users of page changes
| `NOTIFY_AUTH_CODE` | Authentication code for the notify endpoint
| `CACHE_FLUSH_API_URL` | URL endpoint for the cache-flush API
| `CACHE_FLUSH_API_KEY` | API key for the cache-flush API
| `CACHE_FLUSH_API_ENVIRONMENT` | Either `production` or `staging` depending on which akamai environment should be flushed | `staging`
| `USER_FEEDBACK_STORE_ENDPOINT` | Backend to post user feedback to
| `HOTJAR_ID` | Hotjar account ID
| `COOKIE_SCRIPT_URL` | URL of the javascript which is used for cookie settings | `//assets.nhs.uk/scripts/cookie-consent.js`
| `APP_VERSION` | Unique string to identify this code release and as a cache token | `20.18.1`
| `BRIGHTCOVE_CLIENT_SECRET` | Secret to use for authenticating with the brightcove API
| `BRIGHTCOVE_CLIENT_ID` | ID to use for authenticating with the brightcove API
| `BRIGHTCOVE_ACCOUNT_ID` | ID of the brightcove account to use on the frontend
| `BRIGHTCOVE_VIDEOS_IMPORT` | Import all videos from brightcove when container starts. `Y` or `N`
| `BRIGHTCOVE_VIDEOS_SYNC` | Register with the brightcove sync API to get updates when videos change. `Y` or `N`
| `BRIGHTCOVE_PLAYER` | ID of the brightcove player to use on the frontend
| `CAMPAIGNS_EVENT_API_ENDPOINT` | Backend to record campaigns events


<br/>
