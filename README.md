# ansible-aws_cli

Installs AWS CLI v2 on Red Hat-family Linux systems with `x86_64` or `aarch64`
processors and exposes `aws` at `/usr/local/bin/aws` and `/usr/bin/aws`. Other OS
families are unchanged. The role manages no services.

Run with root privileges and gathered facts. A fresh installation downloads the
current AWS installer from `awscli.amazonaws.com`; the managed host needs HTTPS
access to that endpoint. An existing `/usr/local/bin/aws` prevents installation,
so subsequent runs do not upgrade or replace it.

The role has no public variables and does not configure AWS credentials. In check
mode, it checks prerequisites but skips a fresh installation and its symlink.
