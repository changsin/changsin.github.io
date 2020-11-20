---
layout: post
title: "Jekyll Tips and Tricks"
subtitle: "Useful Jekyll tips and tricks"
categories: coding
tags: web
comments: true
---
## Files and folders
### File names
A blog file needs to have the format of [year]-[month]-[day]-[name of the post].md

### Folder location
The blog files need to be under _posts folder, but you can create sub-folders and they will be picked up by
Jekyll as a sub-path in url. For instance, if you have 'ai' as s sub-folder, the url path will be

```markdown
https://{{site.url}}/ai/2020/11/20/<blog name/
```

### Image files
If you want to have images in your blog post, you need to have the images in a sub-folder.
The problem is the location of the image files need to be correctly specified.
For Jekyll, each blog post is mapped differently depending on the date.
The best way is to create a static sub-folder under assets and create links.

```markdown
    ![word2vec]({{site.url}}/assets/images/wordvec_overview.png)
```