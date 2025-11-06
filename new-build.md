# New Build Information

This document outlines the recent updates to the ACME DNS server, focusing on changes to TXT record validation and logging.

## TXT Record Validation

The validation for TXT records sent to the `/update` endpoint has been relaxed. Previously, the server only accepted TXT records with a fixed length of 43 characters. This has been updated to accept any string with a length between 1 and 129 characters. This change allows for more flexible and human-readable TXT records during testing and development.

## Enhanced Logging

The logging for the `/register` and `/update` endpoints has been enhanced to provide more detailed diagnostic information. Log levels have been increased from `Debug` to `Info` and `Error`, making it easier to identify and troubleshoot issues in a production environment. The log messages now include more contextual information, such as the username, subdomain, and the specific error encountered.

## Configuration

The ACME DNS server is configured using a file named `config.cfg`. The application searches for this file in the following locations, in order:

1.  The path specified by the `-c` command-line flag.
2.  `/etc/acme-dns/config.cfg`
3.  `./config.cfg`

There are no build-time configuration options available. All configuration is handled through the `config.cfg` file at runtime.
