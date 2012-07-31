---
title: Embed Code Id Tagging
layout: post
category: For Developers
for_developers: true
post_intro: <p>Using the Video Player API, you can create simple ID tagging that passes user info into your Wistia stats.  Your two options for executing this is:</p> <ol><li>using the <span class="code">wemail=</span> URL query string</li><li>a separate function using the trackEmail embed option.</li></ol>
---

## URL Query String Approach

The custom query string URL approach produces a link like this: <span class="code">http://your-video-URL.com?wemail=example@mail.com</span>.

If you have access to the user's email address (through log-in or form submittal, etc.) you can replace the 'example@mail.com' string with this information.  Note, the URL on the page where the video is embedded (and played from) must have the custom query string.

---

## Function with trackEmail Embed option

The new Wistia API embeds includes an option to track the viewer's email when they watch the video.  This process is predicated on there being a variable available on the client-side for tracking emails (ie. after they log in, their user info is tracked in a cookie).

**Note:** you will need to use the "API" version of the embed code to utilize this feature

Inside the embed code, you will see a snippet that appears like this:

<div class="code">
<pre><script type="text/javascript"> 
  var wistiaEmbed = Wistia.embed("bfc34aa023", {
    platformPreference: "html5",
    autoPlay: true,
    wmode: "transparent",
    container: "my_container"
  });
</script>
</pre></div>

We will be adding the <span class="code">trackEmail</span> embed option:
	
<div class="code"><pre>
<script type="text/javascript"> 
  var wistiaEmbed = Wistia.embed("bfc34aa023", {
    platformPreference: "html5",
    autoPlay: true,
    wmode: "transparent",
    container: "my_container",
    trackEmail: "userEmail"
  });
</script>
</pre></div>

The variables for Wistia video hashed ID (<span class="code">bfc34aa023</span>) and email address (<span class="code">UserEmail</span>) need to be updated to reflect your embedded video ID and the variable of your identifiable user information.
