- Use following command to export the key to a file

```shell
gpg -o ~/secret-keys.asc --export-secret-key  <key>
```

- Use following to list all the keys available

```shell
gpg --list-secret-keys
```