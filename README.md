Gitrob Docker
=============

Forked from [aykit/gitrob-docker](https://github.com/aykit/gitrob-docker).

## Gitrob

[Gitrob][gitrob] is a tool which, using the GitHub API, scans related repositories for things which may be useful to an attacker. This includes passwords, SQL dumps, API keys and much more.

**Gitrob is no longer being actively developed, the author is currently working on its successor.**

## Requirements

 * [Docker][get-docker]
 * [Docker Compose][get-docker-compose]

## How to run Gitrob

 * Copy `.env.example` to `.env`, uncomment `GITHUB_API_KEY` and add your key.
 * Run `docker-compose up -d postgres` to start the postgres container.
 * Run `docker-compose run --rm -p 9393 gitrob <YOUR ORG>` with the name of the org you want to scan.
 * Visit http://your-docker-host-ip:9393 to view the results.

[get-docker]: https://get.docker.com/
[get-docker-compose]: https://docs.docker.com/compose/install/
[gitrob]: https://github.com/michenriksen/gitrob
