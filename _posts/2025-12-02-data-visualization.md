---
tags: [data, exploration, visualization]
---

Ranja Sarkar

![ben2](https://github.com/user-attachments/assets/a07ad6b0-3918-47d8-9e29-f87dcb4c80c4)

In one of my previous [posts](https://ranja-sarkar.github.io/2025/11/28/know-how.html), I have highlighted *data visualization* and how it is essential to understand data. A single post however is not enough to state the criticality of data visualization from data exploration until after a model (trained with the data) is operational that is, in production.

[Anscombe's quartet](https://en.wikipedia.org/wiki/Anscombe%27s_quartet) outlines the importance of graphing data before analysing. 

<img width="272" height="284" alt="add" src="https://github.com/user-attachments/assets/9470c271-14f5-41a9-87ca-ba978314f0f6" />

The quartet data - four identical descriptive statistics, yet four different distributions when plotted and visualized. It only reinstates how powerful exploratory data analysis by visualization is. A visual explanation is mightier than explaining data through statistics, implying the importance of looking at a [dataset graphically](https://matplotlib.org/stable/gallery/specialty_plots/anscombe.html) and not only relying on its basic statistics.

<img width="361" height="292" alt="aq" src="https://github.com/user-attachments/assets/c703278d-e9d6-4022-ab08-2c57a1c8920a" />

When it comes to visualizing data, less is more. Keeping only what is necessary in the visual not only helps the developer understand what important information the data yields, but also helps the business or audience draw meaning from the visual.

<img width="362" height="57" alt="graph" src="https://github.com/user-attachments/assets/01696333-a3f4-45d1-aa21-d6c01119071b" />

There are caveats to data visualization as well. A collection of such caveats is nicely captured by [Yan Holtz](https://www.data-to-viz.com/caveats.html). Few of my favorites are "too many distributions in one chart", "annotate your chart", and the "Simpson's paradox".

[Simpson’s paradox](https://www.data-to-viz.com/caveat/simpson.html) is a statistical phenomenon in which a trend appears in several different groups of data when graphed but disappears or reverses when these groups are combined. 

It is fascinating how there are different ways to look at the same dataset. Mathematician **Jordan Ellenberg** said that the lesson of Simpson's paradox "is not really to tell us which viewpoint to take, but to insist that we keep both the parts and the whole in mind at once".

Look at the scatterplot of whole data, then look at the same for 3 groups of the dataset. We understand that the positive correlation's due to a difference between groups. Actually, the correlation is even negative when each group is considered separately.

<img width="479" height="323" alt="11" src="https://github.com/user-attachments/assets/db752c4e-9b56-4fdf-a9bb-44da61e659d6" />
<img width="469" height="327" alt="22" src="https://github.com/user-attachments/assets/6a47e2f1-30b2-437c-b1dc-b8805b21a792" />

The fact that the trend between two different variables reverses when a third variable is included is Simpson’s paradox. 

-----

We have Anscombe's quintet in 2025. Thanks to [Carl McBride Ellis](https://github.com/ranja-sarkar/ranja-sarkar.github.io/blob/05032475acb828274cfcbc1933bde4c8b00edd12/_posts/assets/Anscombe_quintet_paper.pdf) for his work on these datasets. The new and fifth dataset serves as an illustration of the  Simpson’s paradox.

<img width="424" height="194" alt="sp" src="https://github.com/user-attachments/assets/898a6c7c-ccc4-4971-8e69-e477fc4c9053" />
<img width="386" height="149" alt="dat" src="https://github.com/user-attachments/assets/f88fb4ab-625a-4bc3-a4b9-8c55b0208ef6" />


The new (#5) dataset is in complete concordance with the summary statistics of the original Anscombe’s quartet.

-----

It is not good-to-have, or nice-to-have, it's a must have - *data visualization*. It is a core, analytical skill required for problem-solving. 



