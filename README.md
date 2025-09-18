# gitlab

<!-- More info: https://github.com/Ileriayo/markdown-badges -->
<!-- More info: https://shields.io/badges -->
<!-- More info: https://badgesgenerator.com/ -->

[![GitLab Sync](https://img.shields.io/badge/gitlab_sync-gitlab-blue?style=for-the-badge&logo=gitlab)](https://gitlab-internal.spirit-dev.net/github-mirror/helm-gitlab) <!-- markdownlint-disable MD041 -->
[![GitHub Mirror](https://img.shields.io/badge/github_mirror-gitlab-blue?style=for-the-badge&logo=github)](https://github.com/spirit-dev/helm-gitlab)
[![App Status](https://argocd-internal.spirit-dev.net/api/badge?name=gitlab&revision=true&showAppName=true)](https://argocd-internal.spirit-dev.net/applications/gitlab)

<!--TOC-->

- [Installation process](#installation-process)
- [troubleshooting](#troubleshooting)
  - [MinIO issue](#minio-issue)
  - [Execute Rake commands](#execute-rake-commands)

<!--TOC-->

## Installation process

The installation is entirely managed by Argocd.

A `Makefile` is present here to ease the first and one-time deployment or in case of an issue.
The installation should be done in two steps:

```shell
#> make dry-run ENV=<ENV>
#> make install ENV=<ENV>
```

## troubleshooting

### MinIO issue

For some reason Longhorn lost the drive dedicated to MinIO... fuck it.

Also somehow, the job responsible to create initial bucket failed.

Here is a beggining of resolution guide: <https://docs.gitlab.com/charts/advanced/external-object-storage/minio.html>

### Execute Rake commands

1. Jump in the `toolbox` pod
2. Run `gitlab-rake xyz` commands

<https://docs.gitlab.com/ee/raketasks/>
