Gitrob Docker
=============

Forked from [aykit/gitrob-docker](https://github.com/aykit/gitrob-docker).

[Docker][docker] config for running the [Gitrob][gitrob] security testing tool.

## Gitrob

[Gitrob][gitrob] is a tool which, using the GitHub API, scans related repositories for things which may be useful to an attacker. This includes passwords, SQL dumps, API keys and much more.

**Gitrob is no longer being actively developed, the author is currently working on its successor.**

## Containers

This repository consists of two docker containers and a docker compose config for running Gitrob. The first container is a postgres database and some minimal config to set it up for Gitrob. The second is Gitrob itself which is a ruby application.

## Requirements

 * [Docker][get-docker]
 * [Docker Compose][get-docker-compose]

## How to run Gitrob

 * Copy `.env.example` to `.env`, uncomment `GITHUB_API_KEY` and add your key.
 * Run `docker-compose up -d postgres` to start the postgres container.
 * Run `docker-compose run --rm -p 9393 gitrob <YOUR ORG>` with the name of the org you want to scan.
 * Visit http://your-docker-host-ip:9393 to view the results.

[docker]: https://www.docker.com/
[get-docker]: https://get.docker.com/
[get-docker-compose]: https://docs.docker.com/compose/install/
[gitrob]: https://github.com/michenriksen/gitrob
