# SSH

Basic SSH related commands and notes.

## Commands

- `ssh-keygen` - generates a new public/private key pair

- `ssh-copy-id user@remotehost` - copies SSH public key to remote host (password-less login)

- `ssh -i path_to_private_key user@remotehost` - log in using private key

- `ssh-keygen -y -f path_to_private_key` - generates a public key from your private key

## Notes

Public keys are typically added in `.ssh/authorized_keys` for password-less log in.

Private key requires correct permissions: `chmod 600 path_to_private_key`