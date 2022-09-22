# Rear Wing for UTD FSAE Fall 2022

Slow is smooth and smooth is fast is a great idiom, but might sound backwards when designing a race car. Using the CFD capabilities of the cloud platform SimScale and intelligent airfoil design, I develop a high performance rear wing for a  Formula SAE car.


# Airfoil Design

The general goal of passive aerodynamic elements is to optimize their shape to serve their required function. This might mean a more tapered profile or varying the curvature of the under side. Every airfoil there could ever be has already been designed, dimensions parametrized, and categorized according to a 4 digit number.   If airfoils are wings and wings create lift, why would we want an airfoil. All you have to do to get downforce from an airfoil is flip it over!

For this application we want an airfoil with a low Reynolds number(low is smooth flow, high is turbulent flow) to minimize drag and avoid any unwanted torques on the car from turbulence. For this application and based on previous research we will use the BE-50 airfoil, which has a low Reynold's number of 50,000.
![BE-50 Airfoil Profile](https://i.imgur.com/TnH77gI.png)

## Mock up in Fusion 360

A single element wing is effective, but to allow for a possible active rear wing in the future, we will create a two wing system. After downloading the .dat file from an [airfoil repository](http://airfoiltools.com/airfoil/details?airfoil=be50-il), we use a [script](https://apps.autodesk.com/FUSION/en/Detail/Index?id=3044478757760121899&os=Win64&appLang=en) for Fusion 360 which imports the profile of the BE-50 airfoil into a sketch.
![enter image description here](https://i.imgur.com/1EjofD0.png)
We repeat twice to place both wings on the same sketch plane. The pitch of the upper wing is a good approximation of where an active wing might be at a high speed. Then we extrude the sketch to a width of 1000 mm, the maximum width of the rear wing.
![enter image description here](https://i.imgur.com/afpNnb7.png)

## Evaluating using CFD

To calculate the performance of our wing system we will use a cloud simulation platform called SimScale. To setup our simulation first we need to export our design from Fusion360 in an Inventor file format.
![enter image description here](https://i.imgur.com/qzNSRwP.png)
Then we will start up a new project in SimScale and import our geometry.

![enter image description here](https://i.imgur.com/2A8SzL3.png)
![enter image description here](https://i.imgur.com/IjaiQxj.png)
For instructions on how to set up the CFD simulation, refer to the SimScale [tutorial](https://www.simscale.com/docs/tutorials/aerodynamic-simulation-vehicle/) for a full car. The settings and set up they use is similar to what our wing requires.

**Basic Steps for the CFD:
**	
 - Define flow volume
 - Determine boundary conditions
 - Results Control(calculating lift and drag)
 - Mesh/Mesh Refinements
 - Full Run
 - Analyze Results
 
Here is an animation from after the simulation, using a particle trace to determine if there was turbulent flow separation behind the upper wing.
![enter image description here](https://i.imgur.com/PMrcHBN.gif)
The particle trace doesn't tell us much. Lets look at the drag and lift results.
![ ](https://i.imgur.com/MNLUaHO.png)
After the simulation stabilizes, there is a periodic ripple in the drag and lift values. Definitely something not right going on.
Lets change the angle of attack of the upper wing to be more streamlined.
![enter image description here](https://s5.gifyu.com/images/result.gif)
Much more streamlined flow and lets take a look at the actual performance data.
![enter image description here](https://i.imgur.com/36S1EtV.png)
As we can see there is no periodic ripple from turbulence. 
## Rename a file

You can rename the current file by clicking the file name in the navigation bar or by clicking the **Rename** button in the file explorer.

## Delete a file

You can delete the current file by clicking the **Remove** button in the file explorer. The file will be moved into the **Trash** folder and automatically deleted after 7 days of inactivity.

## Export a file

You can export the current file by clicking **Export to disk** in the menu. You can choose to export the file as plain Markdown, as HTML using a Handlebars template or as a PDF.


# Synchronization

Synchronization is one of the biggest features of StackEdit. It enables you to synchronize any file in your workspace with other files stored in your **Google Drive**, your **Dropbox** and your **GitHub** accounts. This allows you to keep writing on other devices, collaborate with people you share the file with, integrate easily into your workflow... The synchronization mechanism takes place every minute in the background, downloading, merging, and uploading file modifications.

There are two types of synchronization and they can complement each other:

- The workspace synchronization will sync all your files, folders and settings automatically. This will allow you to fetch your workspace on any other device.
	> To start syncing your workspace, just sign in with Google in the menu.

- The file synchronization will keep one file of the workspace synced with one or multiple files in **Google Drive**, **Dropbox** or **GitHub**.
	> Before starting to sync files, you must link an account in the **Synchronize** sub-menu.

## Open a file

You can open a file from **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronize** sub-menu and clicking **Open from**. Once opened in the workspace, any modification in the file will be automatically synced.

## Save a file

You can save any file of the workspace to **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronize** sub-menu and clicking **Save on**. Even if a file in the workspace is already synced, you can save it to another location. StackEdit can sync one file with multiple locations and accounts.

## Synchronize a file

Once your file is linked to a synchronized location, StackEdit will periodically synchronize it by downloading/uploading any modification. A merge will be performed if necessary and conflicts will be resolved.

If you just have modified your file and you want to force syncing, click the **Synchronize now** button in the navigation bar.

> **Note:** The **Synchronize now** button is disabled if you have no file to synchronize.

## Manage file synchronization

Since one file can be synced with multiple locations, you can list and manage synchronized locations by clicking **File synchronization** in the **Synchronize** sub-menu. This allows you to list and remove synchronized locations that are linked to your file.


# Publication

Publishing in StackEdit makes it simple for you to publish online your files. Once you're happy with a file, you can publish it to different hosting platforms like **Blogger**, **Dropbox**, **Gist**, **GitHub**, **Google Drive**, **WordPress** and **Zendesk**. With [Handlebars templates](http://handlebarsjs.com/), you have full control over what you export.

> Before starting to publish, you must link an account in the **Publish** sub-menu.

## Publish a File

You can publish your file by opening the **Publish** sub-menu and by clicking **Publish to**. For some locations, you can choose between the following formats:

- Markdown: publish the Markdown text on a website that can interpret it (**GitHub** for instance),
- HTML: publish the file converted to HTML via a Handlebars template (on a blog for example).

## Update a publication

After publishing, StackEdit keeps your file linked to that publication which makes it easy for you to re-publish it. Once you have modified your file and you want to update your publication, click on the **Publish now** button in the navigation bar.

> **Note:** The **Publish now** button is disabled if your file has not been published yet.

## Manage file publication

Since one file can be published to multiple locations, you can list and manage publish locations by clicking **File publication** in the **Publish** sub-menu. This allows you to list and remove publication locations that are linked to your file.


# Markdown extensions

StackEdit extends the standard Markdown syntax by adding extra **Markdown extensions**, providing you with some nice features.

> **ProTip:** You can disable any **Markdown extension** in the **File properties** dialog.


## SmartyPants

SmartyPants converts ASCII punctuation characters into "smart" typographic punctuation HTML entities. For example:

|                |ASCII                          |HTML                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|


## KaTeX

You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/):

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> You can find more information about **LaTeX** mathematical expressions [here](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).


## UML diagrams

You can render UML diagrams using [Mermaid](https://mermaidjs.github.io/). For example, this will produce a sequence diagram:

```mermaid
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
```

And this will produce a flow chart:

```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ4OTQ1Mzc0MiwtMTk1MjQzNDIzMiwtMT
MzODAzNDUzMSwxNDYyODQ5NjI1LDIwNjc2NzYzOTksLTMwNzgz
ODQ3NSw2ODE3NDQyNDIsLTUzNTU0NjM2MF19
-->