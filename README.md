# Docker Exec Image: s

A Dockerfile describing an container capable of executing s source files.

# Build

```sh
git clone https://github.com/docker-exec/perl6.git
docker build -t dexec/lang-perl6 .
```

# Usage

In a directory containing a script e.g. foo.p6, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.p6:/tmp/dexec/build/foo.p6 \
    dexec/lang-perl6 foo.p6
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.p6:/tmp/dexec/build/foo.p6 \
    dexec/lang-perl6 foo.p6 \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
