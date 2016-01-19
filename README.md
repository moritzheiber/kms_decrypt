# KMS decrypt

A small (and very stupid, i.e. no error checking) KMS decryption script.

## Prerequisites

`kms_decrypt` has been tested with the following dependencies:

- [Ruby >= 2.2.x](https://ruby-lang.org)
- [Bundler >= 1.11.2](https://bundler.io)

## Setup

```sh
bundle install --path vendor/bundle
```

## Usage

This simple script can be used to decrypt credentials encrypted via AWS KMS. You'll need access to the relevant KMS keys used to encrypt the secret originally.
To use `kms_decrypt` with the base64 encoded ciphertext blob you've gotten from your trusted source just run:

```sh
$ ./kms_decrypt "CasAAAfGG3242jdj3993d9j/93d23jjvvjdjw939jj+ss9s99ddAAaa="
```

_Note: The quotes shouldn't be necessary, but they are also not going to interfere with operations._

`kms_decrypt` will fail (and complain) if there is no blob provided.

If you access rights are sufficient and the KMS key exists you'll get a prompt with the decrypted secret:

```sh
Secret: HelloWorld!
```
