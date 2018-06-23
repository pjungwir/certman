# selfsign

Generates an SSL key and self-signed wildcard cert.
The cert will use Subject Alternate Names (SAN)
to augment the `*.example.com` Common Name (CN)
with the bare name as well (just `example.com`).
When you buy a cert,
pretty much every vendor adds this automatically,
but if you follow typical online instructions to self-sign your own,
it will cover only `*.example.com`, not `example.com`,
so browsers will complain if you visit the bare domain.

Generating a cert with SANs requires an extra openssl config file,
so it's convenient to have a script that does all that for you.

# Usage

    selfsign example.com

This will create two files in the current directory:

    example.com.key       - a 2048-bit RSA key
    STAR.example.com.crt  - the self-signed cert

# Author

Paul A. Jungwirth <pj@illuminatedcomputing.com>

# License

MIT
