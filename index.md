# Welcome to AgileInsight Profile Page

AgileInsight is a vscode extension created as part of my doctoral research[^thesis]. As user, it offers you the following:

[^thesis]: <sup>Add Link to thesis once published.</sup>

## Artefact Traceability Benefits:
- Integrates your agile dashboard such as Jira or Trello into your vscode development envrionment
- Allows you to inspect, read, comment on, and do other the common actions on your cards right within vscode
- Allows you to tag your source code items (e.g., methods, or files) to the specific issues or user stories that you are working on
- Once tagged, your source code items become tightly linked to the design items (i.e., issues, bugs, etc) that relates to them
- You will be able to see the tags in the source code, in your GitHub, and in your issue tickets or cards
- You can then hover on an issue in the source code to see all the code items related to it, and vice versa

## Software Visualisation Benefits:
- AgileInsight can visualise your source code using a state of the art 3D visualisation technique called city metahpor (or software maps)[^1]
- The visualisation cleverly brings out your source code structure in a landscape-like view, allowing you to visually see the building blocks that make up your system (from folders or packages, down to files and individual methods inside).
- It is language-agnostic, so no matter what programming or scripting language your source code is, as long as your vscode editor can read it then AgileInsight should be able visualise it
- Once visualised, you will be able to interact with the building blocks of your system right in vscode, and get to explore and navigate through it in a new way.
- And of course, if your source code is all tagged and linked, then you can point to an issue or card in the explorer, and get to see where exactly it is implemented, and how it is distributed across the landscape of your source code.

<br>

```
Below is a lightweight showcase of AgileInsight's key features with screenshots
and videos demonstrating various funcitonalities in aciton.
```

### 1. Parsing Your Source Code Files:
When you open a workspace or a project folder in vscode, AgileInsight will wait for a few seconds to allow basic extensions (e.g., native git extension) to load. It will then launch a background process to parse source code files in your workspace or project folder, and display progress in the status bar. By deafult, it will only parse those files in your 'src' folder. You can configure the type of files or the specific folders that you want to be prased.[^parsing]
<video width="1273" height="977" controls="true" allowfullscreen="true" poster="video captures/Parsing a Workspace.png">
  <source src="video captures/Parsing a Workspace.mp4" type="video/mp4">
</video>

[^parsing]: <sup>Note that due to current limitations with LSP implementation of different languages, AgileInsight will sometimes have to force open few files in order to trigger their language server to fulfil the request. LSP technology is still in its early phase, and future improvements are expected in the near future. Also, the parsing operation is influenced by the behaviour of the individual language server, and thus timing can vary between different runs. Here is a nother parsing example of the same workspace: [Another Parsing Run](https://user-images.githubusercontent.com/31612240/178114350-01c29cfe-10b6-40ab-9acc-d6dd4b24e17d.mp4)</sup> 



### 2. Authorising Access to your Jira or Trello Dashboard
AgileInsight uses oauth to ask permission to access data on your agile dashboards, in much the same way that you would allow vscode and other IDEs to access your versioning repositories.

<video width="1150" height="775" controls="true" allowfullscreen="true" poster="video captures/Auth Demo.png">
  <source src="video captures/Auth Demo.mp4" type="video/mp4">
</video>
<sup>▶︎ *Note that AgileInsight does not store or cache your data. Any fetch or update operation is done live and hence requires an internet connection</sup>

<sup>▶︎ _Authorisation is only needed once, and will be retained across different workspaces of your vscode._</sup>

### 3. Your Agile Dashboard Explorer
>TODO: include a video with shour description. should show the contextual actions

### 4. Tagging Your source code
>TODO: include a video with shour description. show the main methods: 
#### On-Commit:
#### CI Initiated:
#### DI Initiated:

### 5. Discovering the landscape of your system 
Visualising and Exploring your Source Code (>show some open source vis)

#### Interpreting the visualisation
![Visualisation Keys](https://user-images.githubusercontent.com/31612240/178110883-e8c6295a-451f-4c2e-9f57-3fd93b2322e8.png)
Above is an explanation of visualised code items, detailing the color mappings used; White for classes, brown for files, blueish-green for methods & functions, red for structs, pink for namespaces, and beige for folders. The grey platform is the workspace folder. The above visualisation was generated using 10 files of different languages, obtained from real-word open-source systems and placed in a single project folder for demonstration purposes. 


>TODO: include a video with shour description. Include pics too.

### 6. Interacting with your design items in source code (Contextual actions and artefact traceability)
>TODO: include mostly pics I think.

### 7. Interacting with your visualised system
>TODO: include a video with shour description.

### 8. Find how the implementation of your issue or user story is distributed across your system
>TODO: include a video with shour description. Include pics too.

<br>

***


## Showcase of landscape visualisation of various open-source systems
*Note that the visualisation shows extensive components because the entire master (or main) branch is used. The date refers to the date that the repository was pulled*
### KERAS
### VSCODE
### APS.NET Boilerplate
### AngularJs

### Dataset Loader
>Should I include this?

[^1]: <sup>For city metaphor, see [Wettel, Richard, and Michele Lanza. 2007. “Visualizing Software Systems as Cities.” In VISSOFT 2007 - Proceedings of the 4th IEEE International Workshop on Visualizing Software for Understanding and Analysis, 92–99.](https://doi.org/10.1109/VISSOF.2007.4290706) and for software maps see [Bohnet, Johannes, and Jürgen Döllner. 2011. “Monitoring Code Quality and Development Activity by Software Maps.” Proceedings - International Conference on Software Engineering, 9–16.](https://doi.org/10.1145/1985362.1985365). Both are based on the heirarchical treemap containment approach introduced by Johnson and Shneiderman [Johnson, Brian, and Ben Shneiderman. 1991. “Tree-Maps: A Space-Filling Approach to the Visualization of Hierarchical Information Structures.” Proceedings of the 2nd Conference on Visualization 1991, VIS 1991, 284–91.](https://doi.org/10.1109/VISUAL.1991.175815)</sup>


<video width="824" height="576" controls="true" allowfullscreen="true" poster="Screen Shot 2022-04-12 at 12.37.28 AM.png">
  <source src="Agile Dashboard Integration (Contextual Actions).mp4" type="video/mp4">
</video>

---
