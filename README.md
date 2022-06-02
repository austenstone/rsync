# rsync
This repository demonstrates how to use [rsync](https://linux.die.net/man/1/rsync) with [GitHub Actions](https://docs.github.com/en/actions). rsync is a fast, versatile, remote (and local) file-copying tool. It's great for deployment but there are many use cases.

## Gotchas
1. The SSH key, username, and host should be stored as [secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).
2. You must put the secret SSH key in a file and ensure the file has permission 600 (-rw-------)
3. You need to specify the remote shell settings `-e "ssh -o StrictHostKeyChecking=no -i key.pem"`
   - `-o StrictHostKeyChecking=no` ignores the host key check.
   - `-i key.pem` specifies to use the SSH key

See the [workflow file](https://github.com/austenstone/rsync/blob/main/.github/workflows/rsync.yml) and the [actions run](https://github.com/austenstone/rsync/runs/6708535239?check_suite_focus=true)
