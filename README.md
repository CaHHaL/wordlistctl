## Description

Script to fetch, install, update and search wordlist archives from websites
offering wordlists with more than 6400 wordlists available.

In the latest version of the Blackarch Linux it has been added to
**/usr/share/wordlists/** directory.

## Installation

`pacman -S wordlistctl`

## Manual Installation (If pacman is not available)

If you're using a system where pacman is not supported, you can manually clone and run the script:

`git clone https://github.com/BlackArch/wordlistctl.git`

`cd wordlistctl`

`chmod +x wordlistctl.py`

Then use it like this:

`./wordlistctl.py list -g passwords`

`./wordlistctl.py fetch -g usernames -d`

`./wordlistctl.py search admin`

Note - Make sure you have Python 3 installed.

## Usage

```
$ wordlistctl [-h] [-v] {fetch,search,list} ...

Fetch, install and search wordlist archives from websites.

positional arguments:
  {fetch,search,list}
    fetch              fetch wordlists

    search             search wordlists

    list               list wordlists

optional arguments:
  -h, --help           show this help message and exit

  -v, --version        show program's version number and exit
```
### Fetch Options
```
$ wordlistctl fetch [-h] [-l WORDLIST [WORDLIST ...]]
                         [-g {usernames,passwords,discovery,fuzzing,misc} [{usernames,passwords,discovery,fuzzing,misc} ...]]
                         [-d] [-w WORKERS] [-u USERAGENT] [-b BASEDIR] fetch_term

positional arguments:
  fetch_term           fetch string filter

optional arguments:
  -h, --help            show this help message and exit

  -l WORDLIST [WORDLIST ...], --wordlist WORDLIST [WORDLIST ...]
                        wordlist to fetch

  -g, --group {group} [{group} ...]
                        wordlist group to fetch
                        available groups:
                          usernames
                          passwords
                          discovery
                          fuzzing
                          misc

  -d, --decompress      decompress and remove archive

  -w WORKERS, --workers WORKERS
                        download workers [default: 10]

  -u USERAGENT, --useragent USERAGENT
                        fetch user agent [default: wordlistctl/v0.9.x]

  -b BASEDIR, --base-dir BASEDIR
                        wordlists base directory [default: /usr/share/wordlists]

```


### Search Options
```
$ wordlistctl search  [-h] [-l] [-b BASEDIR] search_term

positional arguments:
  search_term           what to search

optional arguments:
  -h, --help            show this help message and exit

  -l, --local           search local archives

  -b BASEDIR, --base-dir BASEDIR
                        wordlists base directory [default: /usr/share/wordlists]

  -f INDEX [INDEX ...], --fetch INDEX [INDEX ...]
                        fetch the wordlists at the given indexes in the search results, see
                        fetch options for additional options

fetch options:
  -d, --decompress      decompress and remove archive

  -w WORKERS, --workers WORKERS
                        download workers [default: 10]

  -u USERAGENT, --useragent USERAGENT
                        parser user agent [default: wordlistctl/v0.9.x]
```

### List Options
```
$ wordlistctl list [-h] [-g {usernames,passwords,discovery,fuzzing,misc}]

optional arguments:
  -h, --help            show this help message and exit

  -g, --group {group}
                        show all wordlists in group
                        available groups:
                          usernames
                          passwords
                          discovery
                          fuzzing
                          misc

  -f INDEX [INDEX ...], --fetch INDEX [INDEX ...]
                        fetch the wordlists at the given indexes in the list, see
                        fetch options for additional options

fetch options:
  -d, --decompress      decompress and remove archive

  -w WORKERS, --workers WORKERS
                        download workers [default: 10]

  -u USERAGENT, --useragent USERAGENT
                        parser user agent [default: wordlistctl/v0.9.x]
```

## Get Involved

You can get in touch with the BlackArch Linux team. Just check out the following:

**Please, send us pull requests!**

**Web:** https://www.blackarch.org/

**Mail:** team@blackarch.org

**IRC:** [irc://irc.freenode.net/blackarch](irc://irc.freenode.net/blackarch)
