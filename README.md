reviser
=======

# Disclaimer

This command is dangerous, please check the directory blacklist and **be sure**
you don't shoot yourself in the foot.

# About

The following command will replace occurances of parameter `$1` with parameter
`$2`.  Let it be henceforth known as `reviser` and symlinked from my `~/bin`
folder for great ease of use.

```
find ./ -type f -not \( -path "*/.git/*" -path "*/node_modules/*" \) -exec sed -i 's/$1/$2' {} \;
```

# Setup

From wherever you stash your clone:

```
$ git clone http://github.com/ninegrid/reviser.git .
$ ln -s ./reviser ~/bin/reviser
```

# Usage

```
$ reviser foo bar
```

Will replace occurances of `foo` with `bar` in all files in the current
directly, recursively throughout all subdirectories except for folders named
`.git` or `node_modules`.

# Todo

This is a one-off script that I've decided not to type twice, it *is not*
robust.

I'll be updating the blacklist in the future, maybe pretty handy to have it work
off of subdirectory .gitignore files.  Who knows, suggestions are welcome.


# LICENSE

The Unlicense, free and unencumbered released into the public domain.
