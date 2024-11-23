TIL - asdf Erlang

To install Erlang with `asdf`

```bash
asdf install erlang 27.0
```

This won't install OpenSSL for some reason; however, install OpenSSL with Homebrew

```bash
brew install openssl
```

Run `brew ls --versions openssl` to see installed, and run `brew --prefix openssl@3` to see the path

Then in your `.bashrc` add this to `KERL_CONFIGURE`

```bash
cat ~/.bashrc

export KERL_CONFIGURE_OPTIONS="--without-javac --with-ssl=/home/linuxbrew/.linuxbrew/opt/openssl@3"
```

Finally, run `asdf install erlang` again.

