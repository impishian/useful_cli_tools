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
| default |  "~/" | 参加上面文件 |
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

1. 下载、本地启动翻译服务： https://github.com/OwO-Network/DeepLX

2. e2c 如下（将zh改为en，则是c2e）

```
$ cat /usr/local/bin/e2c
#!/usr/bin/env bash
if test -f "$1"; then
  xh http://localhost:1188/translate target_lang=zh text="$(cat $1)"
else
  xh http://localhost:1188/translate target_lang=zh text="${1}"
fi
```
