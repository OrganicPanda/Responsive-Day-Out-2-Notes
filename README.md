Responsive-Day-Out-2-Notes
==========================

Some notes for those that couldn't make it:

- "Sculpting Text" by Stephen Hay (@stephenhay)
    + Key takeaways:
        + HTML is responsive by default
        + Start with content then bring in design. Most websites are built out of containers that content gets crammed in to as an afterthought.
        + Start simple (no columns, no complex styles)
        + Design in the browser using new dev tools 
        + "Content break points, not device break points"
    + Slides: https://speakerdeck.com/stephenhay/sculpting-text

- "More Than Media Queries" by Sally Jenkinson (@sjenkinson)
    + Key takeaways:
        + Planning, 
        + Ethics
            + Do you know what's best for the user? Do you _need_ the user's location/contacts/call history ala Facebook?)
            + What about accessibility?
        + Responsibility (light level as an example of something that can be irresponsibly used)
    + http://www.sallyjenkinson.co.uk/blog/2014/06/29/responsive-day-out-review/
    + "If you ship something fast knowing it's shitty code, that's on you. Be responsible."
    + Slides: http://www.slideshare.net/sallyjenkinson/more-than-media-queries-responsive-day-out-2
    + Batman Says: http://image.slidesharecdn.com/final-export-140628043659-phpapp02/95/slide-12-638.jpg

- "The Core Model" by Ida Aalen (@idaAa)
    + Key takeaways:
        + Finding core pages based the overlap between business goals and user tasks
        + Prioritize content that users want and meets business goals.
        + Think about natural flows between pages. What might the user want next? 
        + Don't spend too much time thinking about the home page
        + People fill out forms on mobile and she has the proof!
    + Slides: http://www.slideshare.net/idaiskald/core-model-thinking-at-the-norwegian-cancer-society-responsive-day-out-brighton-june-27th (slides 89, 93 and 97 have data on mobile interactions) 

- "CSS Grid Layout" by Rachel Andrew (@rachelandrew)
    + Key takeaways:
        + CSS Grids are good but somewhat complex.
        + Can really help separate content from design.
        + Will likely be more useful than Flexbox for layout. Flexbox is more suited to module-level CSS.
    + Resources: http://www.rachelandrew.co.uk/presentations/css-grid 

- "Element Queries" by Dan Donald (@hereinthehive)
    + Key takeaways:
        + Media queries are good but what about modular components which should be shielded from knowing about the viewport width (what if you put it in a smaller column?)
        + Element queries are being considered for future versions of CSS but bring tricky problems that browsers would rather not think about (infinite loops for one)
        + Dan has come up with some ideas involving data-attributes and JS.
        + The BBC takes progressive enhancement very seriously. Every client gets all the content and then if a browser can "cut the mustard" they will be enhanced with richer interactions
    + JS: https://github.com/hereinthehive/responsive-modules 
    + More resources: https://kippt.com/hereinthehive/element-query-resources
    + Cut the mustard: http://responsivenews.co.uk/post/18948466399/cutting-the-mustard

- "Realistic Responsive Design" by Inayaili de León Persson (@yaili)
    + Key takeaways:
        + Responsifying ubuntu.com was difficult
        + Buy lots of test devices
        + Set rules that can be used for most cases (thing x goes next to thing y in scenario z)

- "The Container Model" by Oliver Reichenstein (@reichenstein)
    + Key takeaways:
        + Information Architecture is important
        + Don't let company politics decide what information is available to the user
        + Prioritize 
        + Columns and carousels exist only to suit department leads
        + Never place unrelated content on to one row just because it looks nice, fits nice or plays nicely with office politics. Only group content logically.
    + How The Guardian have used this: http://next.theguardian.com/blog/container-model-blended-content/
    + Guardian responsive site: http://www.theguardian.com/uk?view=mobile
    + GitHub: https://github.com/guardian/frontend

- "A Question of Deliverables" by Kirsty Burgoine (@KirstyBurgoine)
    + Key takeaways:
        + Learn from your mistakes
        + Be clear on what you are going to deliver vs what you are not

- "The Future of Media Queries?" by Stephanie Reiger
    + Key takeaways:
        + The future of CSS Media Queries is slightly weird
            + `scripting` - Used for detecting JS but JS support is near universal. The real issue is bad JS or JS that only partially loads.
            + `light-level` - Could be useful but poor hardware will likely make this risky to use.
            + `pointer` and `hover` - Sounds good but multi-input devices will cause confusion
            + `update-frequency` - Detect if complex animations would be appropriate. Could be good.
            + `overflow-block` and `overflow-inline` - How a viewport can overflow. Desktops can scroll but smart-watches maybe not. Again could be useful.
        + Was anyone asking for these features? CSS spec may not be in touch with the current landscape and needs of developers.
        + Maybe we need more native features? Example is being able to hand over components like `<nav>` so the browser shows them in a manner appropriate for the device. (what would the fallback look like? not sure about this one personally).

- "Laziness in the time of Responsive Design" by Ethan Marcotte
    + Key takeaways:
        + Laziness is good for developers.
        + Start with basics and add light touches. 
        + Why `<a href="#" class="btn btn-default">` when `<button>` is easier and more appropriate.
        + Why 
        ```html
        <div class="container-fluid widgets">
          <div class="row">
            <div class="col-xs-6 widget"></div><div class="col-xs-6 widget"></div>
          </div>
          <div class="row">
            <div class="col-xs-6 widget"></div><div class="col-xs-6 widget"></div>
          </div>
        </div>
        ```
        when 
        ```html
        <div class="widgets">
          <div class="widget"></div><div class="widget"></div>
          <div class="widget"></div><div class="widget"></div>
        </div>
        ```
        ```css
        .widgets {
          overflow: auto;
        }
        .widget {
          float: left;
          width: 50%;
        }
        .widget:nth-child(3n) {
          clear: left;
        }
        ```
        allows your content to remain clear of inline style junk plus it's more semantic and flexible
        + Another example showed a responsive video using the aspect ratio `padding-top` trick as a way to avoid JS and increase performance.
        + This message can be made clear with the recent example of the company blog launch.
            + No thought put in to responsive approach
            + Awkward content simply hidden from smaller devices 
            + Various jQuery hacks only making the problem worse
            + Complex design elements sized entirely in pixels not allowing any flex whatsoever
        + “Progressive enhancement is at the heart of every successful responsive design” 


Audio for all speakers: http://huffduffer.com/tags/responsiveconf2

Photos: https://www.flickr.com/photos/marcthiele/sets/72157645354768166/

## TODO:
Gather more notes from:
+ http://paulrobertlloyd.com/2014/07/responsive_day_out/
+ http://adamonishi.com/2014/06/beepcheeks-responsive-day-out-2/
+ http://thought.photos/on-being-responsively-creative/

(me: https://www.flickr.com/photos/marcthiele/14338571907/in/set-72157645354768166)
(me: https://www.flickr.com/photos/marcthiele/14338571137/in/set-72157645354768166/)
(me: https://www.flickr.com/photos/marcthiele/14521620291/in/set-72157645354768166/)

This guy reminded me of fonz: https://www.flickr.com/photos/marcthiele/14524206954/in/set-72157645354768166/ https://www.flickr.com/photos/marcthiele/14339045939/in/set-72157645354768166/

