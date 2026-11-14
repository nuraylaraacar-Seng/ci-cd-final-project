# ci-cd-final-project

A small Flask counter service with a CI/CD pipeline around it: GitHub Actions lints and tests every push and pull request, and a Tekton pipeline on OpenShift builds the image and deploys it.

The service is deliberately simple. The point of this repo is the pipeline.

Final project for IBM's *CI/CD Tools and Practices* course on Coursera.

![CI](https://github.com/nuraylaraacar-Seng/ci-cd-final-project/actions/workflows/workflow.yml/badge.svg)

## Layout

| Path | What it is |
|---|---|
| `service/` | Flask app with the counter endpoints |
| `tests/` | Unit tests, run with coverage |
| `.github/workflows/` | CI: lint + tests on push and PR |
| `.tekton/` | Tekton tasks used by the CD pipeline |
| `Dockerfile`, `Procfile` | Container image and process definition |
| `bin/setup.sh` | Dev environment setup |

## API

[fill in: method, path, behavior. e.g. POST /counters/<name> creates, GET reads, PUT increments, DELETE removes. Include what happens on a duplicate create or a missing counter.]

## Run it locally

```bash
bash bin/setup.sh   # creates the virtualenv and installs dependencies
exit                # open a new shell so the venv is active
[the command you actually use to start the service]
```

## Run the checks

```bash
[the exact flake8 command from your workflow]
[the exact test command from your workflow]
```

## Pipeline

**CI (GitHub Actions).** On every push and pull request to `main`: checkout, set up Python [version], install requirements, lint with flake8, run the tests. [Add the coverage number if you report it.]

**CD (Tekton on OpenShift).** [List only the stages you actually built, in order. Typical set: cleanup → git-clone → flake8 → tests → image build → deploy.]

## What I'd tell someone doing the same course

[2–3 real things that cost you time. Examples of the kind of thing that fits here: a version pin that broke a tool, a Tekton workspace or permission error, how you debugged a failing pipeline run. Use your own, they're the most useful part of the README.]

## License

Apache 2.0, from the course template.
