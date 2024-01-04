# GitHub Template Project

This is a GitHub template repository for project and workflow templates.

### Delete Squashed Branches

After PR merge the squashed branch still exists on local git file system. To delete squashed branches:

``` bash
. .github/delete_squashed_branch.sh
```

### Agile Issue Templates

> ⚠ GitHub Issue forms are currently in beta.
> https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-issue-forms

> 🚧 The agile Issue templates are in experimental development.

The `.github/ISSUE_TEMPLATE` directory contains Issue form templates based on the Azure DevOps Boards work item types.

- 🔮 Epic Proposition
- 🧪 Feature Hypothesis
- 📖 User Story
- 👷‍♀️ Task (with BDD acceptance criteria)

GitHub issues do not support custom fields so all the form fields in the template will be appended as plain text markdown in the Issue description.

> ℹ GitHub Project items _do_ support additional custom fields however there is limited integration between Issues and Project items.

### Project Item Templates

GitHub Projects enable custom fields and visualizations for issue tracking. Project templates are held in Projects and not repositories. See Projects for templates to compliment the Issue templates contained in this repository.
