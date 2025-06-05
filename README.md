commands: 
    git init
    git add .
    git commit -m 'first commit'
    git remote add origin git@github.com:Ysa-04/examen-cloudsystemen-githubactions.git
    git branch -M main
    git push -u origin main 


name: Create diagram
on:
  workflow_dispatch: {}
  push:
    branches:
      - main
jobs:
  get_data:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@master
      - name: Update diagram
        uses: githubocto/repo-visualizer@main
        with:
          excluded_paths: "ignore,.github"