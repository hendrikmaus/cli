---
title: "load"
description: "The load command description and usage"
keywords: "stdin, tarred, repository"
---

# load

```markdown
Usage:  docker load [OPTIONS]

Load an image or repository from a tar archive (even if compressed with gzip,
bzip2, or xz) from a file or STDIN.

Aliases:
  docker image load, docker load

Options:
      --help           Print usage
  -i, --input string   Read from tar archive file, instead of STDIN.
                       The tarball may be compressed with gzip, bzip, or xz
  -q, --quiet          Suppress the load output but still outputs the imported images
```

## Description

Load an image or repository from a tar archive (even if compressed with gzip,
bzip2, or xz) from a file or STDIN. It restores both images and tags.

## Examples

```console
$ docker image ls

REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

### Load images from STDIN

```console
$ docker load < busybox.tar.gz

Loaded image: busybox:latest
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
busybox             latest              769b9341d937        7 weeks ago         2.489 MB
```

### <a name=input></a> Load images from a file (--input)

```console
$ docker load --input fedora.tar

Loaded image: fedora:rawhide
Loaded image: fedora:20

$ docker images

REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
busybox             latest              769b9341d937        7 weeks ago         2.489 MB
fedora              rawhide             0d20aec6529d        7 weeks ago         387 MB
fedora              20                  58394af37342        7 weeks ago         385.5 MB
fedora              heisenbug           58394af37342        7 weeks ago         385.5 MB
fedora              latest              58394af37342        7 weeks ago         385.5 MB
```
