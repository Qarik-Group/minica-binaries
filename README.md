# Minica CLI binaries

[`minica`](https://github.com/jsha/minica) is a small, simple CA intended for use in situations where the CA operator also operates each host where a certificate will be used. It's releases do not include pre-compiled binaries, so end users must have Golang installed to build/install the CLI from source.

This project provides pre-compiled binaries for `minica` via a Concourse CI pipeline for Linux and MacOS.

In addition, we will maintain Homebrew and Debian packages to install these binaries.

For MacOS:

```plain
brew install starkandwayne/kubernetes/minica
```

For Debian/Ubuntu:

```plain
wget -q -O - https://raw.githubusercontent.com/starkandwayne/homebrew-cf/master/public.key | apt-key add -
echo "deb http://apt.starkandwayne.com stable main" | tee /etc/apt/sources.list.d/starkandwayne.list
apt-get update

apt-get install minica
```

## Example usage

```plain
# Generate a root key and cert in minica-key.pem, and minica.pem, then
# generate and sign an end-entity key and cert, storing them in ./foo.com/
$ minica --domains foo.com
```
