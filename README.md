# Pull Requests Labeling Action

Automatically adds a label to pull requests.

## Inputs

- `gh-token` (required): GitHub token with permission to write PR labels.
- `label` (required): Label name to add to the pull request.

## Example workflow

```yaml
name: Label PRs

on:
	pull_request:
		types: [opened, reopened, synchronize]

jobs:
	label:
		runs-on: ubuntu-latest
		steps:
			- name: Apply label to PR
				uses: OmarChouchane/Typescript-Github-Action@main
				with:
					gh-token: ${{ secrets.GITHUB_TOKEN }}
					label: "needs-review"
```

## Local development

```bash
npm install
npm run build
npm test
```

The action entrypoint is `dist/index.js` as defined in `action.yaml`.
