You use Nginx because production applications need a smart traffic manager in front of them.

For the frontend (React):

Nginx serves static files (HTML, JS, CSS) very efficiently.

It handles caching and compression.

It delivers content faster than an application server.

For the backend (FastAPI):

Nginx acts as a reverse proxy.

It handles HTTPS (SSL termination).

It load balances if you run multiple backend instances.

It adds a security layer (rate limiting, request filtering).

So in production:

Internet → Nginx → Frontend (static files)
                    Backend (API)

In simple terms:

Nginx manages traffic and security.
Frontend serves UI.
Backend runs business logic.