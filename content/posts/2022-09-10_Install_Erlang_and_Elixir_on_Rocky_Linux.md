---
title: "Install Erlang and Elixir on Rocky Linux (CentOS/RHEL)"
date: 2022-09-10T22:22:30Z
draft: false
tags: ["elixir", "erlang", "rocky-linux", "rhel", "centos", "linux"]
---

For several years I have heard about these two languages, [Erlang][1] and [Elixir][2], and this
week I thought it'll be worth to try them. So, first things first, let start installing them in
my machine. So, normally the installation process on Linux should be straight forward, as in the
documentation ([1][3],[2][4]), but for [Rocky Linux][5] and other RedHat based distros you need a
couple of steps more in order to add a repository from [Erlang Solutions][6].

```bash
wget https://packages.erlang-solutions.com/erlang-solutions-2.0-1.noarch.rpm
sudo dnf localinstall erlang-solutions-2.0-1.noarch.rpm
sudo dnf update
sudo dnf install erlang elixir
```

And later we can try the languages typing their interactive interpreters, `erl` for Erlang:

```text
$ erl
Erlang/OTP 24 [erts-12.1.5] [source] [64-bit] [smp:4:4] [ds:4:4:10] [async-threads:1] [jit]

Eshell V12.1.5  (abort with ^G)
1>
```

and `iex` for Elixir:

```text
$ iex
Erlang/OTP 24 [erts-12.1.5] [source] [64-bit] [smp:4:4] [ds:4:4:10] [async-threads:1] [jit]

Interactive Elixir (1.13.0) - press Ctrl+C to exit (type h() ENTER for help)
iex(1)>
```

See you next time.

[1]: https://www.erlang.org/
[2]: https://elixir-lang.org/
[3]: https://www.erlang.org/downloads
[4]: https://elixir-lang.org/install.html
[5]: https://rockylinux.org/
[6]: https://www.erlang-solutions.com/downloads/
