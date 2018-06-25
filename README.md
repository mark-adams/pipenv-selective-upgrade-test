This is an example repository to show that there might be a problem with pipenv

1. Install the dependencies

```
$ pipenv install
Creating a virtualenv for this project…
Using /usr/bin/python3.6m (3.6.5) to create virtualenv…
⠋Running virtualenv with interpreter /usr/bin/python3.6m
Using base prefix '/usr'
New python executable in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/bin/python3.6m
Also creating executable in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/bin/python
Installing setuptools, pip, wheel...done.

Virtualenv location: /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7
Installing dependencies from Pipfile.lock (fe220f)…  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 8/8 — 00:00:02
To activate this project's virtualenv, run the following: $ pipenv shell
```

2. Try to update only requests to a new version
```
$ pipenv install --selective-upgrade requests
Installing requests…
Requirement already up-to-date: requests in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/lib/python3.6/site-packages (2.19.1)
Requirement not upgraded as not directly required: idna<2.8,>=2.5 in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/lib/python3.6/site-packages (from requests) (2.7)
Requirement not upgraded as not directly required: urllib3<1.24,>=1.21.1 in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/lib/python3.6/site-packages (from requests) (1.23)
Requirement not upgraded as not directly required: certifi>=2017.4.17 in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/lib/python3.6/site-packages (from requests) (2018.4.16)
Requirement not upgraded as not directly required: chardet<3.1.0,>=3.0.2 in /home/madams/.venv/pipenv-selective-upgrade-test-tRat6HU7/lib/python3.6/site-packages (from requests) (3.0.4)

Adding requests to Pipfile's [packages]…
Installing dependencies from Pipfile.lock (fe220f)…
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 8/8 — 00:00:01
To activate this project's virtualenv, run the following:
 $ pipenv shell
 ```

3. The problem

Pipfile is unchanged (as expected) and Pipfile.lock is unchanged (unexpected).
