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
<video width="1188" height="912" controls="true" allowfullscreen="true" poster="video captures/Parsing a Workspace.png">
  <source src="video captures/Parsing a Workspace.mp4" type="video/mp4">
</video>

[^parsing]: <sup>Note that due to current limitations with LSP implementation of different languages, AgileInsight will sometimes have to force open few files in order to trigger their language server to fulfil the request. LSP technology is still in its early phase, and future improvements are expected in the near future. Also, the parsing operation is influenced by the behaviour of the individual language server, and thus timing can vary between different runs. Here is a nother parsing example of the same workspace: [Another Parsing Run](https://user-images.githubusercontent.com/31612240/178114350-01c29cfe-10b6-40ab-9acc-d6dd4b24e17d.mp4)</sup> 

### 2. Discovering the landscape of your system 
After AgileInsight has parsed your source code, you can explore the structure of your system using its 3D visualisation feature. Below are screenshots of iTrust (the same system parsed above), along with a couple of well-known open-source systems.
#### iTrust
![iTrust](/screenshots/iTrust.png)
#### Asp.Net Boilerplate
![iTrust](/screenshots/ASP.NETBoilerplate.png)
#### Django
![iTrust](/screenshots/Django.png)

### 3. Authorising Access to your Jira or Trello Dashboard
AgileInsight uses oauth to ask permission to access data on your agile dashboards, in much the same way that you would allow vscode and other IDEs to access your source control repository.

<video width="1150" height="775" controls="true" allowfullscreen="true" poster="video captures/Auth Demo.png">
  <source src="video captures/Auth Demo.mp4" type="video/mp4">
</video>

<sup>▶︎ _Note that AgileInsight does not store or cache your data. Any fetch or update operation is done live and hence requires an internet connection_</sup>

<sup>▶︎ _Authorisation is only needed once, and will be retained across different workspaces of your vscode._</sup>

### 4. Your AgileInsight Dashboard Explorer
AgileInsight integrates your authorised agile developmemt dashboards into vscode, allowing you to access and work with your issues, cards, etc. from vscode. Once source code has been tagged (see below), the code items become effectively synchronised to their related issues, making answers to questions such as "what is this method doing?" or "where is this issue implemented?" to be readily accessible. The visualisation could help with  assessing the impact when a certain feature needs to be changed.
<video width="1162" height="1012" controls="true" allowfullscreen="true" poster="video captures/Dashboard Explorer.png">
  <source src="video captures/Dashboard Explorer.mp4" type="video/mp4">
</video>


### 5. Tagging Your source code
AgileInsight offers three ways for developers to tag their source code during development. The tagging involves an automated three-legged operation where code items are linked to design items (e.g., an issue or user story) in source code, in versioning repository, and on the agile dashboard where design items are kept. Currently a developer needs to provide either the code item or the design item in concern, however a future release will reduce that to user only confirming the items that are to be tagged (see on-commit method).

#### On-Commit:
After a developer has contributed some changes to their source code and is about to commit the changes, AgileInsight detects any changed code items (e.g., methods, classes) that are eligible for tagging, and prompts the user to do so if they wish. In future, this will be further automated, offering checkboxes where the user only needs one click to confirm the tagging.[^checkboxes]

[^checkboxes]: <sup>Vscode's native viewlets API does not required felxibility</sup> 


<video width="1154" height="874" controls="true" allowfullscreen="true" poster="video captures/On-CommitTagging.png">
  <source src="video captures/On-CommitTagging.mp4" type="video/mp4">
</video>

<sup>▶︎ _Those unnecessary notifications are only kept for now for development-time purposes._</sup>

#### CI Initiated:
A developer can initiate the tagging process for eligible inidividual code items (classes, methods, functions, structs, and so on) right from their source code editor in Vscode. This can be done through a hover action or via a shortcut command.

<sup>▶︎ _CI stands for Code Item._</sup> 
<video width="1260" height="787" controls="true" allowfullscreen="true" poster="video captures/CI_InitiatedTagging.png">
  <source src="video captures/CI_InitiatedTagging.mp4" type="video/mp4">
</video>

#### DI Initiated:
A developer may also initiate the tagging from a particular design item (DI) that, for instance, they have just implemented or added changes to. Multiple code items can be selected at one time.
<video width="1260" height="787" controls="true" allowfullscreen="true" poster="video captures/DI_InitiatedTagging.png">
  <source src="video captures/DI_InitiatedTagging.mp4" type="video/mp4">
</video>

### 6. Interacting with your design items on the Spot and in source code (Contextual actions and artefact traceability)
A key feature of AgileInsight is to synchronise design items with their code item implementations. It then offers the developer a number of benefits such as readily knowing what design items a method or class is impacting, performing quick actions on issue and user story cards from within source code, and inspecting the design items from the side explorer side by side with source code. The video demo below showcases a number of such benefits.

For example, the clipt below demonstrates how the developer can readily find all the source code items that implement a design item (saving them those long hours wasted on searching, flipping and reading through numerous source files). It shows how a developer or quality engineer can snowball as much as needed, jumping from a design item down to its implementation in source code, from a method down to all the design items that are impacted by it, and so on.

It then shows how the user can make use of the visualisation to visually examine the impact of a user story or an issue on the system. They can reveal the locality and distribution of the design item in question, offering potential insights on the distribution of feature implementation and hence its quality.
<video width="1225" height="753" controls="true" allowfullscreen="true" poster="video captures/Interacting with Design Items.png">
  <source src="video captures/Interacting with Design Items.mp4" type="video/mp4">
</video>

### 7. Visual Artefact Traceability 
AgileInsight enables visual artefact traceability right in your vscode. You can jump from an issue right to its individual code items that implements it, and vice versa. The novel visualisation mapping allows you to visually see the location of your issues (or features) across the structure of your system.  
<video width="1213" height="877" controls="true" allowfullscreen="true" poster="video captures/Artefact Traceability with Visualisation.png">
  <source src="video captures/Artefact Traceability with Visualisation.mp4" type="video/mp4">
</video>

#### Interpreting the visualisation
![Visualisation Keys](https://user-images.githubusercontent.com/31612240/178110883-e8c6295a-451f-4c2e-9f57-3fd93b2322e8.png)
Above is an explanation of visualised code items, detailing the color mappings used; White for classes, brown for files, blueish-green for methods & functions, red for structs, pink for namespaces, and beige for folders. The grey platform is the workspace folder. The above visualisation was generated using 10 files of different languages, obtained from real-word open-source systems and placed in a single project folder for demonstration purposes. 


### 8. Find how the implementation of your issue or user story is distributed across your system
>TODO: include a video with shour description. Include pics too.

<br>

***


## Showcase of landscape visualisation of various open-source systems
AgileInsight offers a novel language-agnostic visualisation of source code. Below are screenshots of a number of open-source systems that were downloaded directly from their public GitHub repositories and visualised using AgileInsight. The diverse scenery seen in the views below, demonstrates the ability of AgileInsight in exposing the structure of a system. The dimensions of the buildings reflects the size and complexity of the corresponding source files and the structural elements they contain. For more information, please see.[^thesis]

<sup>▶︎ _Note that the scenes show extensive number of components due to the fact that the entire master (or main) branch was used to generate the visualisation. The date refers to when the repository was pulled._</sup>

### 1. KERAS (Python)
Python’s deep learning API consisting of 661 python files.
<img width="1538" alt="Screen Shot 2022-04-12 at 12 36 27 AM" src="https://user-images.githubusercontent.com/31612240/178524432-c48b612f-9dfa-47ab-b361-4a711071738c.png">
<img width="1538" alt="Screen Shot 2022-04-12 at 12 37 28 AM" src="https://user-images.githubusercontent.com/31612240/178524511-7deb8ea5-ab7c-4f7e-befc-254666c51e36.png">

<sup>▶︎ _Open image in new tab to see full resolution._</sup>
<sup>▶︎ _Repository: [https://github.com/keras-team/keras](). Date: 10th April, 2022_</sup>

### React (JavaScript)
A visualisation of Facebook’s React API, consisting of a total of 1874 files, spanning JavaScript, CSS, HTML, Typescript, and C++ source code. 
![Screen Shot 2022-04-27 at 7 02 34 PM](https://user-images.githubusercontent.com/31612240/178526387-9bd3b41e-424c-442c-b6ca-1eae95d6b6d6.png)
![Screen Shot 2022-04-27 at 6 58 16 PM](https://user-images.githubusercontent.com/31612240/178526526-3de2f40e-d0a2-4d5b-8701-33283e56cff3.png)
<sup>▶︎ _Repository: [https://github.com/facebook/react]. Date: 10th April, 2022_</sup>

### AngularJs (JavaScript)
Consisting of 849 JavaScript source code files.
![Screen Shot 2022-04-27 at 5 17 24 PM](https://user-images.githubusercontent.com/31612240/178551311-c3ab3d54-3f65-4f92-b1af-7b8cabeae8dc.png)
![Screen Shot 2022-04-27 at 5 22 24 PM](https://user-images.githubusercontent.com/31612240/178551360-72c615fe-ffd0-4002-b28b-9c740bd27ed0.png)
<sup>▶︎ _Repository: [https://github.com/angular/angular.js]. Date: 10th April, 2022._</sup>

### Facebook iOS SDK (Swift)
Facebook’s API for iOS represented by consisting of a total of 779 files, spanning Swift, Objective-C, and JavaScript source code.
![Screen Shot 2022-04-11 at 7 46 39 PM](https://user-images.githubusercontent.com/31612240/178552438-c797bee2-4e7a-49bd-9fc6-070e5e0bafad.png)
![Screen Shot 2022-04-11 at 7 51 51 PM](https://user-images.githubusercontent.com/31612240/178552499-d17b330c-2681-4871-8c3c-b1ecec75d687.png)
<sup>▶︎ _Repository: [https://github.com/facebook/facebook-ios-sdk]. Date: 10th April, 2022._</sup>

### Amazon Web Services SDK for Go Language (excluding 'Service' Module)
Displaying a total of 409 Go source files.
<img width="1552" alt="Screen Shot 2022-04-11 at 5 41 02 PM" src="https://user-images.githubusercontent.com/31612240/178552877-a4c469ef-bc67-4925-952a-097c4715ccbc.png">
<img width="1552" alt="Screen Shot 2022-04-11 at 5 41 34 PM" src="https://user-images.githubusercontent.com/31612240/178552902-d4aed912-902b-4b5b-82fe-277e6bf8d3e6.png">
<sup>▶︎ _Repository: https://github.com/aws/aws-sdk-go. Date: 11th April, 2022</sup>

### Django (Python)
<img width="1538" alt="Screen Shot 2022-04-12 at 12 54 34 AM" src="https://user-images.githubusercontent.com/31612240/178551764-7001dc33-785b-466d-aef2-3b9cd59ebfb1.png">
<img width="1538" alt="Screen Shot 2022-04-12 at 12 53 33 AM" src="https://user-images.githubusercontent.com/31612240/178551846-12ed6ac8-e8b2-4966-a22b-f16fc440669c.png">
<sup>▶︎ _Repository: https://github.com/django/django. Date: 10th April, 2022</sup>

### VSCODE (JavaScript)
A visualisation of Vscode’s main Github branch, consisting of a total of 3280 files, spanning Typescript, JavaScript, HTML, and CSS source code. 
![Screen Shot 2022-04-27 at 9 53 16 PM](https://user-images.githubusercontent.com/31612240/178550039-61cfc5ad-39b0-4f53-b838-36589f193b22.png)
![Screen Shot 2022-04-27 at 9 59 36 PM](https://user-images.githubusercontent.com/31612240/178550149-68b8ba13-fe5e-4072-a2bf-b9a374bf98b2.png)
![Screen Shot 2022-04-28 at 12 39 32 AM](https://user-images.githubusercontent.com/31612240/178550223-afea3b41-f776-4044-b157-580a2cc4b541.png)
<sup>▶︎ _Repository: [https://github.com/microsoft/vscode]. Date: 27th April, 2022._</sup>

### Isitio (Go)
A visualisation of the microservices platform, ISTIO, consisting of 1391 files of Go language source code. 
<img width="1552" alt="Screen Shot 2022-04-11 at 6 34 16 PM" src="https://user-images.githubusercontent.com/31612240/178553524-b3a1dd9d-a30d-4b43-8a1a-e11628ff7591.png">
<sup>▶︎ _Repository: [https://github.com/istio/istio]. Date: 11th April, 2022._</sup>

### Micro (Go)
Consisting of 586 Go source code files.
![Screen Shot 2022-04-11 at 7 03 39 PM](https://user-images.githubusercontent.com/31612240/178553816-b658df81-c8a2-4ed6-a0ed-737e0f361aa7.png)
![Screen Shot 2022-04-11 at 7 04 19 PM](https://user-images.githubusercontent.com/31612240/178553785-4c473a39-25af-4d44-b849-3fdfc406d966.png)
<sup>▶︎ _Repository: [https://github.com/micro/micro]. Date: 11th April, 2022_</sup>

### APS.NET Boilerplate (Csharp)
ASP.NET Boilerplate API consisting of a total of 1401 files, spread across Csharp, JavaScript, Typescript, and CSS source code.
<img width="1538" alt="Screen Shot 2022-04-11 at 11 25 32 PM" src="https://user-images.githubusercontent.com/31612240/178554541-6828b337-0773-40c9-bcd6-6c9d7e15709c.png">
<img width="1538" alt="Screen Shot 2022-04-11 at 11 31 32 PM" src="https://user-images.githubusercontent.com/31612240/178554477-dea759d8-577f-4810-b9e1-e7758a6efd97.png">
<sup>▶︎ _Repository: [https://github.com/aspnetboilerplate/aspnetboilerplate]. Date: 10th April, 2022_</sup>

### CodeHub (Csharp)
CodeHub application for iOS devices consisting of a total of 377 files ranging between Csharp, JavaScript, and CSS source code. 
<img width="1538" alt="Screen Shot 2022-04-12 at 12 13 37 AM" src="https://user-images.githubusercontent.com/31612240/178555029-d26d009f-679a-4138-b544-e17774c1ddfc.png">
![Screen Shot 2022-04-11 at 2 53 47 AM](https://user-images.githubusercontent.com/31612240/178555088-2447db39-bdfe-40d1-9919-1aad2e925ffe.png)
<sup>▶︎ _Repository: [https://github.com/CodeHubApp/CodeHub]. Date: 10th April, 2022</sup>

### ReactiveX (Swift)
ReactiveX API for Swift consisting of 996 files of Swift and Objective-C source code.
<img width="1538" alt="Screen Shot 2022-04-11 at 10 54 26 PM" src="https://user-images.githubusercontent.com/31612240/178555437-e2dda3f7-55c9-4aee-a0ca-455d8f0ff195.png">
<img width="1538" alt="Screen Shot 2022-04-11 at 10 54 46 PM" src="https://user-images.githubusercontent.com/31612240/178556117-e05495ad-c2cc-4ac3-89d2-ac0929e41a44.png">
<sup>▶︎ _Repository: [https://github.com/ReactiveX/RxSwift]. Date: 10th April, 2022_</sup>

### Dataset Loader
>Should I include this?

[^1]: <sup>For city metaphor, see [Wettel, Richard, and Michele Lanza. 2007. “Visualizing Software Systems as Cities.” In VISSOFT 2007 - Proceedings of the 4th IEEE International Workshop on Visualizing Software for Understanding and Analysis, 92–99.](https://doi.org/10.1109/VISSOF.2007.4290706) and for software maps see [Bohnet, Johannes, and Jürgen Döllner. 2011. “Monitoring Code Quality and Development Activity by Software Maps.” Proceedings - International Conference on Software Engineering, 9–16.](https://doi.org/10.1145/1985362.1985365). Both are based on the heirarchical treemap containment approach introduced by Johnson and Shneiderman [Johnson, Brian, and Ben Shneiderman. 1991. “Tree-Maps: A Space-Filling Approach to the Visualization of Hierarchical Information Structures.” Proceedings of the 2nd Conference on Visualization 1991, VIS 1991, 284–91.](https://doi.org/10.1109/VISUAL.1991.175815)</sup>

---
