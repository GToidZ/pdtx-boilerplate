# pdtx-boilerplate (Postgres-ready + Django + Tailwind + htmx)
A Django boilerplate made with *Modernity* in mind.

# Tech Stack
* `Django 4.0.x` - a web framework written in Python; you also will write apps in Python.
* `Tailwind.css` - a CSS utility framework that allows frontend customizations with HTML classes; and builds what-you-only-need on production.
* `htmx` - a supercharger for websites that came in HTML utility tags, make AJAX requests, capture many events and replace HTML content without actually writing JS.

# Prerequisites
* `Python >= 3.8`
* `Node.js >= 16`
* `Postgres Server + Client Library` *see [docs][psycopg2-docs] for more info*
## For building `psycopg2` for production
* `gcc` or any C compiler
* `Python headers` usually in `python3-dev` package
* `libpq-dev`

# Setting Up
To setup this boilerplate with the most stable version, head to the Releases tab and get the latest one.

1. Setup your `.env` file to store enviroment variables. Please refer to `.env.example`
2. Create a new Python virtual environment inside the directory,
   ```sh
   python3 -m venv .venv
   
   # or on Windows...
   python -m venv .venv
   ```
3. Source or activate your virtual environment.
4. Install Python dependencies,
   ```sh
   pip install -r requirements.txt

   # or if you're installing for production...
   pip install -r requirements/prod.txt
   ```
5. Navigate to `./theme/static_src/`.
6. Install Node packages required,
   ```sh
   npm install
   ```
7. Navigate back to the root of directory.
8. Run the server to test setup, you will need to run two servers (concurrent),
   ```sh
   python3 ./manage.py tailwind start   # runs Tailwind.css server
   python3 ./manage.py runserver        # runs Django server
   ```

[psycopg2-docs]: https://www.psycopg.org/docs/install.html#prerequisites
