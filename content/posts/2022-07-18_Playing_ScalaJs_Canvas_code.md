---
title: "Playing with Scala.js and a canvas (code)"
date: 2022-07-18T21:29:57Z
draft: false
tags: ["scala", "scala.js", "web", "javascript", "canvas", "code"]
---

If you look at [yesterday's article][3], you maybe wonder how it works. Well, the code is very
straightforward. We import our dependencies for [exporting the function][4], [using the dom][5],
and [generating random numbers][6].

[![Code for creating a canvas and change color every second][1]][2]

Using a Scala object, we create a method called `main` and add an [annotation][4] to say the
[Scala.js][7] compiler that we want to expose this function. Inside the function, we create a
[canvas][8] object, add it to the dom, and adjust its size to fill all the space.

Next, we get the context for the canvas object and create a function that changes its color
generating three random numbers (one for each value of the intensity of the color red, green, and
blue).

Finally, we set that the function that changes the canvas color will run every second. And that is
it. By the way, I'm using [carbon][9] for code styling.

See you next time.

[1]: /images/canvas-scalajs-01.png
[2]: https://gist.github.com/carlosgruiz-dev/daa84671cc10dd02f5f111c309724b3b
[3]: /posts/2022-07-17_playing_scalajs_canvas/
[4]: http://www.scala-js.org/doc/interoperability/export-to-javascript.html
[5]: https://scala-js.github.io/scala-js-dom/
[6]: https://www.scala-lang.org/files/archive/api/2.13.8/scala/util/Random.html
[7]: http://www.scala-js.org/
[8]: https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API
[9]: https://carbon.now.sh
