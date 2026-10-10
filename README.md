# Personal aide blueprints

My personal preferences for projects that use [aide](https://github.com/jmylchreest/aide).

The `jmylchreest-writing` blueprint covers READMEs, documentation, commit messages, pull request descriptions, release notes, code comments and explanations. It favours natural language, complete sentences and succinct meaning. It avoids em dashes, filler and inflated claims.

## Import into a project

Run this from the project directory:

```sh
aide blueprint import --registry=https://raw.githubusercontent.com/jmylchreest/aide-blueprints/main jmylchreest-writing
```

Add `--dry-run` to preview the decisions. This blueprint complements the standard blueprints shipped with aide and uses distinct decision topics.

## Configure the registry

Merge this entry into `~/.aide/config/aide.json` for personal use, or `.aide/config/aide.json` for a project:

```json
{
  "blueprints": {
    "registries": [
      "https://raw.githubusercontent.com/jmylchreest/aide-blueprints/main"
    ]
  }
}
```

The upstream documentation describes this setting, but upstream `main` at `cec6efcf3c9137ec549803b7c342714fc3ccdb92` does not read it in the blueprint CLI. Use the explicit `--registry` command above until your aide version supports configured registries. The CLI also does not currently list remote blueprints.

Registering a source does not automatically import its decisions. Import the blueprint into each project where you want these preferences applied.

## Update preferences

Edit `jmylchreest-writing.json`, increase its semantic version and commit the change. Run the import command again in each project to apply updates. Aide preserves decisions set by the user or another blueprint unless you explicitly pass `--force`.

Blueprints use aide's [blueprint schema](https://github.com/jmylchreest/aide/blob/main/docs/docs/features/blueprints.md). Keep new personal blueprint names and decision topics distinct from those shipped upstream.
