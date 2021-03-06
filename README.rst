Teams Happiness
===============

A simple Django application to allow daily checkins and monitoring of your teams happiness.

.. image:: https://img.shields.io/badge/built%20with-Cookiecutter%20Django-ff69b4.svg
     :target: https://github.com/pydanny/cookiecutter-django/
     :alt: Built with Cookiecutter Django
.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
     :target: https://github.com/ambv/black
     :alt: Black code style

Sample request/output
---------------------

Given we have a couple of teams and users, make this request to fetch happiness statictics by user::

    $ curl -H 'Accept: application/json; indent=4' -u "team-user-1":testPassword http://127.0.0.1:8000/api/v1/users/2/
    {
        "id": 2,
        "username": "team-user-1",
        "first_name": "",
        "last_name": "",
        "happiness_level": 3,
        "statistics": {
            "user_count_by_happiness_level": [
                {
                    "happiness_level": 3,
                    "user_count": 1
                },
                {
                    "happiness_level": 5,
                    "user_count": 1
                }
            ],
            "average_team_happiness": 4.0
        },
        "team": {
            "id": 1,
            "name": "team1"
        }
    }

Settings
--------

Moved to settings_.

.. _settings: http://cookiecutter-django.readthedocs.io/en/latest/settings.html


Getting Up and Running Locally
------------------------------

See here run_locally_.

.. _run_locally: https://cookiecutter-django.readthedocs.io/en/latest/developing-locally.html


Basic Commands
--------------

Setting Up Your Users
^^^^^^^^^^^^^^^^^^^^^

* To create a **normal user account**, just go to Sign Up and fill out the form. Once you submit it, you'll see a "Verify Your E-mail Address" page. Go to your console to see a simulated email verification message. Copy the link into your browser. Now the user's email should be verified and ready to go.

* To create an **superuser account**, use this command::

    $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and your superuser logged in on Firefox (or similar), so that you can see how the site behaves for both kinds of users.

Type checks
^^^^^^^^^^^

Running type checks with mypy:

::

  $ mypy teams_happiness

Test coverage
^^^^^^^^^^^^^

To run the tests, check your test coverage, and generate an HTML coverage report::

    $ coverage run -m pytest
    $ coverage html
    $ open htmlcov/index.html

Running tests with py.test
~~~~~~~~~~~~~~~~~~~~~~~~~~

::

  $ pytest

