# pre-commit hook for commitlint

A [pre-commit hook][0] for [commitlint][1].

It is agnostic about rulesets, in the sense that it doesn't start out with
`@commitlint/config-conventional` as a base per se. What you need to do besides
adding this to your `.pre-commit-config.yaml` like so:

```yaml
  - repo: https://github.com/solarmonkey/commitlint-pre-commit-hook
    rev: main
    hooks:
        - id: commitlint
          stages: [commit-msg]
```

is adding a `commitlint.config.js` file to the root of your repo. See [the
reference configuration][2] for how that could look.

NOTE: if you reference any packages in that config, eg. for `extends`,
`parserPreset` or `formatter`, you will have to add it as additional dependency
to you `.pre-commit-config.yaml`:

```yaml
    additional_dependencies: ['@commitlint/config-conventional']
```

[0]: https://pre-commit.com/#adding-pre-commit-plugins-to-your-project
[1]: https://github.com/conventional-changelog/commitlint
[2]: https://github.com/conventional-changelog/commitlint/blob/master/docs/reference-configuration.md
