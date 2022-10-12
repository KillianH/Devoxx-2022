# Fleet
#jetbrains #fleet

## What's fleet ?
Fleet is an editor
Central panel with code editor + 3 side panels

### Editor mode
Code higlight but no code completion

### Smart mode
Add language server
Add code processing (powered by intellij)
Can enable multiple language server at the same time
### Remote dev
Can connect to another :
- fleet
- source code
- language server
- code processing
### Remote collaboration
Same as remote dev with others connecting to the same instance(s)
### Languages
Python / Java / JS / C# / PHP / TS / Go / Kotlin / Rust / JSON / HTML
### Architecture
Frontend -> Workspace <- Code Engine
                /\
File system (File system deamon / code engine)

## Demo
