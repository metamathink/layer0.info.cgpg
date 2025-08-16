res = subprocess.run(
  [
    "gpg",
    "--rfc4880",
    "-z0",
    "--symmetric",
    "--cipher-algo", "AES256",
    "--no-symkey-cache",
    "--batch",
    "--pinentry-mode", "loopback",
    "--passphrase", saps,
    "--force-mdc",
    "--s2k-mode", x,
    "--s2k-count", y,
    "--verbose",
    "--output", enc_out_path,
    ul_file
  ],
  capture_output=True, text=True
)
