# 1819

A reviewer for Go payment services: it reviews a feature branch against its
target branch, combining what the compiler can prove about the change with
model reasoning that has to cite the code it talks about.

## Layout

| directory | what it is |
|---|---|
| [`gofacts/`](gofacts/README.md) | the shared code-facts library, extracted from testigo's scanner. Its own Go module so testigo can depend on it without the reviewer's dependencies. |

The reviewer itself is built on `gofacts` and is not here yet.
