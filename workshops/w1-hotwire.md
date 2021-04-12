# Notes about workshop - Hotwire: HTML over the Wire


### Workshop Details
##### Description
Last December, the team behind Basecamp and Hey released Hotwire, a library for managing client side interactions by sending HTML to the client. Hotwire bundles the Stimulus JavaScript library with an expanded Turbo library which makes a wide range of client side interactions possible without writing any custom JavaScript. In this workshop, attendees will see first-hand how powerful the new library is by adding powerful interactions to a basic Rails view.

##### Instructor
Noel Rappin is an Engineering Manager at Root Insurance. Noel has authored multiple technical books, including "Modern Front End Development For Rails" and "Rails 5 Test Prescriptions". He also hosted the podcast Tech Done Right. Follow Noel on Twitter @noelrap, and online at http://www.noelrappin.com.

##### Links:
1. http://www.noelrappin.com/: Noel Rappin website
2. https://github.com/noelrappin/rails_conf_2021_hotwire: Github Repo for the workshop


##### Questions
- What's Hotwire?
Turbo + Stimulus. Server side rendering, do thing on the HTML rather than re-render the entire page. That're sort of hierarchy.

- Layer of...?
![image](https://user-images.githubusercontent.com/55923773/114417967-a5b6c700-9be4-11eb-956d-75c20ca34ea1.png)

- Turbo Drive
> Rebranding of turbolinks, automatically handles navigation in the background (handle links, capture the request, get the response, update DOM iwthout reloading page), much less distracting and flickers. It applies to an entire page. 
> It doesn't use virtual DOM as React.

- To refresh part of the page:
> Inline edit
- Turbo Frames
> 3 pieces of Turbo. Separate into smaller pieces, and treat is as pieces to be updated.

Branch workshop_01 for the code changes. (concert#create, concert#show, _form & _concert partials.

Create a custom html frame call <turbo-frame id="concert_XX" ...>, it captures ... makes the HTML request, response as full-edit page. Custom HTML tag defined by turbo-frame library.. Webpack here loads @hotwired/turbo-rails library..

Problem: Some navigation stays with the frame.

Turbo is capturing the HTML request...


Workshops questions:
Workshop 1:
- It would be great to see some other examples of real websites or Apps where this technology ist useful and makes the most sense...
> Hey.com
- How many people these days have JS disabled? Is this something we really need to "worry" about?
- Would this technology make sense in an App for queing passengers to board a plane, since they reorganize all the time depending on their seats?

#####Workshop 2: https://github.com/noelrappin/rails_conf_2021_hotwire/compare/workshop_01...workshop_02
- MattyMC: Am I understanding correctly that when we update the concert, we want to render both the partial and also the list of favourites?
- phillipspc: so fair to say this situation (updating two sections of the dom) could also be handled by using the "_top" value for a full page refresh. But streams is better because it's more performant/efficient?
- cassar: If a request fails, will there be a default flash alert message?
- Jon Sullivan: Noel what's your take on the :inline flag you're setting up yourself vs. using view variants automatically for the right view to be rendered?
- maxx1128: This is making me think it has great applications for error alerts, like rerendering content inside of an aria live region. Could you also rerender inputs with error states/messages after submitting them?
- fdoxyz: Is there something specific the project is using "rails/ujs" for? Based off this note: https://github.com/hotwired/turbo-rails#compatibility-with-rails-ujs
- Jon Sullivan: I think Rails 6.1 swapped back to remote: false in the default rails forms configs too... Hotwire + remote: true = a bad time AFAIK
- tfinn: Does Turbo Streams do anything to ensure order of updates?
- Does rails become less overwhelming with time :sweat_smile:
- TorpedoSkyline — Today at 11:46 PM If you have a project that is currently using something like React, can you start adding Hotwire in piecemeal
- JimZ — Today at 11:47 PM honestly webpacker has made getting up-and-running with Rails much harder than it used to be
- Brent — Today at 11:48 PM I missed your explanation for webpacker 6 beta -- will webpacker 5 not work with hotwire?

##### Workshop 3 (Turbo streams): https://github.com/noelrappin/rails_conf_2021_hotwire/compare/workshop_02...workshop_03
- Daniel Magliola — Today at 11:52 PM What's the difference between update and replace?
- Stephan — Today at 11:52 PM Why not always use Turbo Streams?
- 876injinier — Today at 11:54 PM I thought Turbo Stream was more for real-time functionality
> t27duck — Today at 11:54 PM It can be. It's when you put action cable on top of streams
- Ashish Prajapati — Today at 11:55 PM We can use Action Cable with Turbo JS to work in realtime.
- KyleFromMalaysia — Today at 11:56 PM What're the differences compared to action cable?
> Ashish Prajapati — Today at 11:58 PM Rails uses JavaScript Turbolinks. Turbolinks allow a Rails application to perform as a single page application without the client-side JavaScript framework. Because of this, ActionCable methods will not run when we need them to. To get past that, we can turn off Turbolinks or purposely trigger page-loads.
- tonys — Today at 11:57 PM It seems to me all of this extra stuff doesn't really make things easier for most of what we would do for a user.

##### Workshop 4 (Add animation): https://github.com/noelrappin/rails_conf_2021_hotwire/compare/workshop_03...workshop_04
- Stephan — Today at 12:01 AM From which book are the "book examples"? "Modern Front-End…"?
- Jon Sullivan — Today at 12:01 AM Noel you didn't update the "Make Favorite" button, right? Previously it was attempting the turbo-stream MIME type but we hadn't configured that partial so Rails was just sending back the plain HTML?
- mlabarca — Today at 12:00 AM It's gonna take some time and practice to get wrap my head around it but not having to add react or some client side js stuff for just a form is a huge time save
> 876injinier — Today at 12:01 AM You will be quite surprised how redundant it makes most front-end frameworks for Rails just implementing Stimulus
- Francesco Aiello — Today at 12:02 AM What does the <% -  do compared to <% or <%=?
> Noel: It doesn't display & doesn't create a new one
- Jon Sullivan — Today at 12:05 AM Could you do a Turbo Stream replace with a version of the object that does have animate_out: true then immediately do Turbo Stream remove? Or would that happen too quickly?
- jeffdill2 — Today at 12:05 AM where can we find helpful snippets like what you just added to application.js?
- joel.cahalan — Today at 12:06 AM where is the hotwire dev forum located?
> https://discuss.hotwire.dev/
- Peter Phillips — Today at 12:06 AM so cool. what's the animation library being used again? (anyone in chat know?)
> animate.css
- Tasos Latsas — Today at 12:08 AM There is also a channel dedicated to hotwire in the stimulus reflex discord server https://discord.com/invite/stimulus-reflex
- TinaBellVance — Today at 12:09 AM what about accessibility and things like keyboard-based navigation?
- gingerlime — Today at 12:09 AM Once you "get" turbostreams, then is there really a need for turboframes? is it basically a superset of frames?

##### Workshop 5(): https://github.com/noelrappin/rails_conf_2021_hotwire/compare/workshop_04...workshop_05
- ljsc — Today at 12:12 AM So all the bits up to this point do not depend on ActionCable?
> alex_ghiculescu — Today at 12:12 AM correct
- brianloomis — Today at 12:13 AM just that one nugget. dont use current+_User in partials with action cable. == saved a morning or afternoon of beating head on wall.
<img src="https://media.discordapp.net/attachments/826229651587465217/831200688125771816/rails_5_actioncable_concepts.png"/>

- ziemek — Today at 12:17 AM We had lots of problems trying to use hotwire with sessions.  Does anyone have some solutions for this?
- Filipe (he/him) — Today at 12:17 AM Is there a way to create another abstraction to put these callbacks other than the model? Custom form objects?
> Ashish Prajapati — Today at 12:18 AM Yes, you can write them in Concerns and include that concern in your rails model. If you are planning to re-use or something.
> Horia Radu — Today at 12:18 AM use service object for operations and, in the service object, also broardcast on your streams
- Helio Cola (he/him) — Today at 12:16 AM can you image DHH doing TDD on AR callbacks? :exploding_head:
- Peter Phillips — Today at 12:16 AM ViewComponent also works really nice with these
- elbarto — Today at 12:20 AM Can we make an action cable broadcast on a controller?
- Sarah S — Today at 12:21 AM beginner question: so it looks like if my app uses minimum JS I could go straight to Hotwire and doesn't need to do Stimulus, unless for super custom stuff?
- liam.elliott — Today at 12:23 AM Speaking of stimulus, how would you compare turbo streams to stimulus reflex?
- Francesco Aiello — Today at 12:23 AM Is this demonstration also in your book?
> Yes
- elbarto — Today at 12:24 AM Do you have a snippet of code using the Action Cable Broadcast o a controller?
- danieldpence — Today at 12:24 AM What's the best approach for handling user-specific data in turbo_streams since streams are rendered outside of the session? For example, only allowing comment authors to see edit/delete links on a comment.
- Peter Phillips — Today at 12:25 AM Question: Having worked with Hotwire a good bit, what changes or improvements to it are you hoping to see down the road? (ie. What do you feel are the rough edges that need smoothing?)
- kstratis — Today at 12:27 AM Stimulus based sorting happens like this in Hey... https://github.com/hotwired/turbo/issues/109#issuecomment-761538869
- gingerlime — Today at 12:25 AM Once you "get" turbostreams, then is there really a need for turboframes? is it basically a superset of frames?
- Ryan — Today at 12:27 AM do you know of any way to add turbo, without turbo drive?
- Jack M (he/him) — Today at 12:28 AM So would you add includes(:user) to most scopes for use in Turbo?
- Josh Puetz — Today at 12:28 AM Any guesses what will be in Hotwire Strada?
- ShanaLMoore — Today at 12:29 AM What about writing tests/specs? Any recommendations?
> Crypress & Capybara for end-to-end testings
- jcoyne — Today at 12:30 AM Another good blog article to checkout https://evilmartians.com/chronicles/hotwire-reactive-rails-with-no-javascript
