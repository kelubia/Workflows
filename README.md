name: Update Clock Badge
on:
  schedule:
    - cron: '*/5 * * * *' # Runs every 5 minutes
  workflow_dispatch:
jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - name: Update README
        uses: actions/github-script@v6
        with:
          script: |
            const fs = require('fs');
            const readmePath = './README.md';
            let readmeContent = fs.readFileSync(readmePath, 'utf8');
            const newTime = new Date().toLocaleTimeString();
            readmeContent = readmeContent.replace(/TIME: .*/, `TIME: ${newTime}`);
            fs.writeFileSync(readmePath, readmeContent);











![Digital Clock](https://img.shields.io/badge/dynamic/json?color=00ff00&label=TIME&query=datetime&url=http://worldtimeapi.org/api/ip&style=for-the-badge&logo=clockify&logoColor=white&labelColor=000000)




            
