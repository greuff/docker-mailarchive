Provides an IMAP interface to a Dovecot [mdbox](https://wiki2.dovecot.org/MailboxFormat/dbox) volume.

Designed for running as a short-term, single-account IMAP server for importing email for archival and later searching via IMAP.

## Instructions

Run the container:

```
$ docker run -p 143:143 -v "$(pwd)/mail:/mail" -e "IMAP_USER=greuff" -e "IMAP_PASS=xxx" -e "UID=501" -e "GID=20" greuff/mailarchive
```

You can override the IMAP username/password, UID, and GID with the environment variables `IMAP_USER`, `IMAP_PASS`, `UID`, and `GID`.

Original project from https://github.com/ilianaw/dockerfiles and modified by Thomas Wana in 2018:

* Don't generate an SSL certificate and don't start SSL - not required for a local archive.
