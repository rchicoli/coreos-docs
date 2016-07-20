# Generating signing keys for ACI conversion

## Download the generation script and config

Download the files [aci-signing-key-batch](aci-signing-key-batch) and [generate-signing-keys.sh](generate-signing-keys.sh) next to your configuration directory.

## Make sure the generation script is executable

```sh
chmod +x generate-signing-keys.sh
```

## Edit the configuration

Edit the [aci-signing-key-batch](aci-signing-key-batch) configuration, replacing the email address, name and comment.

## Run the generation script

Run the generation script, pointing it to an output config directory.

```sh
./generate-signing-keys.sh outputdir
```

The files will be generated as `signing-private.gpg` and `signing-public.gpg`:

```
Generating initial keys
gpg: Generating a default key
gpg: done
Generating public signing key
Determining private key
Exporting private signing key
Private key name: CBFB447F
Cleaning up
Emitted outputdir/signing-private.gpg and outputdir/signing-public.gpg
```

Take note of the private key's name.

## Enter config in superuser panel

Upload the `signing-private.gpg` and `signing-public.gpg` files as the keys, and enter the generated key's name. Save the configuration and restart Quay Enterprise to enable signed ACI conversion.