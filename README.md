# Web performance

## Performance and usability

Web response times and usability is based on psychological research by Miller 1968[1](#note-1) and Card et al. 1991[2](#note-2). Referencing Table 3 Human time constants for tuning cognitive co-processor of Card et al. we have three constants.

* The perceptual processing time constant - 0.1 seconds. A 0.1 second response time creates the illusion of an instant response time. The user will not perceive a task being completed.
* The immediate response time constant - 1 second. In a 1 second response time the user does not lose confidence in the system waiting for a response, there is no need to inform the user that a task is being processed. An action above 1 second should have an indicator that a task is being processed.
* The unit task time constant - 10 seconds. A 10 second response time is the upper limit before a user loses confidence in the system performing a desired action. The user will need an indicator that the task is being processed and where possible an indicator of when the task should be finished allowing the user to complete an alternative task 

Using these constants as reference for Web page response times, we can conclude that although all browsers provide a task indicator, a response time of under 10 seconds is preferred, with an optimal response time near 1 second.  

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

### Reduce JavaScript rendering

### Asynchronous image loading

Inline images that are not initially visible to the user can present an additional HTTP and resource request before a Web page completes loading. 

One possible solution to avoid this is to remove the image source and set it as a data attribute. JavaScript can then be used to set the image source from the data attribute on a triggered event. A classname common to all asynchronously loaded images can be used to easily reference the JavaScript enhanced images.

	<img class="asynchronous" data-src="/images/example.jpg" alt="An example image" />
	
If a non-JavaScript fallback is required the same image can be wrapped in a noscript tag, the classname used to identify all asynchronously loaded images can then be used to hide the JavaScript enhanced images.
	
	<img class="asynchronous" data-src="/images/example.jpg" alt="An example image" />
	<noscript><img src="/images/example.jpg" alt="An example image"  /></noscript>
	
Standard JavaScript events can then be used to set the source of the required image. The exact event trigger should be chosen on a per module basis.
	
#### Empty image source

An empty image source can cause the browser to make a request for the relative page, generating a significant performance hit.

Although the HTML5 specification has changed the description of the image src to avoid this, it is recommended that an empty image src is avoided.

### Image sprites

#### Base64 encoded images

### Conditional comment blocking

## Notes

1. Miller, R. B. (1968). Response time in man-computer conversational transactions. Proc. AFIPS Fall Joint Computer Conference Vol. 33, 267-277. <a name="note-1" />
2. Card, S. K., Robertson, G. G., and Mackinlay, J. D. (1991). The information visualizer: An information workspace. Proc. ACM CHI'91 Conf. (New Orleans, LA, 28 April-2 May), 181-188. <a name="note-2" />

## Resources

1. [W3C Web Performance Working Group](http://www.w3.org/2010/webperf/)
2. [Response Times: The 3 Important Limits](http://www.useit.com/papers/responsetime.html)
3. [Repaint and reflow](http://dev.opera.com/articles/view/efficient-javascript/?page=3#reflow)
4. [Empty image src can destroy your site](http://www.nczonline.net/blog/2009/11/30/empty-image-src-can-destroy-your-site/)
5. [Best Practices for Speeding Up Your Web Site](http://developer.yahoo.com/performance/rules.html)
