# Introduction:
This is an application that depends on a vulnerable Npm package (<i>jquery@3.4.0</i>), and also on another local Npm package that is not itself vulnerable, but has dependencies on other vulnerable Npm package (<i>minimist@0.0.8</i>).
Therefore, if you scan this application, you can expect an output showing two vulnerabilities: one from the direct dependency and one from its transitive dependencies.

## Actions:
1. Get pkgs: ```npm install```
2. Scan by native tool: ```npm audit```
3. Scan by mend: ```mend dep -d .```
4. Dockerize: ```docker build -t app:node .```
5. Scan the image: ```mend image app:node```
