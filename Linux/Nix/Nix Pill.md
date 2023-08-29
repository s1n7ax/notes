# nix-env

- Installing hello to current user environment

```shell
# installs hello to /nix/store and link the output to user invironment
nix-env -i hello
```

- List installed derivations

```shell
# list just the names
nix-env -q

# list the names and the paths in the user environment
nix-env -q --out-path
```

- Rollback to last generation

```shell
# rollback to the last generation
nix-env --rollback

# rollback to nth generation
nix-env -G 3
```

# nix-store

- List direct runtime dependencies of a derivation

```shell
# only the direct runtime dependencies
nix-store -q --references `which hello`

# list the closure
# this includes every dependency recursivly to run the hello
# command
nix-store -qR `which hello`

# list the closure but in a tree structure
nix-store -q --tree `which hello`
```

- List derivations depending on the given derivation

```shell
nix-store -q --referrers `which hello`
```


