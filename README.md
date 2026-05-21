# Snapcraft Action

**GitHub Action for setting up Snapcraft**

This action installs snapd and snapcraft, and logins into snapcraft for build

Example:
```yaml
name: My workflow

on: push

jobs:
  my-job:
    runs-on: ubuntu-latest
    env:
      SNAPCRAFT_STORE_CREDENTIALS: ${{ secrets.SNAPCRAFT_TOKEN }}
    steps:
      - name: Check out Git repository
        uses: actions/checkout@v3

      - name: Install Snapcraft
        uses: lucassabreu/action-snapcraft@v3

      # You can now run Snapcraft shell commands
      - name: Use Snapcraft
        run: snapcraft --help
```

Based on https://github.com/samuelmeuli/action-snapcraft and https://github.com/snapcore/action-build
