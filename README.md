# pdtx-boilerplate (Postgres-ready + Django + Tailwind + htmx)
A Django boilerplate made with *Modernity* in mind.

# Tech Stack
* `Django 4.0.x` - a web framework written in Python; you also will write apps in Python.
* `Tailwind.css` - a CSS utility framework that allows frontend customizations with HTML classes; and builds what-you-only-need on production.
* `htmx` - a supercharger for websites that came in HTML utility tags, make AJAX requests, capture many events and replace HTML content without actually writing JS.

# Prerequisites
* `Python >= 3.8`
* `Node.js >= 16 + npm`
* `Postgres Server + Client Library` *see [docs][psycopg2-docs] for more info*
## For building `psycopg2` for production
* `gcc` or any C compiler
* `Python headers` usually in `python3-dev` package
* `libpq-dev`

# Setting Up
To setup this boilerplate with the most stable version, head to the Releases tab and get the latest one.

1. Setup your `.env` file to store enviroment variables. Please refer to `.env.example`
   * Make sure to put the absolute path of `npm` for `NPM_BIN_PATH`!
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

After completing the setup you can consult the [materials](#reading-materials) to get started on developing a supercharged Django app!

# Type Checking
**Added in Revision 3**

Type checking is a powerful tool for developers to know what they're doing. In Django, types are pretty much
generic especially, `RelatedManager`, `ForeignKey` etc.

To solve the problem of most type checker not being able to understand Django's typing, we must use an extension to
the source code, "stubs."

This boilerplate uses `django-types` package from PyPI as stubs and it needs some workarounds to work properly.

Consult the [Github Repository][django-types] for more info.

# Reading Materials
> Don’t keep "trying" solutions until you find one that works. Take the time to find the correct solution. *-- Steve Maguire*
* [Django Documentation][django-docs]
* [Tailwind.css Documentation][tailwind-docs]
* [htmx Documentation][htmx-docs]

There are also materials for specific Python packages for app dependencies,
* [django-tailwind][django-tailwind]
* [django-htmx][django-htmx]

# Video Materials
* [What you can do with Django + HTMX][django-htmx-playlist]

# Additional Info
* If you're ready to step up your game and use some satisfying functions from `django.contrib.postgres`, set `LOCAL_DB` to "False"<br>
  Note: you'll lose support for other database providers but, the application will be much more easier to be used with Postgres.

[psycopg2-docs]: https://www.psycopg.org/docs/install.html#prerequisites
[django-docs]: https://docs.djangoproject.com/en/
[tailwind-docs]: https://tailwindcss.com/docs/utility-first
[htmx-docs]: https://htmx.org/docs/
[django-tailwind]: https://django-tailwind.readthedocs.io/en/latest/
[django-htmx]: https://django-htmx.readthedocs.io/en/latest/
[django-types]: https://github.com/sbdchd/django-types
[django-htmx-playlist]: https://www.youtube.com/playlist?list=PL-2EBeDYMIbRByZ8GXhcnQSuv2dog4JxY



