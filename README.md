## Getting Started

Clone this directory:

```
    % cd ~/src
    % git clone github.com/snakebitenet/snakebite.git
    % cd snakebite
```

Initialize `snakebite.subr` by running it:

```
% sh snakebite.subr
Logged you in from 66.65.133.115.
+------------------------------------------------------------------+
|                         Available Hosts                          |
|               (Last Update: 2014-07-27 23:01:52Z)                |
+------------------------------------------------------------------+
| Alias |      OS     |   Arch   |     CPUs     | RAM  | Compilers |
+-------|-------------|----------|--------------|------|-----------+
|     a7|AIX 7.1      | PowerPC  |    2 @ 1.4GHz|   8GB|xlc121     |
|     h2|HP-UX 11iv2  | PA-RISC  |    2 @ 875MHz|   8GB|hpacc0395  |
|     h3|HP-UX 11iv3  | Itanium2 |    4 @ 1.3GHz|  64GB|hpacc0626  |
|     i6|IRIX 6.5.30  |   MIPS   |    4 @ 500MHz|   4GB|gcc34      |
|    s10|Solaris 10   |  SPARC   |    2 @ 1.2GHz|   8GB|suncc123   |
|    s11|Solaris 11   |   x64    |    2 @ 2.4GHz|  16GB|suncc123   |
|     s9|Solaris 9    |  SPARC   |    2 @ 900MHz|   8GB|suncc123   |
|     t5|Tru64 5.1B   |  Alpha   |    4 @ 667MHz|   7GB|cc65       |
+------------------------------------------------------------------+
Enter alias (^C to exit): a7

AIX arsenic 1 7 000BF95F4C00

    :::.     :::::::..    .::::::. .,::::::  :::.    :::.  :::    .,-:::::
    ;;`;;    ;;;;``;;;;  ;;;`    ` ;;;;''''  `;;;;,  `;;;  ;;;  ,;;;'````'
   ,[[ '[[,   [[[,/[[['  '[==/[[[[, [[cccc     [[[[[. '[[  [[[  [[[
  c$$$cc$$$c  $$$$$$c      '''    $ $$""""     $$$ "Y$c$$  $$$  $$$
   888   888, 888b "88bo, 88b    dP 888oo,__   888    Y88  888  `88bo,__,o,
   YMM   ""`  MMMM   "W"   "YMmMY"  """"YUMMM  MMM     YM  MMM    "YUMMMMMP"

                                 AIX 7.1
                       IBM IntelliStation 9114-275
                          2 x 1.4GHz Power4 CPUs
                         2 x 2Gbps LP9802 FC HBAs
                            8GB RAM, 4 x 36GB

[trent@arsenic]~%
```

You can also get into servers directly once you've logged in:

```
% ./sb s11

Last login: Wed Jul 30 02:27:49 2014 from cpe-66-65-133-1
Oracle Corporation      SunOS 5.11      11.1    October 2012
  .,-:::::      :::.       :::::::..     :::::::.        ...       :::.    :::.
,;;;'_***'      ;;*;;      ;;;;**;;;;     ;;;'';;'    .;;;;;;;.    *;;;;,  *;;;
[[[            ,[[ '[[,     [[[,/[[['     [[[__[[\.  ,[[     \[[,    [[[[[. '[[
$$$           c$$$cc$$$c    $$$$$$c       $$""""Y$$  $$$,     $$$    $$$ "Y$c$$
*88bo,__,o,    888   888,   888b "88bo,  _88o,,od8P  "888,um:ttypts/0) (Wed/05:47) ..                                    (~)
% echo $DISPLAY
localhost:10.0
_ _,88P    888    Y88
  "YUMMMMMP"   YMM   ""*    MMMM   "W"   ""YUMMMP"     "YMMMMMP"     MMM     YM

                      Solaris 11/11.1 x64, Sun Fire v20z
                          Dual Opteron 250 @ 2.4GHz
                       16GB DDR400 RAM, Dual FC 2Gbps
                       `zpool status -v` for ZFS info
```

## X-Forwarding

`./sbx` and `./sby` cause X11 display forwarding:

```
% ./sbx h3
 ::::::::::: ::: :::::::::: :::.   :::.    :::.  ::  ...    ::: .        :
  ;;;;;;;;''' ;;; ;;;;;;;''' ;;`;;  `;;;;,  `;;  ;;;  ;;     ;;; ;;,.    ;;;
       [[     [[[     [[    ,[[ '[[,  [[[[[. '[[ [[[ [['     [[[ [[[[, ,[[[[,
       $$     $$$     $$   c$$$cc$$$c $$$ "Y$c$$ $$$ $$      $$$ $$$$$$$$"$$$
       88,    888     88,   888   888,888    Y88 888 88    .d888 888 Y88" 888o
       MMM    MMM     MMM   YMM   ""` MMM     YM MMM  "YmmMMMM"" MMM  M'  "MMM

                               HP-UX/ia64 11iv3
                              HP Integrity RX5670
                             4 x Itanium2 @ 1.3GHz
                             64GB RAM, 4x73GB HDDs

(trent@titanium:ttypts/0) (Wed/05:47) ..                                    (~)
% echo $DISPLAY
localhost:10.0
% xclock
```

Will bring up a little X11 clock on the screen.

Other commands:

```
% ./sbctl
available subcommands for sbctl:
    cat-gpg-encrypted-file
    connection-test
    decrypt
    decrypt-secret
    delete-gpg-info
    export-gpg-pubkey
    get-gpg-conf
    get-project-count
    get-project-details
    get-sbctl-gpg-keyid
    get-sbctl-gpg-pubkey
    get-username-for-project
    hard-reset
    import-sbctl-gpg-pubkey
    init-gpg
    list-host-aliases
    list-hosts
    list-projects
    login
    logout
    print-current-project
    print-current-project-short
    pssst
    sb-ssh-cmd
    sbctl-ssh-cmd
    select-project
    set-project
    show-my-gpg-keyid
    svn-cmd
    svn-update
    try-switch-to-https
    upload-gpg-pubkey
```

Try `init-gpg` first.

