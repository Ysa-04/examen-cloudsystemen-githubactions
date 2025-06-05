commands: 
    git init 
    git add . 
    git commit -m 'first commit' 
    git remote add origin git@github.com:Ysa-04/examen-cloudsystemen-githubactions.git 
    git branch -M main 
    git push -u origin main

main.yml:
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
    
-> hij geeft error bij ophalen van data. Ik krijg een error die zegt dat de permission tot mijn github repo denied is, maar die staat public. 

https://github.com/Ysa-04/examen-cloudsystemen-githubactions