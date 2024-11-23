# TIL - gitlab mac runner

Logged user must be same as the one on project, runner should be installed under that user as well.

Documentation from Gitlab is uncomplete:

```bash
gitlab-runner install --user <user>
```

## Signing

For iOS projects, using xcode, move all build commands into build.sh since gitlab runner is using bash, and mac has zshell.

```yaml

...

build:
    script:
        - |
          zsh -c '
            chmod +x build.sh
            ./build.sh
          '
    when: manual
```

