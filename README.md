# MY_PROJECT

PROJECT_STATEMENT

## Setup

### Dependencies

- [Docker](https://www.docker.com/products/docker-desktop/) OR [OrbStack](https://orbstack.dev/) (recommended, commercial license required)
  for external dependencies, e.g. Postgres
- [mise-en-place](https://mise.jdx.dev/installing-mise.html) for version management e.g. Elixir, Erlang, Node.js
- [FlyCTL](https://fly.io/docs/flyctl/install/) for deployment only

### Instructions

Request the following from a team member:

- `.env` and place it in the root path of the project
- database dump; this will be loaded after setup is completed

Run the setup script:

```shell
script/setup
```

Load the database dump replace `DB_DUMP_PATH` with the path of the file containing SQL dump:

```shell
psql postgres://postgres:postgres@localhost/MY_PROJECT_dev < DB_DUMP_PATH
```

## Development

Generate docs to learn more about the application:

```shell
mix docs --open
```

Start:

```shell
script/server
```

Testing and linting:

```shell
mix test
mix check
```

Scripts located in `script/` are used to automate common tasks. They're
not necessary to use all the time, but you may find them a good tool to
learn various commands.

## Deployment

https://MY_PROJECT.fly.dev/

```shell
# if not authenticated:
fly auth login

fly deploy
```

## Practices

- Please add the prefix to pull requests:
  - `feat:` for new features
  - `chore:` for maintenance tasks
  - `test:` for adding tests
  - `fix:` for bug fixes
  - `docs:` for documentation
- Keep merge commit messages when merging a PR to one-line to keep the history clean,
  e.g. `feat: Add new some feature (pull request #42)`
