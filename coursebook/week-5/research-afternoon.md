# Research Afternoon

## Continuous Integration

1. Research what Continuous Integration is and what assurances it can provide when building an application.
2. Create a basic Node project on Github that includes some tests with Tape, then sync your project with an online CI tool. Add a new feature to your project, commit your changes, then check on your CI tool to ensure your tests are still passing and your project build is passing. A popular tool is [Travis](https://travis-ci.org/), [this](https://github.com/dwyl/learn-travis) excellent tutorial will come in handy.
3. (Bonus) after verifying the latest changes, display the [build](https://camo.githubusercontent.com/3de407029531b1bcff394070e6d820d3f883a8c5/68747470733a2f2f7472617669732d63692e6f72672f6e6a736669656c642f6d79736974652e7376673f6272616e63683d6d6173746572) .svg file provided and display it at the top of your projects' README.md file.

## Streams and Buffers

1. Research what streams and buffers are in Node, how are they used in conjunction?
2. Create a Node project that lets a user run the command `node bigtextfile.txt` in the same directory as bigtextfile.txt and **stream** the contents of the file to the users terminal. Need a big file? How about a [book](https://www.gutenberg.org/).
3. (Bonus) Allow an additional argument to be provided in the command to specify a time interval of how often a chunk of text from the file is streamed to the terminal. E.G `node bigtextfile.txt 1s`

## Linting!
1. Research what linting is and why it is very useful? What is es-lint?
1. Install es-lint in an old project of yours following their getting started guide
1. What are some of the commands you can use with es-lint? How do you configure it (style guide vs. your own configuration)?
1. How can you set up your editor to show you the linting issues?
1. How can you ignore a line or a file in es-lint

