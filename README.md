## Code snippet

<code>
<script src="assets/js/ex/exercises.js">
    <script src="assets/js/ex/vocal_tract_tour.js">

    <body onload="initialize()">

        <h1>A tour of the vocal tract</h1>
        <p>Fill in the blanks on this figure.</p>
        
        <span class="image fit"><img src="images/ex/ex1_1.png" width="400px"></span>
        
        <p>Fill in the name of number: <span id="question"></span>
          <input id="answerbox" type="text" onkeydown="if (event.keyCode == 13) check_answer()" placeholder="type answer here">
          <span id="feedback"></span></p>
        <p style="font-size:small">Correct: <span id="correct">0</span> ---- Run: <span id="run">0</span></p>
</code>

## Building the site for deployment to a public server

A GitHub Action can be used to build the site on GitHub and push the result
to a specific branch. When the Action completes you can pull the branch to
your server.

1. Log in to GitHub.
2. Find the [`Build phonwork website and deploy to a site-* branch` workflow](https://github.com/PhonWork/phonwork/actions/workflows/publish.yaml) under the Actions tab.
5. Click on the `Run workflow` button.
6. Choose the branch you would like to push to, either `site-dev` (development version) or `site-prod` (production).
7. Click 'Run workflow`.

When the workflow completes successfully pull the branch to your server:

1. Log in to your server.
1. Navigate to the directory where the repository branch has been cloned (`site-dev` or `site-prod`).
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

Then configure your web server to use the cloned `site-dev` and
`site-prod` directories. **It is also recommended to disallow access to the `.git` subdirectories in your server configuration.**
