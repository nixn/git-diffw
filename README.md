# git-diffw

A post-processor for `git diff` to combine the best of `git diff` and `git diff --color-words`.

For lines which differ significantly, it displays the result of `git diff`.
For lines which differ only slightly or only in prefix or suffix,
it displays the result of `git diff --color-words`.

A new prefix for the resulting diff lines beside `+` and `-` is introduced:
`~`, meaning a line, which is diff'ed by `--color-words`.

The code is written in Perl and the whole program is inspired
by [diff-highlight](https://github.com/git/git/tree/master/contrib/diff-highlight).
It uses the library Levenshtein::XS.

## Usage

Install Levenshtein::XS by e.g. `sudo apt-get install libtext-levenshteinxs-perl`.

```text
$ sudo cp diff-words /usr/local/bin/
$ sudo chmod +x /usr/local/bin/diff-words
$ git config --global alias.diffw '!env GIT_PAGER="diff-words | pager" git diff'
```

Now you have a new git (alias) command: `git diffw`. Using an alias has the advantage
to have the original `git diff` still present (unlike in the diff-highlight examples).

## License

MIT. See [LICENSE](LICENSE) for details.

## Donations

If you like the program, consider dropping some satoshis to `1nixn9rd4ns8h5mQX3NmUtxwffNZsbDTP`. Thanks!
