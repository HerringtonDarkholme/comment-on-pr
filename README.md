# Comment on PR via GitHub Action

A GitHub action to comment on the relevant open PR when a commit is pushed.

## Usage

- Requires the `GITHUB_TOKEN` secret.
- Requires the comment's message in the `msg` parameter.
- Supports `push` and `pull_request` event types.

### Sample workflow

```
name: comment-on-pr example
on: pull_request
jobs:
  example:
    name: sample comment
    runs-on: ubuntu-latest
    steps:
      - name: comment PR
      uses: Schniz/comment-on-pr@master
      with:
          token: ${{ secrets.GITHUB_TOKEN }}
          file_path: ./.github/comment.md
          unique_id: my-unique-id
```
