# Loading Animation

Coming soon...

One minor detail once things actually started to get dynamic is it looks empty for a second when you refresh it, if reload, it's empty and then it loads and that's fine. That's a natural part of how the web works, which is why we typically have loading messages so that the user knows that things aren't broken and things flow a little bit better. So when you start working with react, adding loading animations and loading screens is something that is very important to your workflow. So how can we add? So my goal is this, the first low is before we've finished the Ajax call, which sometimes is very fast. I'm going to have one row that just says loading. So if you look over close a few things, this will actually happen inside of our lowest level rep log list because this is actually what holds the body. So it's out of here. Instead of rendering all of these, we'll just have a single row that says loading. So we ultimately need to know is whether or not the Ajax call has finished and that is something that rep log app will know. It knows when it finishes loading, 

so to keep track of that, we need to add a new state, so up at the top I'm going to add a new state called is loaded. False. We can use this as a generic flag to make sure that you know to set when this component has fully look finished loading and then down who actually finished the Ajax call will change. This is loaded to true awesome. Now because we just added this new is loaded state thinks the way we are rendering our child component, this is going to be automatically pass as a new is loaded prop, so that's great because now we can go to rep logs. I mean reorganize things a little bit here. When you go into it, Chow, it's child upon rep logs at the bottom, as is loaded as a prop types. That pool that is required. You have noticed that I make most things required. That's a personal preference. Since this is my application, I know that I should always be passing. It is loaded, so I like making things required because probably if is loaded is missing. It's probably a mistake on my part. I'm not going to be reusing my rep logs elsewhere, so I don't need to make it extra flexible and make all of my props optional. 

Now that we have the prototype set up, won't go up top. We'll structure that is loaded and then down when we actually render our rep log list will pass his load of equals is loaded, and finally in rep log list we'll do the same thing. I'll actually copy our prop, type the bottom there. Then we can go up and restructure is loaded, and then down here we'll handle that. Now here's what's interesting. Basically if things are not loaded yet, we don't even really need to run any of this code down here. This will be empty. We can actually short circuit the entire process, so if not is loaded, then we can just return a completely new set of jsx. So I'll put a new body tr tr and then we'll do a td call span equals four in class name equals and we'll use texts dash center and then loading up. Close up that td and I noticed one thing, it's called span with a capital s. that's another one of those rare cases where um, it's a slightly different than html. It's pretty easy though because Petri storm auto completed that for me. Perfect. Because this is a return, it's not going to hit our normal code down there. So let's try it. 

Grover refresh there. You could say just for a second, it says loading right when a refreshed awesome. And this is such a powerful thing because if you ever needed to for some reason, reload the components, you can just go and all I need to do is just change that state from is loaded true back to false and it goes back to the loading screen. So you can toggle that as needed. If for some reason you needed to reload things, how does the power of react.