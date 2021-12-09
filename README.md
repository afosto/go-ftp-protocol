go-ftp-protocol
===============

Plugin for http.Transport with support for ftp:// protocol in Go.

Limitations:  only file retrieval operations.
authentication in case of the url containing the username password

Internally connections to FTP servers are cached and re-used when possible.

Example usage:

    import "github.com/afosto/go-ftp-protocol/protocol"

    transport := &http.Transport{}
    transport.RegisterProtocol("ftp", &protocol.FTPRoundTripper{})

    client := &http.Client{Transport: transport}

    resp, err := client.Get("ftp://ftp.ru.debian.org/debian/README")

License: MIT

Base on FTP client library: http://github.com/jlaffaye/ftp/