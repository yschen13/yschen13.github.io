---
layout: default
---

I'm a PhD candadiate in computational neuroscience, mentored by [Dr.Terrence Sejnowski](https://cnl.salk.edu) at Salk. [My research](https://scholar.google.com/citations?user=7xTBMSkAAAAJ&hl=en) focuses on causality detection in time-series data and modeling computation principles in neural circuits. Check out my latest network causality estimation algorithm: [Dynamical Differential Covariance (DDC)](https://www.biorxiv.org/content/10.1101/2021.06.18.448901v2).

Besides lab research, I'm broadly interested in **AI algorithms, theories (and puzzles)**. During the years, I accumulated pages of [research notes (network dynamics, causality estimation, ICA algorithms)](#notes) and [side projects (Object recognition, SLAM, puzzle sovling!)](#fun-projects) and equivalently two M.S. degrees! 

I'm posting them here so that they don't have to go through the painful and lengthy review process to qualify as publications. If anyone is interested in these material, feel free to drop me an email (cyusi@ucsd.edu).

### Latest Publication
* Yusi Chen, Burke Q. Rosen and Terrence J. Sejnowski, Dynamical differential covariance recovers directional network structure in multiscale neural systems. _Cosyne 2021, bioRxiv(2021)_ [[paper](https://www.biorxiv.org/content/10.1101/2021.06.18.448901v2)][[code](https://github.com/yschen13/DDC)] [[5-min video](https://www.youtube.com/watch?v=okGOtK3Y7IM)]
  * Our ability to think, feel, and react depends on the underlying interaction patterns of distinct brain regions. This paper defines the interaction patterns in a dynamical system and derived an efficient algorithm to estimate it from time-series data.
* [All publications](https://scholar.google.com/citations?user=7xTBMSkAAAAJ&hl=en)


### Fun Projects
* Simultaneous Localization and Mapping (SLAM)
  * Core question in autonomous driving: how to represent the street map and self location with information from in-vehicle cameras and kinetic data (e.g. linear/angular velocity). Following are two Bayesian filters transforming visual/kinetic streams into latent variable series representing the map and location
  * Particle Filter: [[code]](https://github.com/yschen13/SLAM_ParticleFilter) [[report](./assets/files/SLAM_Particle.pdf)]
  * Unscented Kalman Filter: [[code]](https://github.com/yschen13/SLAM_KalmanFilter) [[report](./assets/files/SLAM_KF.pdf)]
* Image Classification through neural networks: [[code]](https://github.com/yschen13/Classification_CNN)
* Seahorse puzzle: [[code]](https://github.com/yschen13/Puzzle_Seahorse)
  * Nine square tiles to place in a 3-by-3 grid 
  * Around 100 billion possibilities with different positions and poses
  * Only ONE possibility to match all patterns on the edges
<!-- * [All projects](./projects.html) -->


### Notes
* Mathematical models for oscillatory signals in the brain 
  * [[Where does it arise from?]](./assets/files/Notes_Wave_generation.pdf)
  * [[Why do they oscilate?](./assets/files/Notes_Wave_Effect.pdf)]
* The past and future of Dynamical Differential Covariance (DDC)
  * [[Theoretical foundations of differential covariance](./assets/files/Notes_DDC.pdf)]
  * [[Other potential DDC variants](./assets/files/Notes_DDC.pdf)]
* The many algorithms of ICA
  * Real-valued ICA: infomax, FastICA, et al. [[note](./assets/files/Notes_ComplexICA.pdf)] [[code](https://github.com/yschen13/ICA)]
  * Complex-valued ICA: how to extend definitions to the complex field and translate it back to real-valued ICA. [[note](./assets/files/Notes_ComplexICA.pdf)] [[code](https://github.com/yschen13/ICA)]
<!-- * [All notes](./notes.html) -->


### Recommended Courses
* **[Probability Theory](https://www.youtube.com/channel/UCeKkMyeKBnec9Y3I_eI2BNQ)** 
  * by Prof. Todd Kemp from UCSD Mathematics
  * one-year sequence of courses to define probability concepts from the sample space
* **[Modern Physics](https://www.youtube.com/watch?v=ApUFtLCrU90&list=PL47F408D36D4CF129)** 
  * by Prof. Leonard Sussikind from Stanford
  * multiple lecture sequences introducing classical mechanics, quantum mechanic, et al.
* **[Robotics](https://natanaso.github.io/ece276a/)** 
  * by Prof. Nikolay Atanasov from UCSD Engineering
  * a clear and straightforward introduction of cutting-edge robotic algorithms.
* **[Information Theory](https://books.google.com/books/about/Elements_of_Information_Theory.html?id=VWq5GG6ycxMC)** 
  * by [Prof. Alon Orlitsky](https://jacobsschool.ucsd.edu/faculty/profile?id=54) from UCSD Engineering
* **[Computational Neuroscience](https://www.google.com/books/edition/The_Computational_Brain/z4pfDQAAQBAJ?hl=en&gbpv=0)** 
  * by [Prof. Terrence Sejnowski](https://cnl.salk.edu) from Salk (Yes, my PI)
  * for whoever wants to know about computational neuroscience.

### Service
* Reviewer for _Proceedings of the National Academy of Sciences_
* Reviewer for _Neural Computation_
* Graduate instructor assistant for system computational neuroscience, UCSD
* Graduate instructor assistant for bioinformatics, UCSD

### Awards
* Kavli-Helinski Fellowship (08/2021)
* National Scholarship of China (2016)


<!-- 
Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
``` -->
