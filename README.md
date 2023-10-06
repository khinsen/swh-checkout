`swh-checkout` is a simple tool to download a precise version of some
software package, identified by one of
 - the URL of a git repository plus a full commit ID (40 characters)
 - a SWHID of type "dir" or "rev" with contextual attributes
 
 `swh-checkout` tries accessing the git repository first. In case of failure, it obtains the software from the [Software Heritage](https://www.softwareheritage.org/) archive.
 
 ## Installation
 
 1. Install the [Guix package manager](https://guix.gnu.org)
 
 2. Download `swh-checkout`, make it executable (`chmod a+x swh-checkout`), and move it to a directory on the `$PATH` variable of your shell.

The Guix package manager is required because `swh-checkout` uses part of its code. In fact, it is little more than a user interface to Guix functionality that is not exposed otherwise.

## Usage

If you have the URL of a git repository plus a commit hash:

```
swh-checkout --url=<url> --commit=<sha1>
```

If you have a SWHID:
```
swh-checkout --swhid="swh:1:..."
```

Note that the SWHID must be written in double quotes to prevent it from being broken up by the shell.

The requested commit is checked out into a directory whose default name is the last part of the URL. A different directory can be specified using the option `--directory`.

