# 1819

A reviewer for Go payment services: it reviews a feature branch against its
target branch, combining what the compiler can prove about the change with
model reasoning that has to cite the code it talks about.

## Code facts

What the compiler can prove comes from
[gofacts](https://github.com/katayunak/gofacts), the shared code-facts library
extracted from testigo's scanner. It lives in its own repo so testigo and the
reviewer depend on one implementation. See its
[README](https://github.com/katayunak/gofacts/blob/main/README.md) for what it
answers, and [TESTIGO.md](https://github.com/katayunak/gofacts/blob/main/TESTIGO.md)
for how it relates to testigo.

## Taking gofacts

The reviewer is not here yet, so there is no `go.mod`. When its first code
lands, the module is

```
module github.com/katayunak/1819

go 1.25.0
```

and, once that code imports gofacts, gofacts is added at v0.1.0 and vendored:

```bash
GOFLAGS=-mod=mod go get github.com/katayunak/gofacts@v0.1.0
GOFLAGS=-mod=mod go mod tidy
GOFLAGS=-mod=mod go mod vendor
```

`GOFLAGS=-mod=mod` is needed because builds here default to `-mod=vendor`.
