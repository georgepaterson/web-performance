# Web performance

## Performance and usability

## Measuring performance

### Client versus server performance

## Server performance techniques

### Cache static HTML

### Content delivery networks

## Client performance techniques

### HTTP requests

### CSS and JavaScript external files

### Code quality

### Content types

### DOM depth

### Flash of unbehavioured content

### Repaint and reflow

### JavaScript blocking

### Asynchronous JavaScript loading

### JavaScript render logic

### Asynchronous image loading

Inline images that are not initially visible to the user can present an additional HTTP and resource request before a Web page completes loading. 

One possible solution to avoid this is to remove the image source and set it as a data attribute. JavaScript can then be used to set the image source from the data attribute on a triggered event. A classname common to all asynchronously loaded images can be used to easily reference the JavaScript enhanced images.

	<img class="asynchronous" data-src="/images/example.jpg" alt="An example image" />
	
If a non-JavaScript fallback is required the same image can be wrapped in a noscript tag, the classname used to identify all asynchronously loaded images can then be used to hide the JavaScript enhanced images.
	
	<img class="asynchronous" data-src="/images/example.jpg" alt="An example image" />
	<noscript><img src="/images/example.jpg" alt="An example image"  /></noscript>
	
Standard JavaScript events can then be used to set the source of the required image. The exact event trigger should be chosen on a per module basis.
	
#### Empty image source

### Image sprites

#### Base64 encoded images

### Conditional comment blocking

## Notes

## Resources

1. [W3C Web Performance Working Group](http://www.w3.org/2010/webperf/)
2. [Response Times: The 3 Important Limits](http://www.useit.com/papers/responsetime.html)
3. [Repaint and reflow](http://dev.opera.com/articles/view/efficient-javascript/?page=3#reflow)
