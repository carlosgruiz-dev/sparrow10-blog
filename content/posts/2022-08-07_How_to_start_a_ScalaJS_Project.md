---
title: "How to start a Scala.js project"
date: 2022-08-07T17:51:26Z
draft: false
tags: ["scala.js", "scala", "web", "sbt", "tools"]
---

[Scala.js][1] is a Scala to JavaScript compiler. In this post, we are going to see a couple of ways
to start a project. Foremost we need to install [sbt][2] and [node.js][3] (I prefer to use
[nvm][4] which allows us to install and use different versions).

One way to start a project in Scala is using a [giter8][5] template. For [Scala.js][1] there is no
template from official sources, but some were created by [third parties][6]. These templates create
projects for [Scala.js][1] and add libraries to help to build your application more easily.

For example if you wan't to create a project with [Scala.js][1] and [Akka HTTP][7] you can use
[giter8][5] from [sbt][8] on the command line by typing:

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 akka-http-scalajs-template.txt >}}

And you are set to start coding your application.

![screenshot of ][9]

Another option to start a project with [Scala.js][1] is following the steps from the
documentation to [set up a project][10]. In this case, you can add this compilation option to a new
project or just start on a clean slate. For that we start with a new project, we can use a seed
[giter8][5] project.

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 create-project-from-giter8-seed.txt >}}

Now we add the [Scala.js][1] sbt plugin in `project/plugins.sbt`

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 add-scalajs-sbt-plugin.sbt >}}

And enable this plugin on the `build.sbt` file of the project.

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 enable-scalajs-sbt-plugin.sbt >}}

Last, we need to specify the [sbt][8] version in `project/build.properties`.

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 project-build.properties >}}

To get your stack traces resolved on [node.js][3], you will have to install the source-map-support package.

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 node-packages.txt >}}

And now lets add some code in `src/main/scala/example/Hello.scala` to test our configuration.

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 Hello.scala >}}

And now we can run the projec typing: `sbt run`

{{< gist carlosgruiz-dev 1cd12d9b87c4ffcd14af7f4cae1ba411 sbt-run.txt >}}

See you next time to integrate HTML to thie newly created project.

[1]: https://www.scala-js.org/
[2]: https://www.scala-sbt.org/1.x/docs/Setup.html
[3]: https://nodejs.org/
[4]: https://github.com/nvm-sh/nvm#intro
[5]: http://www.foundweekends.org/giter8/
[6]: https://github.com/foundweekends/giter8/wiki/giter8-templates#scalajs
[7]: https://doc.akka.io/docs/akka-http/
[8]: https://www.scala-sbt.org/
[9]: /images/akka-http-and-scalajs-template-project.png
[10]: https://www.scala-js.org/doc/tutorial/basic/
