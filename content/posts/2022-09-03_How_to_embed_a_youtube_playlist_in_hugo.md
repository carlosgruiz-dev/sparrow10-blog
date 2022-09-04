---
title: "How to embed a YouTube playlist in a Hugo website"
date: 2022-09-03T12:02:50Z
draft: false
tags: ["hugo", "youtube", "stackoverflow"]
---

[Hugo][1] is very flexible to create a static page website, with rich contents. So, one of the
things we like to share is YouTube videos, and of course playlists.

To embed a youtube video we can use the following shortcode:

![how to embed youtube videos](/images/how-to-embed-youtube-01.png)

and the result is as follows:

{{< youtube F8pyaR4uQ2g >}}

And for embedding YouTube playlist we need a custom shortcode as this [StackOverflow post][2]
indicates:

> 1. Create: `/layouts/shortcodes/youtubepl.html`
> 2. In that file place the following: (based on the [built-in youtube shortcode][3])
> ```
> {{- $pc := .Page.Site.Config.Privacy.YouTube -}}
> {{- if not $pc.Disable -}}
> {{- $ytHost := cond $pc.PrivacyEnhanced  "www.youtube-nocookie.com" "www.youtube.com" -}}
> {{- $id := .Get "id" | default (.Get 0) -}}
> {{- $class := .Get "class" | default (.Get 1) -}}
> {{- $title := .Get "title" | default "YouTube Video" }}
> <div {{ with $class }}class="{{ . }}"{{ else }}style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;"{{ end }}>
>  <iframe src="https://{{ $ytHost }}/embed/videoseries?list={{ $id }}{{ with .Get "autoplay" }}{{ if eq . "true" }}&autoplay=1{{ end }}{{ end }}" {{ if not $class }}style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border:0;" {{ end }}allowfullscreen title="{{ $title }}"></iframe>
> </div>
> {{ end -}}
> ```

And using now this shorthand:

![how to embed youtube playlist](/images/how-to-embed-youtube-02.png)

We got this result:

{{< youtubepl PLEiEAq2VkUUK3tuBXyd01meHuDj7RLjHv >}}

Note the list of videos on the top right position.

See you next time.

[1]: https://gohugo.io/
[2]: https://stackoverflow.com/a/72068135
[3]: https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/shortcodes/youtube.html
