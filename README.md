<img src="https://capsule-render.vercel.app/api?type=waving&color=0:833ab4,50:fd1d1d,100:fcb045&height=100&section=header&text=&fontSize=0" width="100%"/>

### 안녕하세요~ 👋

![header](https://capsule-render.vercel.app/api?type=rect&color=timeGradient&height=150&section=header&text=손%20석현의%20깃허브&desc=&fontSize=90)

![js](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)
![js](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)


<img src="https://capsule-render.vercel.app/api?type=waving&color=0:833ab4,50:fd1d1d,100:fcb045&height=100&section=footer&text=&fontSize=0" width="100%"/>


name: generate animation
on:
  schedule:
    - cron: "0 */24 * * *" 
  workflow_dispatch:
  push:
    branches:
    - master
    
jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: 여기다가 github ID 적기 !!!
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark

      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: 여기다가는 토큰 적기


<!--
**lobster0202/lobster0202** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
