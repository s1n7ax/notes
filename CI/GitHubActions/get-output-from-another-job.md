# How to get an output from another job

```yaml
name: Test
on:
  workflow_dispatch:

jobs:
  one:
    runs-on: ubuntu-latest
    outputs:
      HELLO: "${{ steps.set-some-stuff.outputs.HELLO }}"
    steps:
      - name: one-1
        id: set-some-stuff
        run: |
          echo "HELLO=WORLD" >> "$GITHUB_OUTPUT"
      - name: one-2
        run: |
          echo "${{ steps.set-some-stuff.outputs.HELLO }}"
  two:
    runs-on: ubuntu-latest
    needs: one
    steps:
      - name: two-1
        run: |
          echo "${{ needs.one.outputs.HELLO }}"
```
