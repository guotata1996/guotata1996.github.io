Jan 10, 2019, Icy night. Manhattan.

Roadbuilder, my recent personal project, has went through her (possibly) hardest part towards the 2nd milestone --- traffic simulation. More importantly, the whole system became 
one piece again, in other words, (almost) every line of code could be reached only by running once. 

## What is the project all about
When it comes to the motivation of something, it could be too much to explain, but it also could be unbelievably **naive**. Even if itself isn't at all.

Roadbuilder belongs to the latter.

I had a pretty weird hobby in my childhood. Strictly speaking, I didn't drop it until the third year of middle school.

What is it? City planning, or drawing roads, on _papers_. (When other boys are watching cartoons or playing games)

How much addicted? Believe it or not, I used up at least 500 pages of A4 papers. Some drawings were even done on A3/A2 papers, none of which was left with any blank.

Why quit? Because I got to know a game called "Simcity 4" from my cousin where I can draw roads on the computer.

Even myself couldn't understand where I picked up this hobby, but at that time I simply couldn't live without it.

You see, I'm just picking it up again, but not on paper. It's Roadbuilder.

## The First Failure
Actually it's not the first time I initialized a project of this kind. 

I made my first attempt in summer 2017, the 3rd year of my graduate study. I learned a little bit of Unity in advance, but coding only lasted one weekend.

The failure was mainly because a totally underestimate of difficulty. To me, how could Roadbuilder be more complicated than Flowfree game (a course project)?.
 I owe the estimation failure to my inexperience. I've never written more than 1500 lines in a single project at that time, how possibly could I do an estimation to this kind of stuff?

Once you get the scale of a problem wrong, things would get even worse. I rushed through 1300 lines in two days, without any thought on overall structure or design, as
I thought I would have finished in 1000 lines. The product is of course, piles of messy and buggy codes, with lots and lots of features unfinished.

There're plenty of lessons I learnd from this failure, but most importantly, I got a good estimation of the overall workload.

## Game of Making A Game
In most role playing games, you are set with a goal from the beginning. In pursuit of the goal, you gradually uncover the virtual world, learn about connections and rules,
which eventually builds up a way towards the ending.

My development procedure is quite alike. Here, the goal is quite straightforward: simulate roads and traffic of the real world. I mean even an illiterate could tell you what a road looks
like, and how cars run on it. 

Also note after all it's a **sim game**. _Looking good is enough_. This is extremely important because I can always use intuition and observation to figure out any solution, instead of
~~my biggest enemy~~ formula derivation (My ability in the former aspect is 100x better than the latter). It means every "Mission" in my "Game of Making A Game" wouldn't take me too 
long. The pleasure I enjoy upon completion can always make up for whatever it takes, just like in an RPG.

So far there's only one exception, where a bad (far from optimal) approach cost me almost two weekends' debugging. At the third weekend, I finally decided to delete the 300 lines of codes
where bugs frequently rise, and replace them with a completely different solution. Anyway, this is the kind of thing that constantly happen in a formal research, or even in a game ---
any bad decision at the early Don't Starve could be fatal. Nothing to complain.

## Freedom is a plus
The most fascinating aspect of a personal project is freedom. No project manager, no supervisor (no credit for it, either), everything is up to you. You can always keep a balance between
implementation difficulty and loss in simulation precision. There's absolutely no "Required features", only "Features you think are necessary". Thus, there's far less chance of getting
negative emotions that prevent you from moving on. From this point, my "Game of Making A Game" is even better than some computer games which require you to complete a series of
missions that you're already tired of.

I actually gave up many interesting features in "Building Tools", after a thorough evaluation of the implementation difficulty. Just like in a game, some decisions you made in the early
stage can greatly expand or limit your code's ability and potential in certain aspects. Each time I came up with a crazy difficult feature, I'd rather give up or wait until I have the 
ability to do all refactoring.

## Where I am
As far as I know, any state-of-the-art Simicity game should consist of at least 4 major parts:

1. Traffic system
2. Terrian and Landscape
3. Building Construction / Area Planning
4. Politics and Economy Simulation

For the traffic system part, here are my 3 milestones, in increasing order of difficulty:

1. Road construction --- 80% viable
2. Visible(discrete) traffic simulation (like vehicle behaviors I'm working on) --- framework set, but still much to improve
3. Invisible(continuous) traffic simulation (too slow if done as 2) --- still at the stage of investigation

## What's next
For now, most key features for road building and traffic simulation have completed and been tested. 

Honestly, this is not a moment of celebration. So far the code is only fine in not-too-ridiculous input, and on a limited scale. If you build hundreds of roads, run thousands of vehicles, or simply make roads too
close to each other, in countless ways the program will die. Also, most textures look ugly, and I certainly have to learn more about shaders in Unity. In a word, before moving on a real Simcity game, I have 
lots of shit to clean up.

But before all of these, there's one more important thing: reviewing and refactoring everything I've written, and documenting the most important designs (and downside in some designs). I'm not
a fan of doing documentation, like seldom do I leave comments, but writing down the purpose of some high level designs will certainly help people(including myself) quickly understand what I'm thinking these days.

Perhaps the best news is that, since the main framework has been done, everything is nearly self-explainary and I don't have to be hanging around the code all day long in case I forgot the meaning of 
something I typed a minute ago.

Basically this is just a summary or reflection, and I didn't intend to post any demo here. But I changed my mind as anyone with a patience to read through this nonsense deserves a tiny reward.

![build tools](../assets/img/post3/build.gif)

![traffic](../assets/img/post3/traffic.gif)

Check the [project homepage](https://github.com/guotata1996/roadbuilder) for more info.