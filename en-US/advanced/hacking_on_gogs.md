---
name: Hacking on Gogs
---

# Hacking on Gogs

If you want to contribute to Gogs you should fork the project and work on the dev branch.
There is a catch though; some internal packages are referenced by their Github url. So
you have to trick the Go tool to think that you work on a clone of the official repository.

Start by downloading the source code as you normally would:

    $ go get github.com/gogits/gogs

Now fork the project on Github and then go to gogs' source parent directory:

    $ cd $GOPATH/src/github.com/gogits

Remove the gogs repository and clone your fork in its place:

    $ rm -rf gogs
    $ git clone git@github.com:<USERNAME>/gogs.git gogs

Go inside the gogs directory, checkout the develop branch and use `go get -u ./...` again to fetch any new dependencies:

    $ cd gogs
    $ git checkout develop
    $ go get -u ./...

Gogs have a test suite that can be run with the `make test` command. Writing
test cases is not mandatory to contribute, but we will be happy if you do.
More information about writing tests in Go can be found on
[the official documentation](golangtesting).

That's it! You are ready to hack on Gogs. Test your changes, push them to your repository and open a pull request.

[golangtesting]: https://golang.org/pkg/testing/
