### setting up github commit signature verification:
- First check that your email id is verified:
  - go to github->user settings->emails->see if it mentions 'unverified' below your email id
  - ref [here](https://docs.github.com/en/github/getting-started-with-github/signing-up-for-github/verifying-your-email-address)
- Check if you have a GPG key (private-public key pair) already generated for this email id on your machine
  - `gpg --list-secret-keys --keyid-format LONG`
- if you don't have a key generate it
  - while generating the key, it'll ask for inputs, most of it is ok to keep default and email is your github (preferrably private, or public) email id.
  - `gpg --full-generate-key`
  - ref [here](https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification/generating-a-new-gpg-key)
- Now check the key that got generated
  - `gpg --list-secret-keys --keyid-format LONG`
  - output have a line similar to `sec   rsa4096/<your key> 2021-06-02 [SC]`
- Now, set GPG key in your local git client
  - `git config --global user.signingkey <your key>`
- Now we need to add same key to your github account
  - get public key block
    - `gpg --armor --export <your key>`
    - copy the entire text that got printed on your screen, starting from first '-' to last '-'
  - now go to github->profile->settings->SSH and GPG keys->New GPG key. Paste public key block that you copied in step above.
- after this whenever you want to sign a commit add `-S` flag
  - `git commit -S -m your commit message` 


Above steps were derived from links given [here](https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification)

### how to link issues and PRs
- Link one issue with other :
  - This can be done by creating a task within the issue and then converting that task into issue. Or mentioning issue in the task description. [Reference](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-from-a-task-list-item)
- Link PR with an issue :
  - open PR and in description you can mention issue that it addresses using any of the keyword like `closes`. Or you can mention issue in the `linked issues` section.

### creating issue templates for all repos of a user:
- create a new repo called `.github` under your user account
- go to setting of `.github` repo and scroll down under `option` section
- under `issues`, click on `enable templates`

## To be read:

- number of ways in Github to create an issue (https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-from-a-url-query)

