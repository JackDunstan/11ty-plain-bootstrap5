---
layout: base
eleventyNavigation:
  key: Pressbooks
  order: 1
PressbooksURL: https://rmit.pressbooks.pub/learninglab/wp-json/pressbooks/v2/parts
---


## Pressbooks

**This was written in Markdown.**

<div class="posts"></div>


<!-- partial -->
<script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.1/jquery.min.js'></script>
{% include "pressbooks.njk" %}
<script>
// Post.
var postsDiv = $( '.posts' );
postsDiv.html( '<p>⌛️ Loading...</p>' );
$.getJSON( 'https://rmit.pressbooks.pub/learninglab/wp-json/pressbooks/v2/parts', function( data ) {
		// Empty.
		postsDiv.empty();	
	// Loop through each post.
	$.each( data, function( i, part ){
		// Log the post data.
		// console.log( post );
		// Post Link.
		//const link = part.link;
		// Post Title.
		const title = part.title.rendered;
	    // Post Excerpt.
		const excerpt = part.content.rendered;
		// Post Content.
		// const content = post.content.rendered;
		// Building the HTML. 
		postsDiv.append( '<h3>'+title+'</h3><div>' + excerpt  );
	});
});
</script>

