### Hi there! My name is Lara Justino, I'm a portuguese front-end developer!
<div align="center">
  <a href="https://github.com/rafaballerini">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=LaraJustino&show_icons=true&theme=material-palenight&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=LaraJustino&layout=compact&langs_count=7&theme=material-palenight"/>
</div>
name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: rafaballerini
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
