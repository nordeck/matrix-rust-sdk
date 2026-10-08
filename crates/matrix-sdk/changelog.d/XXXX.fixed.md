Remove the session tokens from the `Client` again when an OAuth 2.0 login
fails, or its future is dropped, after the tokens were obtained but before the
session was set. Previously, cancelling `OAuth::finish_login()`,
`OAuth::login_with_qr_code()` or `OAuth::login_with_device_code()` while the
session was being loaded left the tokens on the client without a session.
