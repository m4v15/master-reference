Inspired by dwyl process handbook found [here](https://github.com/dwyl/process-handbook)

## Preparing for your build sprint
1. Break down your user journey into user stories
1. Talk through your [choice of tech stack](./tech-choices.md) with the help of your mentors.
1. Run through the architectural flow of your app at this point, maybe redraw some wireframes on pen and paper.

## [Sprint planning](https://hackmd.io/s/SJz_QKOzE)

With your Scrum Master, write out your tasks to be done in issues.

- Go through user stories and decide on the very core ones that need to be done for the basic app to be working.
- Give these a milestone - Sprint 1
- Starting with these user stories we’ve made think about everything that needs to be done for all of them

Each issue should contain:
- acceptance criteria (define these with your PO)
- a priority label ([import DWYL labels](https://label-sync.herokuapp.com/login))
- a time estimate

Decide on:
- File structure - folders and what will go in them, not necessarily every single file! Be consistent across the app. 
- Linting rules
- Naming conventionsfor files and variables - camelCase, kebab-case, snake_case
- Where to use es6 and es5
- How you will handle Asynchronous code
All of these things should go into your readme.

Then
- order the issues in your milestone accordingly
- assign issues

Note: you may want to factor in technical spikes to your build time estimates, depending on your choice of tech stack.

## Starting work
1. Write your initial `README.md`, if you haven't done already.
Remember: You will have a time slot ("Today I Learned" in the 2nd week) for a quick show and tell. If you update your documentation as you go, you can use this to showcase what you have learned to the rest of your cohort.

1. With your mentor, set up your environment
    - Deployment (e.g. Heroku)
    - Continuous Integration (e.g. Travis)
    - Linter
    - File structure
