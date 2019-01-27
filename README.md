Early meteor+vuejs app to explore components

Start with https://guide.meteor.com/vue.html
Use meteor-vue-tracker with a reactive var, not a collection
Then add some bootstrap, with https://bootstrap-vue.js.org
And create a child component that's wired in via events

It works initially (changes in either text box change the text everywhere)
... but if you click clear twice or swap between the boxes then eventually one of the boxes will get out of sync
