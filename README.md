## Hi there 👋

<div align="center">
  <img src="https://capsule-render.vercel.app/render?type=waving&color=00b4d8&height=250&section=header&text=Hi%20I'm%20Ansh%20🚀&fontSize=70&animation=fadeIn" width="100%" />
</div><!--
**anshere0/anshere0** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
## 🛠 My Tech Stack
<p align="left">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=html,css,cpp,py,java,flask,vscode,github,git" />
  </a>
</p>

### 🐍 Python Libraries & Focus
`NumPy` • `Pandas` • `Matplotlib` • `Pine Script` • `DSA (Striver A2Z)`
Here are some ideas to get you started:

- 🔭 I’m currently working on productivity app
- 🌱 I’m currently learning database, backend 
- 📫 How to reach me: 

-->
## 📊 GitHub Analytics


name: Generate Snake

on:
  schedule:
    - cron: "0 */24 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Generate Snake
        uses: Platane/snk@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
      - name: Push to GitHub
        uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
