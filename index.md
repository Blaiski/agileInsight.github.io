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

#### Parsing Your Source Code File:
When you open a workspace or a project folder in vscode, AgileInsight will wait for a few seconds to allow basic extensions (e.g., native git extension) to load. It will then launch a background process to parse source code files in your workspace or project folder. By deafult, it will only parse those files in your 'src' folder. You can configure the type of files or the specific folders that you want to be prased.


[^1]: <sup>For city metaphor, see [Wettel, Richard, and Michele Lanza. 2007. “Visualizing Software Systems as Cities.” In VISSOFT 2007 - Proceedings of the 4th IEEE International Workshop on Visualizing Software for Understanding and Analysis, 92–99.](https://doi.org/10.1109/VISSOF.2007.4290706) and for software maps see [Bohnet, Johannes, and Jürgen Döllner. 2011. “Monitoring Code Quality and Development Activity by Software Maps.” Proceedings - International Conference on Software Engineering, 9–16.](https://doi.org/10.1145/1985362.1985365). Both are based on the heirarchical treemap containment approach introduced by Johnson and Shneiderman [Johnson, Brian, and Ben Shneiderman. 1991. “Tree-Maps: A Space-Filling Approach to the Visualization of Hierarchical Information Structures.” Proceedings of the 2nd Conference on Visualization 1991, VIS 1991, 284–91.](https://doi.org/10.1109/VISUAL.1991.175815)</sup>


<video width="824" height="576" controls="true" allowfullscreen="true" poster="Screen Shot 2022-04-12 at 12.37.28 AM.png">
  <source src="Agile Dashboard Integration (Contextual Actions).mp4" type="video/mp4">
</video>

---
