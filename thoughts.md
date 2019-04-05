---
layout: page
title: Arguments with a Strawman
permalink: /thoughts/
---

<div class="home">

I’m generally afraid to share opinions. No matter how careful I try to be, I'll always say something that isn't quite representative of what I think or what I think may not quite capture the subtleties of the topic. But shutting up’s decidedly not how to get good at developing opinions, and while some of the things I say may be steps backwards, saying nothing at all is assuredly a non-step nowhere. So I'll write them down for you here. And in writing them down, I'll join with the ranks who lack sense, as Plato has Socrates describe to Phaedrus (276c, translated by Alexander Nehamas and Paul Woodruff, in the Complete Works of Plato, Hackett Publishing 1997):

> > Socrates: Now what about the man who knows what is just, noble, and good? Shall we say he is less sensible with his seeds than the farmer is with his?
> > Phaedrus: Certainly not.
> > Socrates: Therefore, he won't be serious about writing them in ink, sowing them, through a pen, with words that are as incapable of speaking in their own defense as they are of teaching the truth adequately.

I don't at all claim to be the paragon of moral behavior or thought, although neither did Socrates, and I hardly believe his defense was authentic. Still, I hope when I say something inane or poorly considered that you, my reader, will help me understand where I have gone wrong.

<hr>

  <h1 class="page-heading">Posts</h1>
  
  <ul class="post-list">
    {% for post in site.posts %}
    {% if post.type == 'thoughts' %}
      <li>
        {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h2>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

  

</div>
