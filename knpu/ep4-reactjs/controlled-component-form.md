# Controlled Component Form

Coming soon...

So we just saw how we can use a control input where you actually set the value of an input to state this case number of hearts is state that stored up in rep log APP. 

Yeah. 

When you do this, you actually also need to add an on change so that when that field changes you actually update the state. Once you do this, everything else is kind of Nice because the components, the input automatically renders correctly based on the state and you can very easily read that state in other places to do what you need to do. In Rep log creator, we use the other methods. We use the method where we took advantage of refs so we can access the underlying html dom elements directly and then it's read off of their values. So I want be, I wanna, I want to see what the approach would, what the controlled component approach would look like for revlon creator. And that'll give you a recommendation about when you should use each one. So let's actually copying rep law, career prep, epilogue creator controlled components. Then in rep logs up top, we'll just copy the import statement, but now we're going to import from rap creator controlled components. Perfect, because we have two fields on this particular form, the select and also the input. We need two new pieces of state, so on top I'll add selected item ID, set the empty quotes and quantity value set to zero. We're also going to delete the old rough stuff because we're not wanting to be accessing the dom element directly anymore. 

Down in render 

we can destruction these items out of state selected item ID and quantity value. Then we're going to bind those to the actual elements, so instead of rep equals will say value equals selected item Id. Then down below on the input, same thing, value equals quantity value. Now one cool thing is when you use control components with select element, you actually add the value to be select element itself. You don't have to worry about adding these selected attribute on the right option. You can actually treat these select element as if it had a value directly. That's not how html works, but react gives you that shortcut, which is really nice. 

So as soon as we actually bind a some state to our elements, we need to add handler functions so that we can update them on change. So above this I'm going to create a new handle selected item change in a bad argument, and inside of here all we need to do is set that state. So this set state, I'm going to set these, select that item ID state to event that target that value. Now again, thanks to that, the nice way that react handles select elements. Instead of US needing to go to the dom, go find these selected index and then find the option using the index and then get its value. We can just say event.target. That value because the value is actually stored on the select element. So that's kind of Nice. I'll copy this because we also need copy this, paste it, make the next one called handle quantity input change, and this time we're updating the quantity value and it's still even at that target about value. Now, as soon as we make to handle functions, we want to make sure we go find those soft copy. The first method name in the constructor, I'll say this dot handle selected item change equals that same thing that find this and then we'll repeat that for handle quantity input change. 

We'll find that also to this and finally, now that those are ready, when did he go down to our elements and unselect wagons on change equals this dot handle selected item change and the same thing down on the input on change equals this dot handle quantity interchange, fear in after all that we should at least be able to play with this. So I moved back over refresh 

and then I'm going to inspect element on my text element and click that input. If I go over to react, it takes me to that same spot, which is nice because I can find the blog creator and we can see the state that set on that component and as we change things, the select actually does change and the input changes and you can see the value of changing behind your background. If you haven't seen, it's instantly so the control components are working perfectly. Now that we have the setup, the last thing we need to change is actually really nice. We need to change our handle form submit function. Instead of looking at the dominant elements themselves, we can just read the state, so on the top, on a d structure out the state first, so we'll say const selected, item Id, quantity value equals this dot state. We can delete the old rough stuff and then in the if statement, it's just if quantity value and that's it. We can use that quantity value further below and then for the selected text for a second, I'm just going to put out to do there at the bottom. This is where we actually clear the form. This is also easier. We don't need to actually clear the underlying elements. We just need to set the state on those. So reset the state of select the item id so that back to empty quotes and quantity value set back to zero. 

Now right now on ad rep log that the 

they actually handle their function is or passing off the item labels, the actual like visual part in the input field and they select a right now because our state is the selected item id, that's not exactly what we want and this has been a change later when we make our Ajax, call it a server, but to make this work right now, I need to actually turn this into the text. To do that, we're just going to take advantage of the fact that I set these item options up as an array up here so we can use that to look up the text for any specific option. So down here I'll say const item labeled equals. I say this dot item options that fine past this, a callback and Java script. We'll loop over this for each option will say, if the option ID equals this dot state that selected item Id, then that's the item we want to get back. And then we want to read the text key off of that. So this will find us the exact item in this array and they'll read the text to get up to get that shoe. So finally down here we can pass our item label 

and we should be good. Alright, so let's move over. Make sure that page is fully refreshed. Lives are big fat cap 25 times and we got it. Lift a Coffee Cup 10 times and we're good. So if you look at these two approaches, you notice that rep log creator is about 100 lines long and the rep log created risk controls departments. It's about 116 and that reflects the fact that with when you use control component, there's a bit more setup. Do you have to add more state? And then for every piece of state you have to add a handler for it. So there's more things to keep track of on the bright side. Oh, and I just noticed that we can use the local variable selected item Id. Not that that's important. Um, the nice thing is that when you actually need to read those values off, it's really easy because you're just reading values off of state instead of going out to the individual elements. 

So officially in react controlled components are actually the way that you're supposed to do things. However, because of the added complexity of the state and handlers, we usually recommend using the refs method instead. And this is not a perfect right or wrong answer and this is something that's hot intubated. So the story is that both are correct. We find the refs way of doing things a little bit simpler because there's less state in handlers to set up. But if you want to set up then if you do want to use control components because you liked them better than definitely use them in. Don't feel bad about it. One other downside of control components is that it does require your component to have state. And so if you have a functional components like rep logs, you'll need to refactor your functional component into a class because only classes can have state.

And now we switch back to using the old component.