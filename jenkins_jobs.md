# Linking Jenkins Job to GitHub Repo

1. Create job
2. Select GitHub project box and enter repo HTTPS link.
3. Restrict where project is run so that the node doesn't get overloaded.
4. In source code management, select Git and paste SSH link from GitHub.
5. Add private SSH key and ensure file name matches.
6. Change branch to main.
7. In build environment, select "Provide Node & npm bin/ folder to PATH" and choose Sparta-Node-JS.
8. Add build step, execute shell.
9. Enter `cd app`, `npm install`, `npm test`.
10. Save and build.

## Adding webhook to Jenkins

1. On Jenkins, select "configure" on the job you wish to add a webhook.
2. Go to build triggers and select "GitHub hook trigger for GITScm polling".
3. Save changes.
4. On GitHub repo, go to settings and navigate to webhooks.
5. Add webhook.
6. Enter `http://<Jenkins-IP>:8080/github-webhook/` into payload URL.
7. Content type: application/json.
8. Select push and pull to trigger webhook.
9. Ensure active box is selected at the bottom.
10. Create webhook.
11. Commit changes to repo to test whether it has worked.

## Merge branches with Jenkins

1. Same steps as creating a job.
2. Enter dev branch.
3. Add additional behaviors "merge before build".
4. Enter origin in repository and main in branch to merge to.
5. Add post build actions, Git publisher.
6. Select push only if build succeeds and merge results.
7. Add branches.
8. Enter branch to push main.
9. Enter target remote name main.
10. Build other projects, next project in the pipeline.

## Delivering changes to AWS

1. Create job.
2. Add build, execute shell.
