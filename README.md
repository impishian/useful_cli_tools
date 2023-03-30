- [1. useful command line tools ( written in rust/go/c )](#1-useful-command-line-tools--written-in-rustgoc-)
  - [1.1 search, list, view](#11-search-list-view)
  - [1.2 serve, make, deploy, upload, download](#12-serve-make-deploy-upload-download)
  - [1.3 convert, calc](#13-convert-calc)
  - [1.4 test, diag](#14-test-diag)
  - [1.5 其他](#15-其他)
- [2. lolcate](#2-lolcate)
  - [2.1 lc 的 help](#21-lc-的-help)
  - [2.2 文件类型](#22-文件类型)
  - [2.3 default数据库](#23-default数据库)
  - [2.4 其他数据库](#24-其他数据库)
  - [2.5 日常使用](#25-日常使用)
  - [2.6 lc\_info](#26-lc_info)
- [3. generate\_password](#3-generate_password)
- [4. hex2dec / dec2hex](#4-hex2dec--dec2hex)
- [5. dot](#5-dot)
- [6. lilypond](#6-lilypond)
- [7. e2c / c2e](#7-e2c--c2e)
- [8. man](#8-man)
- [9. bash5 in macOS](#9-bash5-in-macos)
  - [9.1 install bash, bash completion](#91-install-bash-bash-completion)
  - [9.2 bash completion](#92-bash-completion)
  - [9.3 bash常用设置](#93-bash常用设置)
    - [9.3.1  ~/.bashrc](#931--bashrc)
    - [9.3.2 ~/.bash\_profile](#932-bash_profile)
    - [9.3.3 ~/.hg-prompt.sh](#933-hg-promptsh)
    - [9.3.4 ~/.git-prompt.sh](#934-git-promptsh)

## 1. useful command line tools ( written in rust/go/c )

### 1.1 search, list, view

|   | github  | 说明  |
| ------------ | ------------ | ------------ |
| `lolcate` |  https://github.com/ngirard/lolcate-rs | A comically fast way of indexing and querying your filesystem. Replaces locate / mlocate / updatedb. Written in Rust. 推荐 `ln -s ... lc` 。下个小节，是 lc 的配置和使用 |
| `joshuto` | https://github.com/kamiyaa/joshuto | ranger-like terminal file manager written in Rust 与 hunter 类似，功能和定制性更优、可参考 github 上的 toml 配置，而 keymap.toml , mimetype.toml 可适当修改。推荐 `ln -s ... jst` |
| hunter | https://github.com/rabite0/hunter | The fastest file manager in the galaxy! |
| `fd` | https://github.com/sharkdp/fd | A simple, fast and user-friendly alternative to 'find' |
| `fzf` | https://github.com/junegunn/fzf |A command-line fuzzy finder |
| `exa` | https://github.com/ogham/exa | A modern replacement for ‘ls’. |
| `zoxide` | https://github.com/ajeetdsouza/zoxide | A smarter cd command. Supports all major shells. 增加一行到 .bashrc，以后便可 z 或 zi 替代长长的 cd 命令行 |
| `glow` | https://github.com/charmbracelet/glow   | Render markdown on the CLI, with pizzazz!  (类似的有: mdcat)  |
| `tldr` (rust) | https://github.com/dbrgn/tealdeer | A very fast implementation of tldr in Rust. 在 MacOS下不便编译C版本的，可用 rust 版本的。 |
| tldr (in c) | https://github.com/tldr-pages/tldr-c-client | C command-line client for tldr pages. 代替 man 常用功能，省去大略查看 man 的时间. 相关页面: https://tldr.sh/ |
| tree | https://github.com/Old-Man-Programmer/tree.git |Tree for Unix/LInux|
| `ncdu` | https://dev.yorhel.nl/ncdu | v1.17, a disk usage analyzer with an ncurses interface |
| `czkawka` | https://github.com/qarmin/czkawka |find duplicates, empty folders, similar images etc. 超快。(Ubuntu：可下载最新5.0.2；MacOS 13.1 可下载5.1.0；CentOS7.9需rpm安装glibc2.28再下载3.31版本)|
| `ripgrep` | https://github.com/BurntSushi/ripgrep | `rg` (grep替代). ripgrep recursively searches directories for a regex pattern while respecting your gitignore |
| ugrep | https://github.com/Genivia/ugrep | NEW ugrep v3.8: ultra fast grep with interactive TUI, fuzzy search, boolean queries, hexdumps and more: search file systems, source code, text, binary files, archives (cpio/tar/pax/zip), compressed files (gz/Z/bz2/lzma/xz/lz4/zstd), documents etc. A faster, user-friendly and compatible grep replacement.( github.com/genivia/ugrep/wiki ) |
| `bat` | https://github.com/sharkdp/bat/ | A cat(1) clone with wings. |
| `difft` | https://github.com/Wilfred/difftastic/ | a structural diff that understands syntax|
| delta | https://github.com/dandavison/delta | A syntax-highlighting pager for git, diff, and grep output |
| `gitui` | https://github.com/extrawurst/gitui | Blazing 💥 fast terminal-ui for git written in rust   |
| `ydict` | https://github.com/TimothyYe/ydict | Yet another command-line youdao dictionary for geeks! 推荐 `ln -s ... yd` |
| `manssh` | https://github.com/xwjdsh/manssh | Manage your ssh alias configs easily. |
| hexyl | https://github.com/sharkdp/hexyl  | A command-line hex viewer |
| hex | https://github.com/sitkevij/hex  | Futuristic take on hexdump, made in Rust |
| `viu` | https://github.com/atanunq/viu | Terminal image viewer with native support for iTerm and Kitty |
| ag | https://github.com/ggreer/the_silver_searcher | A code-searching tool similar to ack, but faster. ( https://geoff.greer.fm/ag/ ) |

### 1.2 serve, make, deploy, upload, download

|   | github  | 说明  |
| ------------ | ------------ | ------------ |
| `fnm` | https://github.com/Schniz/fnm |nvm替代|
|frum | https://github.com/TaKO8Ki/frum | rvm替代。A little bit fast and modern Ruby version manager written in Rust|
| `miniserve` | https://github.com/svenstaro/miniserve | For when you really just want to serve some files over HTTP right now! (release下的MacOS版本，运行时报“段故障”，需自行编译)  ，常用参数：miniserve -v -u -W -D -g -z .  可上传、下载，大文件性能也不错。 Android/iOS/Mac/Windows 之间，局域网内互传文件之佳选|
| `facil` | https://github.com/boazsegev/facil.io | Your high performance web application C framework (1.使用 scripts/new/app 这个 shell 脚本，新建一个工程，2.进入工程目录，make 编译得到 fioapp改名为 facil 即得到最轻量级的一个 http server。 3.比如：nohup facil -p 3333 -w 1 -t 1 -www /Users/ian/html-book-20211231/reference/ 2>&1 > /dev/null &)  和 nohup facil -p 4444 -w 1 -t 1 -www /Users/ian/.rustup/toolchains/stable-x86_64-apple-darwin/share/doc/rust/html 2>&1 > /dev/null & |
| simple-http-server| https://github.com/TheWaWaR/simple-http-server  | 支持上传的 Simple http server in Rust (Windows/Mac/Linux), 可用于 android 上传文件到 iMac |
| uploadserver | https://github.com/akovacs/uploadserver |Simple Rust file server which lets you upload, share, and download files from a web browser.  |
| aria2 | https://github.com/aria2/aria2 | aria2 is a lightweight multi-protocol & multi-source, cross platform download utility operated in command-line. It supports HTTP/HTTPS, FTP, SFTP, BitTorrent and Metalink. ( aria2.github.io/ ) |
| wget2 | https://github.com/rockdaboot/wget2.git | The successor of GNU Wget |
| croc | https://github.com/schollz/croc | Easily and securely send things from one computer to another ( https://schollz.com/software/croc6) |
| you-get | https://github.com/soimort/you-get | Dumb downloader that scrapes the web, 可下载大量视频网站 (https://you-get.org/ ) |
| `task` | https://github.com/go-task/task | A task runner / simpler Make alternative written in Go (https://taskfile.dev) |
| sup | https://github.com/pressly/sup | Super simple deployment tool - think of it like 'make' for a network of servers |
| xmake, xrepo | https://github.com/xmake-io/xmake.git | A cross-platform build utility based on Lua |
| ssh-copy-id-for-OSX | https://github.com/beautifulcode/ssh-copy-id-for-OSX.git | Quick Mac OSX port of the useful unix utility ssh-copy-id |
| up | https://github.com/apex/up | Deploy infinitely scalable serverless apps, apis, and sites in seconds to AWS. (https://up.docs.apex.sh) |
| drone | https://github.com/harness/drone | Drone is a Container-Native, Continuous Delivery Platform |
| xh| https://github.com/ducaale/xh | Friendly and fast tool for sending HTTP requests . 实现 HTTPie 大部分功能、性能更好。用  HTTPie 一样的请求语法|
| httpie || python |
| curlie || go |
| axel || c, 依赖太多，OS下不好编译 |

### 1.3 convert, calc

|   | github  | 说明  |
| ------------ | ------------ | ------------ |
| `network-calc`|https://github.com/allisonmachado/network-calc | A subnet mask and network calculator|
| `sd` | https://github.com/chmln/sd | Intuitive find & replace CLI (sed alternative) 替换字符串，更快。 |
| `tokei` | https://github.com/XAMPPRocky/tokei | Count your code, quickly. |
| cloc | https://github.com/AlDanial/cloc.git |perl script. cloc counts blank lines, comment lines, and physical lines of source code in many programming languages. |
| scc | https://github.com/boyter/scc | Sloc, Cloc and Code: scc is a very fast accurate code counter with complexity calculations and COCOMO estimates written in pure Go |
| `jq` | https://github.com/stedolan/jq | Command-line JSON processor |
| yq | https://github.com/mikefarah/yq | yq is a portable command-line YAML, JSON and XML processor (https://mikefarah.gitbook.io/yq/ ) |
| pup | https://github.com/ericchiang/pup.git  | Parsing HTML at the command line ，HTML 的 jq|
| xsv | https://github.com/BurntSushi/xsv | A fast CSV command line toolkit written in Rust.|
| w3m | https://github.com/tats/w3m.git | Debian's w3m: WWW browsable pager，可做到类似Sublime Text的 HTML Prettify的格式化 |
| html tidy | https://www.html-tidy.org/ | https://blog.longwin.com.tw/2010/09/html-tidy-formatter-2010/ , 类似Sublime Text的 HTML Prettify|
| rename | https://github.com/ap/rename.git | perl script. Rename multiple files |
| jade | https://github.com/Joker/jade | Jade.go - pug template engine for Go (golang) , https://www.cnblogs.com/xiaohuochai/p/7222227.html|
| q | https://harelba.github.io/q |Run SQL directly on delimited files and multi-file sqlite databases |

### 1.4 test, diag

|  | github  | 说明  |
| ------------ | ------------ | ------------ |
| `nali` | https://github.com/zu1k/nali | 一个查询IP地理信息和CDN服务提供商的离线终端工具.An offline tool for querying IP geographic information and CDN provider. |
| `bandwhich` | https://github.com/imsnif/bandwhich | Terminal bandwidth utilization tool |
| `websocat` | https://github.com/vi/websocat | Command-line client for WebSockets, like netcat (or curl) for ws:// with advanced socat-like functions |
| `iperf3` | https://github.com/esnet/iperf | iperf3: A TCP, UDP, and SCTP network bandwidth measurement tool |
| q | https://github.com/natesales/q |A tiny command line DNS client with support for UDP, TCP, DoT, DoH, DoQ and ODoH.|
| m-cli | https://github.com/rgcr/m-cli | Swiss Army Knife for macOS |
| dnslookup | https://github.com/ameshkov/dnslookup | Simple command line utility to make DNS lookups to the specified server |
| duf | https://github.com/muesli/duf | Disk Usage/Free Utility - a better 'df' alternative |
| RustScan | https://github.com/RustScan/RustScan | The Modern Port Scanner |
| wtf | https://github.com/wtfutil/wtf | The personal information dashboard for your terminal (https://wtfutil.com ) |
| ctop | https://github.com/bcicen/ctop | Top-like interface for container metrics (https://ctop.sh) |
| `zenith` | https://github.com/bvaisvil/zenith  | Zenith - sort of like top or htop but with zoom-able charts, CPU, GPU, network, and disk usage |
| wrk | https://github.com/wg/wrk.git | Modern HTTP benchmarking tool ，可用 lua |
| siege | https://github.com/JoeDog/siege | Siege is an http load tester and benchmarking utility |
| mtr / mtr-packet| https://github.com/traviscross/mtr | Official repository for mtr, a network diagnostic tool |
| mylg | https://github.com/mehrdadrad/mylg | Network Diagnostic Tool |
| mmock | https://github.com/jmartin82/mmock  |  Mmock is an HTTP mocking application for testing and fast prototyping |

### 1.5 其他

k9s, kdash, termscp, oxker, trippy 等基于tui-rs的一些应用。

MacOS下编译以上C工程代码，需依赖的一些软件示意如下（不完全列表）：

```
$ brew ls

autoconf  autossh   bdw-gc    coreutils gettext   gnutls    libevent  libidn2
libtasn1  libunistring  m4    openssl@1.1 p11-kit   pkg-config  unbound
automake  bash    ca-certificates ctags   gmp   guile   libffi    libnghttp2
libtool   lzip    nettle    openssl@3 pcre    readline
```

更多 rust 实现的命令行工具，可查阅： https://lib.rs/command-line-utilities

----

## 2. lolcate

### 2.1 lc 的 help

```
$ ln -s /usr/local/bin/lolcate lc
```

```
$ lc --help
Lolcate 0.10.0
Nicolas Girard <girard.nicolas@gmail.com>
Find files by name -- A better locate / mlocate / updatedb

USAGE:
    lc [FLAGS] [OPTIONS] [PATTERN]...

FLAGS:
        --all            Query / update all databases
        --create         Create a database
    -h, --help           Prints help information
    -i, --ignore-case    Search the given patterns case-insensitively. Default is "smart-case", i.e. patterns are
                         searched case-insensitively when all in lowercase, and sensitively otherwise.
        --info           Display configuration informations and existing databases
        --update         Update database
    -V, --version        Prints version information

OPTIONS:
    -b, --basename <PATTERN>    Match only the base name against the specified PATTERN. Can be supplied multiple times,
                                e.g. -b PATTERN1 -b PATTERN2
        --db <database>         Database to be used / created [default: default]
        --type <type>           One or several file types to search, separated with commas

ARGS:
    <PATTERN>...
```
### 2.2 文件类型

配置文件的根目录的 config.toml：根据需要，配置一些文件类型，以及对应的一些后缀名。

```
ian@iandeiMac ~/Library/Application Support/lolcate$ cat config.toml
[types]
# Definition of custom path name types
# Examples:
audio = ".*\\.(mp3|m4a|flac|ogg)$"
video = ".*\\.(flv|mp4|mp.?g|avi|wmv|mkv|3gp|m4v|asf|webm)$"
img = ".*\\.(jp.?g|png|gif|JP.?G)$"
doc = ".*\\.(doc|docx|xls|xlsx|ppt|pptx)$"
iwork = ".*\\.(pages|numbers|key)$"
pdf = ".*\\.(pdf)$"
txt = ".*\\.(txt|text)$"
edoc = ".*\\.(chm|epub|djvu?|mobi|azw3|odf|ods|md|adoc)$"
```

### 2.3 default数据库

配置文件的 default 子目录下：config.toml 的 dirs，只索引 ~/ 目录， ignores 里面添加一些不索引的目录

```
ian@iandeiMac ~/Library/Application Support/lolcate$ cat default/config.toml

description = ""

# Directories to index.
dirs = [
  # "~/first/dir",
  # "/second/dir"
  "~/"
]

# Set to "Dirs" or "Files" to skip directories or files.
# If unset, or set to "None", both files and directories will be included.
skip = "Dirs"

# Set to true if you want skip symbolic links
ignore_symlinks = true

# Set to true if you want to ignore hidden files and directories
ignore_hidden = false

# Set to true to read .gitignore files and ignore matching files
gitignore = false
```

```
ian@iandeiMac ~/Library/Application Support/lolcate$ cat default/ignores
# Dirs / files to ignore.
# Use the same syntax as gitignore(5).
# Common patterns:
#
.hg
.git
*~
/Users/ian/Library/**
node_modules
node_modules__
node_modules_2
.vim
.rvm
.nvm
.npm
.composer
.node-gyp
.bundle
.gem
.Trash
.android
.aws
.bash_sessions
.bazel
.cache
.cargo
.cocoapods
.composer_backup
.config
.cups
.dlv
.docker
.goldendict
.gradle
.greenflare
.httpie
.idm
.jetbrains
.itmstransporter
.laradock
.lilypond-fonts.cache-2
.lldb
.local
.m2
.matplotlib
.nali
.node-gyp
.oracle_jre_usage
.putty
.rustup
.siege
.soxy
.ssh
.subversion
.vagrant.d
.vim_bak_20210316120705
.vim_runtime
.vimpls
.vntrader
.vscode
.vjp
.zoomus
```
### 2.4 其他数据库

可参考以上 default 数据库，多建几个索引数据库。根据需要使用。

| `db`  | `dirs`  | `ignores` |
| ------------ | ------------ | ------------ |
| default |  "~/" | 参见上面文件 |
| not_ian | "/Users" | 在 default的 ignores 基础上，再增加一些，如：<br></br>/Users/ian <br> /Users/Deleted Users/ |
| usr_opt_private |   "/usr", "/opt", "/private" | .git <br> .hg <br> *~ <br> /usr/11 <br> /usr/X11R6 <br> /private/tmp <br> /private/var |
| library | "/Library" | 无 |
| application | "/Applications"  | 无 |

### 2.5 日常使用

```
# 从默认的 default 索引里检索
lc xxxx

# 从 database 的索引里，检索名字带 xxxx 的 pdf 的文件
lc --type pdf --db <database> xxxx

# 更新 default 索引
lc --update

# 更新 指定的 database 的索引
lc --db <database> --update
```

### 2.6 lc_info

(1) 查看各个索引数据库的 info 以及数据库大小。

$ cat /usr/local/bin/lc_info

```
#!/usr/bin/env bash

LOLCATE_DIR="/Users/ian/Library/Application Support/lolcate"

echo ==== 基本信息 ====
echo
lc --info

echo ==== 索引文件 *.lz4 大小, 配置文件大小 ====
echo
find "${LOLCATE_DIR}" -type f -name '*.lz4' -print0 | xargs -0 printf '"%s" ' | xargs ls -lh
echo
find "${LOLCATE_DIR}" -type f -name '*.toml' -print0 | xargs -0 printf '"%s" ' | xargs ls -lh
echo
find "${LOLCATE_DIR}" -type f -name 'ignores' -print0 | xargs -0 printf '"%s" ' | xargs ls -lh
echo

echo ==== 每个索引文件里的文件数量 ====
echo
exa -D -1 "${LOLCATE_DIR}" | xargs -I {} echo "printf {}':'; lc --db {} | wc -l;" | xargs -I {} sh -c "{}"
```

(2) 示例结果：

```
==== 基本信息 ====

Config file:
  /Users/ian/Library/Application Support/lolcate/config.toml

Databases:
  default
    Description:
    Config file:  /Users/ian/Library/Application Support/lolcate/default/config.toml
    Ignores file: /Users/ian/Library/Application Support/lolcate/default/ignores
    Data file:    /Users/ian/Library/Application Support/lolcate/default
  library
    Description:
    Config file:  /Users/ian/Library/Application Support/lolcate/library/config.toml
    Ignores file: /Users/ian/Library/Application Support/lolcate/library/ignores
    Data file:    /Users/ian/Library/Application Support/lolcate/library
  not_ian
    Description:
    Config file:  /Users/ian/Library/Application Support/lolcate/not_ian/config.toml
    Ignores file: /Users/ian/Library/Application Support/lolcate/not_ian/ignores
    Data file:    /Users/ian/Library/Application Support/lolcate/not_ian
  usr_opt_private
    Description:
    Config file:  /Users/ian/Library/Application Support/lolcate/usr_opt_private/config.toml
    Ignores file: /Users/ian/Library/Application Support/lolcate/usr_opt_private/ignores
    Data file:    /Users/ian/Library/Application Support/lolcate/usr_opt_private
  applications
    Description:
    Config file:  /Users/ian/Library/Application Support/lolcate/applications/config.toml
    Ignores file: /Users/ian/Library/Application Support/lolcate/applications/ignores
    Data file:    /Users/ian/Library/Application Support/lolcate/applications

File types:
  doc: .*\.(doc|docx|xls|xlsx|ppt|pptx)$
  audio: .*\.(mp3|m4a|flac|ogg)$
  img: .*\.(jp.?g|png|gif|JP.?G)$
  edoc: .*\.(chm|epub|djvu?|mobi|azw3|odf|ods|md|adoc)$
  pdf: .*\.(pdf)$
  video: .*\.(flv|mp4|mp.?g|avi|wmv|mkv|3gp|m4v|asf|webm)$
  iwork: .*\.(pages|numbers|key)$
  txt: .*\.(txt|text)$

==== 索引文件 *.lz4 大小, 配置文件大小 ====

-rw-r--r--  1 ian  staff    14M  3 17 11:25 /Users/ian/Library/Application Support/lolcate/applications/db.lz4
-rw-r--r--  1 ian  staff   5.5M  3 17 11:24 /Users/ian/Library/Application Support/lolcate/default/db.lz4
-rw-r--r--  1 ian  staff    33M  3 17 11:25 /Users/ian/Library/Application Support/lolcate/library/db.lz4
-rw-r--r--  1 ian  staff    18K  3 17 11:25 /Users/ian/Library/Application Support/lolcate/not_ian/db.lz4
-rw-r--r--  1 ian  staff   3.2M  3 17 11:25 /Users/ian/Library/Application Support/lolcate/usr_opt_private/db.lz4

-rw-r--r--  1 ian  staff   465B 12 14 12:19 /Users/ian/Library/Application Support/lolcate/applications/config.toml
-rw-r--r--  1 ian  staff   373B  7 19  2022 /Users/ian/Library/Application Support/lolcate/config.toml
-rw-r--r--  1 ian  staff   488B  7 19  2022 /Users/ian/Library/Application Support/lolcate/default/config.toml
-rw-r--r--  1 ian  staff   460B 12 14 12:18 /Users/ian/Library/Application Support/lolcate/library/config.toml
-rw-r--r--  1 ian  staff   458B 12 14 12:13 /Users/ian/Library/Application Support/lolcate/not_ian/config.toml
-rw-r--r--  1 ian  staff   480B 12 14 15:40 /Users/ian/Library/Application Support/lolcate/usr_opt_private/config.toml

-rw-r--r--  1 ian  staff    98B 12 14 12:11 /Users/ian/Library/Application Support/lolcate/applications/ignores
-rw-r--r--  1 ian  staff   643B  7 21  2022 /Users/ian/Library/Application Support/lolcate/default/ignores
-rw-r--r--  1 ian  staff    98B 12 14 12:11 /Users/ian/Library/Application Support/lolcate/library/ignores
-rw-r--r--  1 ian  staff   817B 12 14 12:16 /Users/ian/Library/Application Support/lolcate/not_ian/ignores
-rw-r--r--@ 1 ian  staff   144B 12 14 15:41 /Users/ian/Library/Application Support/lolcate/usr_opt_private/ignores

==== 每个索引文件里的文件数量 ====

applications: 1792047
default:  495683
library: 4161431
not_ian:    3330
usr_opt_private:  419624
```

----

## 3. generate_password

```
$cat generate_password

#!/usr/bin/env bash
LC_CTYPE=C tr -dc A-Za-z0-9 < /dev/urandom | head -c 16;echo
```

----

## 4. hex2dec / dec2hex

```
$ cat hex2dec
#!/usr/bin/env bash

HEX_NUM=`echo $1 | tr 'a-fx' 'A-FX'`
TMP_NUM=`echo $HEX_NUM | tr -d [XA-F0-9]`

if [ "${TMP_NUM}" != "" ]; then
    echo "hex chars: [0xXa-fA-F0-9]"
    exit
fi;

if [ "${HEX_NUM:0:2}" = "0X" ]; then
    echo "ibase=16;obase=A;${HEX_NUM:2}"|bc -l
else
    echo "ibase=16;obase=A;${HEX_NUM}"|bc -l
fi;
```

```
$ cat dec2hex
#!/usr/bin/env bash

if [ "`echo $1 | tr -d [0-9]`" != "" ]; then
    echo "dec chars: [0-9]"
    exit
fi;

DEC_NUM=`echo "obase=16;ibase=10;$1"|bc -l`
DEC_NUM2=`echo $DEC_NUM|tr 'A-F' 'a-f'`

echo '0x'$DEC_NUM
echo '0x'$DEC_NUM2
```

----

## 5. dot

```
$ cat Dockerfile

FROM alpine:3.13
RUN apk add --no-cache graphviz ttf-freefont
CMD ["dot"]
```

```
$  cat circo
#!/bin/bash

/usr/local/bin/docker run --rm -v $(pwd):/root -w /root dot:1.0 circo "$@"
```

```
$ cat dot
#!/bin/bash

/usr/local/bin/docker run --rm -v $(pwd):/root -w /root dot:1.0 dot "$@"
```

----

## 6. lilypond

```
$cat Dockerfile

FROM ubuntu:18.04

RUN apt-get update \
  && apt-get install -y --no-install-recommends wget bzip2 fonts-arphic-ukai && wget http://lilypond.org/download/binaries/linux-64/lilypond-2.20.0-1.linux-64.sh && sh ./lilypond-2.20.0-1.linux-64.sh && rm -f ./lilypond-2.20.0-1.linux-64.sh

CMD ["lilypond"]
```

```
$ cat lilybook
#!/bin/bash

#/usr/local/bin/docker run --rm -v $(pwd):/root -w /root 80s_chinese_songs_lilypond:1.0 lilypond-book -f latex --psfonts --output OUTPUT small.tex "$@"
/usr/local/bin/docker run --rm -v $(pwd):/root -w /root 80s_chinese_songs_lilypond:1.0 lilypond-book --pdf --format=latex -o ./12 small.ly
```

```
$ cat lily
#!/bin/bash

/usr/local/bin/docker run --rm -v $(pwd):/root -w /root 80s_chinese_songs_lilypond:1.0 lilypond "$@"
```

## 7. e2c / c2e

(1) 下载、本地启动翻译服务：

https://github.com/OwO-Network/DeepLX

(2) e2c 如下（将zh改为en，则是c2e）

```
$ cat /usr/local/bin/e2c
#!/usr/bin/env bash
if test -f "$1"; then
  xh http://localhost:1188/translate target_lang=zh text="$(cat $1)"
else
  xh http://localhost:1188/translate target_lang=zh text="${1}"
fi
```
## 8. man

复制相关配置到 /usr/local/share/man/man1/ , 以 exa 为例：

```
cp ~/Downloads/exa-macos-x86_64-v0.10.1/man/exa.1  /usr/local/share/man/man1/

man exa
```

## 9. bash5 in macOS

### 9.1 install bash, bash completion

(1) install

```
brew install bash-completion@2  # 没有 @2 适用于 bash3 等低版本。 @2 适用于 bash4.2+ 版本。

sudo bash -c 'echo /usr/local/bin/bash >> /etc/shells'  # 将 bash 5 添加到系统 shells

chsh -s /usr/local/bin/bash # 修改当前用户的默认 shell

#sudo chsh -s /usr/local/bin/bash # 修改系统默认 shell
```

(2) 增加以下配置到 .bash_profile：

```
  [[ -r "/usr/local/etc/profile.d/bash_completion.sh" ]] && . "/usr/local/etc/profile.d/bash_completion.sh"
```

其功能大致相当于下面这几行（但是会先判断为较高的 bash 版本，才执行then）

```
#if [ -f /usr/local/share/bash-completion/bash_completion ]; then
#   . /usr/local/share/bash-completion/bash_completion
#fi
```

### 9.2 bash completion

(1) 复制相关配置到 bash_completion.d/ , 以 fd 为例：

```
cp ~/fd-v8.3.2-x86_64-apple-darwin/autocomplete/fd.bash /usr/local/etc/bash_completion.d/
```

(2) 重启 iterm，输入命令，按两下 TAB 键，自动完成

```
fd - <TAB> <TAB>
```

(3) 安装命令和配置目录对比

| | ubuntu  | MacOS  |
| ------------ | ------------ | ------------ |
| 安装命令 | apt install ...  |  brew install ... |
| 配置目录 |/etc/bash_completion.d   | /usr/local/etc/bash_completion.d  |

(4) 常用的一些 bash_completion:

```
$ exa --oneline /usr/local/etc/bash_completion.d
aria2c.bash
bat.bash
delta.bash
docker.bash
exa.bash
fd.bash
fnm.bash
frum.bash
fzf.bash
git.bash
hg-completion.bash
kubectl.bash
m.bash
mtr.bash
rg.bash
rvm.bash
task.bash
tldr-c.bash
xh.bash
xmake.bash
yq.bash
zoxide.bash
```

### 9.3 bash常用设置

#### 9.3.1  ~/.bashrc

(1) 增加一些常用命令的相关设置，并增加两行用于 hg 和 git 命令的 prompt.sh

```
# zoxide
eval "$(zoxide init bash)"

# fzf
export FZF_DEFAULT_COMMAND='fd --type f'

# fnm
export FNM_DIR="$HOME/.fnm"
eval "$(fnm env --use-on-cd)"
export FNM_LOGLEVEL=error

# git prompt
source ~/.git-prompt.sh

# hg prompt
source ~/.hg-prompt.sh
```

#### 9.3.2 ~/.bash_profile

(1) 增加 PS1 (带有 __hg_ps1 和 __git_ps1)。用 -K 或 --apple-use-keychain，添加带密码的私钥，就不必每次都输入密码。

```
export PS1='\[\033[0;35m\]\u\[\033[m\]@\[\033[0;32m\]\h \[\033[1;34m\]\w$(__hg_ps1 " (%s)")$(__git_ps1 " (%s)")\[\033[m\]\$ '

# add ssh key at the first time
ssh-add --apple-use-keychain ~/.ssh/id_ed25519_xxxx

source ~/.bashrc
```

(2) 进入hg或git的目录，就会在目录名旁边显示当前分支或版本号。示意如下：

```
ian@iandeiMac ~/git_test/feather (master)$
```

#### 9.3.3 ~/.hg-prompt.sh

```
# bash hg prompt support
#
# Copyright (c) 2018 Stephane Moore
# Distributed under the MIT License.
#
# To enable:
#
#    1) Copy this file to somewhere (e.g. ~/.hg-prompt.sh).
#    2) Add the following line to your .bashrc:
#        source ~/.hg-prompt.sh
#    3) Change your PS1 to call __hg_ps1:
#       Bash: PS1='[\u@\h \W$(__hg_ps1 " (%s)")]\$ '
#       the optional argument will be used as format string.

# Constructs a prompt string for the Mercurial repository containing the current working directory
# or nothing if the current working directory is not within a Mercurial repository.
#
# If the HG_PS1_TAGSTEMPLATE environment variable is set, tags will be
# retrieved using the specified template for tags. If this environment
# variable is not set, the template "{tags}" will be used.
__hg_ps1() {
  local exit_code=$?

  local hg_root="$(hg root 2>/dev/null)"

  if [ -z "${hg_root}" ]; then
    return ${exit_code}
  fi

  local printf_format=" (%s)"
  if [ "$#" -ge 1 ]; then
    printf_format="$1"
  fi

  # Show * for modified files, + for added files, and % for untracked files.
  local hg_display_modifiers=""
  local hg_status_summary="$(hg status | cut -c 1)"
  if [[ "${hg_status_summary}" =~ .*M.* ]]; then
    hg_display_modifiers="${hg_display_modifiers}*"
  fi
  if [[ "${hg_status_summary}" =~ .*A.* ]]; then
    hg_display_modifiers="${hg_display_modifiers}+"
  fi
  if [[ "${hg_status_summary}" =~ .*\?.* ]]; then
    hg_display_modifiers="${hg_display_modifiers}%"
  fi

  # Begin constructing the prompt string moving backwards.
  local hg_prompt=""
  if [ "${hg_display_modifiers}" != "" ]; then
    hg_prompt=" ${hg_display_modifiers}"
  fi

  # Check for an active bookmark.
  local hg_current_bookmark="${hg_root}/.hg/bookmarks.current"
  if [ -e "${hg_current_bookmark}" ]; then
    local hg_bookmark_name=$(cat "${hg_current_bookmark}")
    hg_prompt="${hg_bookmark_name}${hg_prompt}"
    printf -- "$1" "${hg_prompt}"
    return ${exit_code}
  fi

  # Check for a tag on the current commit.
  local hg_default_tags_template="{tags}"
  local hg_tags_template="${HG_PS1_TAGSTEMPLATE-$hg_default_tags_template}"
  local hg_tags="$(hg log -r . --template "${hg_tags_template}")"
  local hg_tag_array=( $hg_tags )
  if [ ${#hg_tag_array[@]} -ne 0 ]; then
    for hg_tag in "${hg_tag_array[@]}"
    do
      if [ "${hg_tag}" != "tip" ]; then
        hg_prompt="${hg_tag}${hg_prompt}"
        printf -- "$1" "${hg_prompt}"
        return ${exit_code}
      fi
    done
  fi

  # In the absence of other information, simply display the changeset identifier.
  local hg_changeset_id_hash="$(hg log -r . --template '({node|short})')"
  hg_prompt="${hg_changeset_id_hash}${hg_prompt}"
  printf -- "$1" "${hg_prompt}"
  return ${exit_code}
}
```

#### 9.3.4 ~/.git-prompt.sh

```
# bash/zsh git prompt support
#
# Copyright (C) 2006,2007 Shawn O. Pearce <spearce@spearce.org>
# Distributed under the GNU General Public License, version 2.0.
#
# This script allows you to see repository status in your prompt.
#
# To enable:
#
#    1) Copy this file to somewhere (e.g. ~/.git-prompt.sh).
#    2) Add the following line to your .bashrc/.zshrc:
#        source ~/.git-prompt.sh
#    3a) Change your PS1 to call __git_ps1 as
#        command-substitution:
#        Bash: PS1='[\u@\h \W$(__git_ps1 " (%s)")]\$ '
#        ZSH:  setopt PROMPT_SUBST ; PS1='[%n@%m %c$(__git_ps1 " (%s)")]\$ '
#        the optional argument will be used as format string.
#    3b) Alternatively, for a slightly faster prompt, __git_ps1 can
#        be used for PROMPT_COMMAND in Bash or for precmd() in Zsh
#        with two parameters, <pre> and <post>, which are strings
#        you would put in $PS1 before and after the status string
#        generated by the git-prompt machinery.  e.g.
#        Bash: PROMPT_COMMAND='__git_ps1 "\u@\h:\w" "\\\$ "'
#          will show username, at-sign, host, colon, cwd, then
#          various status string, followed by dollar and SP, as
#          your prompt.
#        ZSH:  precmd () { __git_ps1 "%n" ":%~$ " "|%s" }
#          will show username, pipe, then various status string,
#          followed by colon, cwd, dollar and SP, as your prompt.
#        Optionally, you can supply a third argument with a printf
#        format string to finetune the output of the branch status
#
# The repository status will be displayed only if you are currently in a
# git repository. The %s token is the placeholder for the shown status.
#
# The prompt status always includes the current branch name.
#
# In addition, if you set GIT_PS1_SHOWDIRTYSTATE to a nonempty value,
# unstaged (*) and staged (+) changes will be shown next to the branch
# name.  You can configure this per-repository with the
# bash.showDirtyState variable, which defaults to true once
# GIT_PS1_SHOWDIRTYSTATE is enabled.
#
# You can also see if currently something is stashed, by setting
# GIT_PS1_SHOWSTASHSTATE to a nonempty value. If something is stashed,
# then a '$' will be shown next to the branch name.
#
# If you would like to see if there're untracked files, then you can set
# GIT_PS1_SHOWUNTRACKEDFILES to a nonempty value. If there're untracked
# files, then a '%' will be shown next to the branch name.  You can
# configure this per-repository with the bash.showUntrackedFiles
# variable, which defaults to true once GIT_PS1_SHOWUNTRACKEDFILES is
# enabled.
#
# If you would like to see the difference between HEAD and its upstream,
# set GIT_PS1_SHOWUPSTREAM="auto".  A "<" indicates you are behind, ">"
# indicates you are ahead, "<>" indicates you have diverged and "="
# indicates that there is no difference. You can further control
# behaviour by setting GIT_PS1_SHOWUPSTREAM to a space-separated list
# of values:
#
#     verbose       show number of commits ahead/behind (+/-) upstream
#     name          if verbose, then also show the upstream abbrev name
#     legacy        don't use the '--count' option available in recent
#                   versions of git-rev-list
#     git           always compare HEAD to @{upstream}
#     svn           always compare HEAD to your SVN upstream
#
# By default, __git_ps1 will compare HEAD to your SVN upstream if it can
# find one, or @{upstream} otherwise.  Once you have set
# GIT_PS1_SHOWUPSTREAM, you can override it on a per-repository basis by
# setting the bash.showUpstream config variable.
#
# You can change the separator between the branch name and the above
# state symbols by setting GIT_PS1_STATESEPARATOR. The default separator
# is SP.
#
# When there is an in-progress operation such as a merge, rebase,
# revert, cherry-pick, or bisect, the prompt will include information
# related to the operation, often in the form "|<OPERATION-NAME>".
#
# When the repository has a sparse-checkout, a notification of the form
# "|SPARSE" will be included in the prompt.  This can be shortened to a
# single '?' character by setting GIT_PS1_COMPRESSSPARSESTATE, or omitted
# by setting GIT_PS1_OMITSPARSESTATE.
#
# If you would like to see a notification on the prompt when there are
# unresolved conflicts, set GIT_PS1_SHOWCONFLICTSTATE to "yes". The
# prompt will include "|CONFLICT".
#
# If you would like to see more information about the identity of
# commits checked out as a detached HEAD, set GIT_PS1_DESCRIBE_STYLE
# to one of these values:
#
#     contains      relative to newer annotated tag (v1.6.3.2~35)
#     branch        relative to newer tag or branch (master~4)
#     describe      relative to older annotated tag (v1.6.3.1-13-gdd42c2f)
#     tag           relative to any older tag (v1.6.3.1-13-gdd42c2f)
#     default       exactly matching tag
#
# If you would like a colored hint about the current dirty state, set
# GIT_PS1_SHOWCOLORHINTS to a nonempty value. The colors are based on
# the colored output of "git status -sb" and are available only when
# using __git_ps1 for PROMPT_COMMAND or precmd in Bash,
# but always available in Zsh.
#
# If you would like __git_ps1 to do nothing in the case when the current
# directory is set up to be ignored by git, then set
# GIT_PS1_HIDE_IF_PWD_IGNORED to a nonempty value. Override this on the
# repository level by setting bash.hideIfPwdIgnored to "false".

# check whether printf supports -v
__git_printf_supports_v=
printf -v __git_printf_supports_v -- '%s' yes >/dev/null 2>&1

# stores the divergence from upstream in $p
# used by GIT_PS1_SHOWUPSTREAM
__git_ps1_show_upstream ()
{
	local key value
	local svn_remote svn_url_pattern count n
	local upstream_type=git legacy="" verbose="" name=""

	svn_remote=()
	# get some config options from git-config
	local output="$(git config -z --get-regexp '^(svn-remote\..*\.url|bash\.showupstream)$' 2>/dev/null | tr '\0\n' '\n ')"
	while read -r key value; do
		case "$key" in
		bash.showupstream)
			GIT_PS1_SHOWUPSTREAM="$value"
			if [[ -z "${GIT_PS1_SHOWUPSTREAM}" ]]; then
				p=""
				return
			fi
			;;
		svn-remote.*.url)
			svn_remote[$((${#svn_remote[@]} + 1))]="$value"
			svn_url_pattern="$svn_url_pattern\\|$value"
			upstream_type=svn+git # default upstream type is SVN if available, else git
			;;
		esac
	done <<< "$output"

	# parse configuration values
	local option
	for option in ${GIT_PS1_SHOWUPSTREAM}; do
		case "$option" in
		git|svn) upstream_type="$option" ;;
		verbose) verbose=1 ;;
		legacy)  legacy=1  ;;
		name)    name=1 ;;
		esac
	done

	# Find our upstream type
	case "$upstream_type" in
	git)    upstream_type="@{upstream}" ;;
	svn*)
		# get the upstream from the "git-svn-id: ..." in a commit message
		# (git-svn uses essentially the same procedure internally)
		local -a svn_upstream
		svn_upstream=($(git log --first-parent -1 \
					--grep="^git-svn-id: \(${svn_url_pattern#??}\)" 2>/dev/null))
		if [[ 0 -ne ${#svn_upstream[@]} ]]; then
			svn_upstream=${svn_upstream[${#svn_upstream[@]} - 2]}
			svn_upstream=${svn_upstream%@*}
			local n_stop="${#svn_remote[@]}"
			for ((n=1; n <= n_stop; n++)); do
				svn_upstream=${svn_upstream#${svn_remote[$n]}}
			done

			if [[ -z "$svn_upstream" ]]; then
				# default branch name for checkouts with no layout:
				upstream_type=${GIT_SVN_ID:-git-svn}
			else
				upstream_type=${svn_upstream#/}
			fi
		elif [[ "svn+git" = "$upstream_type" ]]; then
			upstream_type="@{upstream}"
		fi
		;;
	esac

	# Find how many commits we are ahead/behind our upstream
	if [[ -z "$legacy" ]]; then
		count="$(git rev-list --count --left-right \
				"$upstream_type"...HEAD 2>/dev/null)"
	else
		# produce equivalent output to --count for older versions of git
		local commits
		if commits="$(git rev-list --left-right "$upstream_type"...HEAD 2>/dev/null)"
		then
			local commit behind=0 ahead=0
			for commit in $commits
			do
				case "$commit" in
				"<"*) ((behind++)) ;;
				*)    ((ahead++))  ;;
				esac
			done
			count="$behind	$ahead"
		else
			count=""
		fi
	fi

	# calculate the result
	if [[ -z "$verbose" ]]; then
		case "$count" in
		"") # no upstream
			p="" ;;
		"0	0") # equal to upstream
			p="=" ;;
		"0	"*) # ahead of upstream
			p=">" ;;
		*"	0") # behind upstream
			p="<" ;;
		*)	    # diverged from upstream
			p="<>" ;;
		esac
	else # verbose, set upstream instead of p
		case "$count" in
		"") # no upstream
			upstream="" ;;
		"0	0") # equal to upstream
			upstream="|u=" ;;
		"0	"*) # ahead of upstream
			upstream="|u+${count#0	}" ;;
		*"	0") # behind upstream
			upstream="|u-${count%	0}" ;;
		*)	    # diverged from upstream
			upstream="|u+${count#*	}-${count%	*}" ;;
		esac
		if [[ -n "$count" && -n "$name" ]]; then
			__git_ps1_upstream_name=$(git rev-parse \
				--abbrev-ref "$upstream_type" 2>/dev/null)
			if [ $pcmode = yes ] && [ $ps1_expanded = yes ]; then
				upstream="$upstream \${__git_ps1_upstream_name}"
			else
				upstream="$upstream ${__git_ps1_upstream_name}"
				# not needed anymore; keep user's
				# environment clean
				unset __git_ps1_upstream_name
			fi
		fi
	fi

}

# Helper function that is meant to be called from __git_ps1.  It
# injects color codes into the appropriate gitstring variables used
# to build a gitstring. Colored variables are responsible for clearing
# their own color.
__git_ps1_colorize_gitstring ()
{
	if [[ -n ${ZSH_VERSION-} ]]; then
		local c_red='%F{red}'
		local c_green='%F{green}'
		local c_lblue='%F{blue}'
		local c_clear='%f'
	else
		# Using \[ and \] around colors is necessary to prevent
		# issues with command line editing/browsing/completion!
		local c_red='\[\e[31m\]'
		local c_green='\[\e[32m\]'
		local c_lblue='\[\e[1;34m\]'
		local c_clear='\[\e[0m\]'
	fi
	local bad_color=$c_red
	local ok_color=$c_green
	local flags_color="$c_lblue"

	local branch_color=""
	if [ $detached = no ]; then
		branch_color="$ok_color"
	else
		branch_color="$bad_color"
	fi
	if [ -n "$c" ]; then
		c="$branch_color$c$c_clear"
	fi
	b="$branch_color$b$c_clear"

	if [ -n "$w" ]; then
		w="$bad_color$w$c_clear"
	fi
	if [ -n "$i" ]; then
		i="$ok_color$i$c_clear"
	fi
	if [ -n "$s" ]; then
		s="$flags_color$s$c_clear"
	fi
	if [ -n "$u" ]; then
		u="$bad_color$u$c_clear"
	fi
}

# Helper function to read the first line of a file into a variable.
# __git_eread requires 2 arguments, the file path and the name of the
# variable, in that order.
__git_eread ()
{
	test -r "$1" && IFS=$'\r\n' read "$2" <"$1"
}

# see if a cherry-pick or revert is in progress, if the user has committed a
# conflict resolution with 'git commit' in the middle of a sequence of picks or
# reverts then CHERRY_PICK_HEAD/REVERT_HEAD will not exist so we have to read
# the todo file.
__git_sequencer_status ()
{
	local todo
	if test -f "$g/CHERRY_PICK_HEAD"
	then
		r="|CHERRY-PICKING"
		return 0;
	elif test -f "$g/REVERT_HEAD"
	then
		r="|REVERTING"
		return 0;
	elif __git_eread "$g/sequencer/todo" todo
	then
		case "$todo" in
		p[\ \	]|pick[\ \	]*)
			r="|CHERRY-PICKING"
			return 0
		;;
		revert[\ \	]*)
			r="|REVERTING"
			return 0
		;;
		esac
	fi
	return 1
}

# __git_ps1 accepts 0 or 1 arguments (i.e., format string)
# when called from PS1 using command substitution
# in this mode it prints text to add to bash PS1 prompt (includes branch name)
#
# __git_ps1 requires 2 or 3 arguments when called from PROMPT_COMMAND (pc)
# in that case it _sets_ PS1. The arguments are parts of a PS1 string.
# when two arguments are given, the first is prepended and the second appended
# to the state string when assigned to PS1.
# The optional third parameter will be used as printf format string to further
# customize the output of the git-status string.
# In this mode you can request colored hints using GIT_PS1_SHOWCOLORHINTS=true
__git_ps1 ()
{
	# preserve exit status
	local exit=$?
	local pcmode=no
	local detached=no
	local ps1pc_start='\u@\h:\w '
	local ps1pc_end='\$ '
	local printf_format=' (%s)'

	case "$#" in
		2|3)	pcmode=yes
			ps1pc_start="$1"
			ps1pc_end="$2"
			printf_format="${3:-$printf_format}"
			# set PS1 to a plain prompt so that we can
			# simply return early if the prompt should not
			# be decorated
			PS1="$ps1pc_start$ps1pc_end"
		;;
		0|1)	printf_format="${1:-$printf_format}"
		;;
		*)	return $exit
		;;
	esac

	# ps1_expanded:  This variable is set to 'yes' if the shell
	# subjects the value of PS1 to parameter expansion:
	#
	#   * bash does unless the promptvars option is disabled
	#   * zsh does not unless the PROMPT_SUBST option is set
	#   * POSIX shells always do
	#
	# If the shell would expand the contents of PS1 when drawing
	# the prompt, a raw ref name must not be included in PS1.
	# This protects the user from arbitrary code execution via
	# specially crafted ref names.  For example, a ref named
	# 'refs/heads/$(IFS=_;cmd=sudo_rm_-rf_/;$cmd)' might cause the
	# shell to execute 'sudo rm -rf /' when the prompt is drawn.
	#
	# Instead, the ref name should be placed in a separate global
	# variable (in the __git_ps1_* namespace to avoid colliding
	# with the user's environment) and that variable should be
	# referenced from PS1.  For example:
	#
	#     __git_ps1_foo=$(do_something_to_get_ref_name)
	#     PS1="...stuff...\${__git_ps1_foo}...stuff..."
	#
	# If the shell does not expand the contents of PS1, the raw
	# ref name must be included in PS1.
	#
	# The value of this variable is only relevant when in pcmode.
	#
	# Assume that the shell follows the POSIX specification and
	# expands PS1 unless determined otherwise.  (This is more
	# likely to be correct if the user has a non-bash, non-zsh
	# shell and safer than the alternative if the assumption is
	# incorrect.)
	#
	local ps1_expanded=yes
	[ -z "${ZSH_VERSION-}" ] || [[ -o PROMPT_SUBST ]] || ps1_expanded=no
	[ -z "${BASH_VERSION-}" ] || shopt -q promptvars || ps1_expanded=no

	local repo_info rev_parse_exit_code
	repo_info="$(git rev-parse --git-dir --is-inside-git-dir \
		--is-bare-repository --is-inside-work-tree \
		--short HEAD 2>/dev/null)"
	rev_parse_exit_code="$?"

	if [ -z "$repo_info" ]; then
		return $exit
	fi

	local short_sha=""
	if [ "$rev_parse_exit_code" = "0" ]; then
		short_sha="${repo_info##*$'\n'}"
		repo_info="${repo_info%$'\n'*}"
	fi
	local inside_worktree="${repo_info##*$'\n'}"
	repo_info="${repo_info%$'\n'*}"
	local bare_repo="${repo_info##*$'\n'}"
	repo_info="${repo_info%$'\n'*}"
	local inside_gitdir="${repo_info##*$'\n'}"
	local g="${repo_info%$'\n'*}"

	if [ "true" = "$inside_worktree" ] &&
	   [ -n "${GIT_PS1_HIDE_IF_PWD_IGNORED-}" ] &&
	   [ "$(git config --bool bash.hideIfPwdIgnored)" != "false" ] &&
	   git check-ignore -q .
	then
		return $exit
	fi

	local sparse=""
	if [ -z "${GIT_PS1_COMPRESSSPARSESTATE-}" ] &&
	   [ -z "${GIT_PS1_OMITSPARSESTATE-}" ] &&
	   [ "$(git config --bool core.sparseCheckout)" = "true" ]; then
		sparse="|SPARSE"
	fi

	local r=""
	local b=""
	local step=""
	local total=""
	if [ -d "$g/rebase-merge" ]; then
		__git_eread "$g/rebase-merge/head-name" b
		__git_eread "$g/rebase-merge/msgnum" step
		__git_eread "$g/rebase-merge/end" total
		r="|REBASE"
	else
		if [ -d "$g/rebase-apply" ]; then
			__git_eread "$g/rebase-apply/next" step
			__git_eread "$g/rebase-apply/last" total
			if [ -f "$g/rebase-apply/rebasing" ]; then
				__git_eread "$g/rebase-apply/head-name" b
				r="|REBASE"
			elif [ -f "$g/rebase-apply/applying" ]; then
				r="|AM"
			else
				r="|AM/REBASE"
			fi
		elif [ -f "$g/MERGE_HEAD" ]; then
			r="|MERGING"
		elif __git_sequencer_status; then
			:
		elif [ -f "$g/BISECT_LOG" ]; then
			r="|BISECTING"
		fi

		if [ -n "$b" ]; then
			:
		elif [ -h "$g/HEAD" ]; then
			# symlink symbolic ref
			b="$(git symbolic-ref HEAD 2>/dev/null)"
		else
			local head=""
			if ! __git_eread "$g/HEAD" head; then
				return $exit
			fi
			# is it a symbolic ref?
			b="${head#ref: }"
			if [ "$head" = "$b" ]; then
				detached=yes
				b="$(
				case "${GIT_PS1_DESCRIBE_STYLE-}" in
				(contains)
					git describe --contains HEAD ;;
				(branch)
					git describe --contains --all HEAD ;;
				(tag)
					git describe --tags HEAD ;;
				(describe)
					git describe HEAD ;;
				(* | default)
					git describe --tags --exact-match HEAD ;;
				esac 2>/dev/null)" ||

				b="$short_sha..."
				b="($b)"
			fi
		fi
	fi

	if [ -n "$step" ] && [ -n "$total" ]; then
		r="$r $step/$total"
	fi

	local conflict="" # state indicator for unresolved conflicts
	if [[ "${GIT_PS1_SHOWCONFLICTSTATE}" == "yes" ]] &&
	   [[ $(git ls-files --unmerged 2>/dev/null) ]]; then
		conflict="|CONFLICT"
	fi

	local w=""
	local i=""
	local s=""
	local u=""
	local h=""
	local c=""
	local p="" # short version of upstream state indicator
	local upstream="" # verbose version of upstream state indicator

	if [ "true" = "$inside_gitdir" ]; then
		if [ "true" = "$bare_repo" ]; then
			c="BARE:"
		else
			b="GIT_DIR!"
		fi
	elif [ "true" = "$inside_worktree" ]; then
		if [ -n "${GIT_PS1_SHOWDIRTYSTATE-}" ] &&
		   [ "$(git config --bool bash.showDirtyState)" != "false" ]
		then
			git diff --no-ext-diff --quiet || w="*"
			git diff --no-ext-diff --cached --quiet || i="+"
			if [ -z "$short_sha" ] && [ -z "$i" ]; then
				i="#"
			fi
		fi
		if [ -n "${GIT_PS1_SHOWSTASHSTATE-}" ] &&
		   git rev-parse --verify --quiet refs/stash >/dev/null
		then
			s="$"
		fi

		if [ -n "${GIT_PS1_SHOWUNTRACKEDFILES-}" ] &&
		   [ "$(git config --bool bash.showUntrackedFiles)" != "false" ] &&
		   git ls-files --others --exclude-standard --directory --no-empty-directory --error-unmatch -- ':/*' >/dev/null 2>/dev/null
		then
			u="%${ZSH_VERSION+%}"
		fi

		if [ -n "${GIT_PS1_COMPRESSSPARSESTATE-}" ] &&
		   [ "$(git config --bool core.sparseCheckout)" = "true" ]; then
			h="?"
		fi

		if [ -n "${GIT_PS1_SHOWUPSTREAM-}" ]; then
			__git_ps1_show_upstream
		fi
	fi

	local z="${GIT_PS1_STATESEPARATOR-" "}"

	b=${b##refs/heads/}
	if [ $pcmode = yes ] && [ $ps1_expanded = yes ]; then
		__git_ps1_branch_name=$b
		b="\${__git_ps1_branch_name}"
	fi

	# NO color option unless in PROMPT_COMMAND mode or it's Zsh
	if [ -n "${GIT_PS1_SHOWCOLORHINTS-}" ]; then
		if [ $pcmode = yes ] || [ -n "${ZSH_VERSION-}" ]; then
			__git_ps1_colorize_gitstring
		fi
	fi

	local f="$h$w$i$s$u$p"
	local gitstring="$c$b${f:+$z$f}${sparse}$r${upstream}${conflict}"

	if [ $pcmode = yes ]; then
		if [ "${__git_printf_supports_v-}" != yes ]; then
			gitstring=$(printf -- "$printf_format" "$gitstring")
		else
			printf -v gitstring -- "$printf_format" "$gitstring"
		fi
		PS1="$ps1pc_start$gitstring$ps1pc_end"
	else
		printf -- "$printf_format" "$gitstring"
	fi

	return $exit
}
```
