# vaultgnupg

Scripts to link ansible-vault and GnuPG.

Encrypted passwords are stored in `~/.local/share/vaultgnupg/` using file
name set to a git remote URL in git@ format if it could be determined or
current directory name otherwise, with `/` replaced with `⌿`.

## Installation

Just save `vaultgnupg` script from repo into any directory in `$PATH` and
make it executable. You can rename it to `vaultkeychain` if you wanna use
it instead of https://github.com/gitinsky/vaultkeychain.

## Usage

Usually it will be called automatically by Ansible.

```
$ vaultgnupg -h
Usage:
	vaultgnupg
		add/get vault password for current repo or dir
	vaultgnupg -r
		replace vault password for current repo or dir
	vaultgnupg -h|--help
		show this information
```

### ansible.cfg:

```ini
[defaults]
vault_password_file = vaultgnupg
```
