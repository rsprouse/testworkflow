## Building the site for deployment to a public server

A GitHub Action can be used to build the site on GitHub and push the result
to a specific branch. When the Action completes you can pull the branch to
your server.

1. Log in to GitHub.
1. Visit the [Actions](actions) tab.
1. Select the `Build phonwork website and deploy to a site-* branch` workflow.
1. Click on the `Run workflow` button.
1. Choose the branch you would like to push to, either `site-dev` or `site-prod`.
1. Click 'Run workflow`.

When the workflow completes successfully you pull the branch to your server:

1. Log in to your server.
1. Navigate to the directory where the repository branch has been cloned.
1. Give the command `git pull origin --rebase --allow-unrelated-histories`.

The `git pull ...` command assumes that the repository branch has already been
cloned on your server, and that you have also configured your web server to
use the cloned repository branch. As a one-time setup step you can clone
the branches on your server with:

```bash
mkdir phonwork
cd phonwork
git clone -b site-dev https://github.com/PhonWork/phonwork site-dev  # Development site
git clone -b site-prod https://github.com/PhonWork/phonwork site-prod  # Production site
```

Then your web server must be configured to use the cloned `site-dev` and
`site-prod` directories.
