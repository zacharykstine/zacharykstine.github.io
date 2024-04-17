---
title: 'AI Needs the Humanities'
date: 2024-04-13

# permalink: /posts/2012/08/blog-post-4/
---
zachary k stine  
posted: 2024-04-13    
updated:  
[add a pdf link when finished]      

# Consider making this a part 1 post and update it each week with the next part. Or just finish the whole thing over a week and post it all at once i guess.
     
# AI Needs the Humanities
## Primary argument: AI tells us that the ability to navigate an uncertain environment is to develop good models of how the environment works, to have evaluation functions that align with what we care about, and to encourage exploration beyond what is quanitfiably useful. Right now, we are collectively losing one of our most powerful engines of progress in our ability to 1) understand how the world works (transition models) and 2) clarify and interrogate values (ie, evaluation and exploration), which is the broad liberal arts education. This is true for all fields (eg, in computer sci, the shift to become a job training program vs science training), but this disaster is, right now, particularly dire for the humanities (but also some social sciences, mathematics outside of clear business uses, etc.). [This is more honest, and a way to spread the appeal of the argument to even more people]
# Primary points:
  
# 1. Hook and framing (which *could* be totally distinct from motivation, which could better function as a nice conclusion capped off with a motivating call to action (but avoid being overly specific with actions to avoid coming across as preachy
  
## Stuff about the AI discourse kind of bumming me out.
  
## The beauty of AI
[This makes sense depending on one particular framing of the introduction:] The thing that most bothers me about the discourse around AI is that its terms make it hard to see what is beautiful about AI. This is due to the fact that the discourse is always about what AI means for things external to AI, namely, us. This is unfortunate, but I don't mean to suggest that it's unnecessary. Given the myriad ways AI is being used that has a direct effect on people's lives, the debate is necessary. But still unfortunate. Setting all that aside for the moment, I'd like to do something different, to share a few ideas from AI that I happen to find beautiful and inspiring.  [Another option would be to push this down to an introductory framing of section 2.]

[Does it make sense to have a summary of what's to come here? Maybe in vague terms? Like, I believe that we are well on our way to building an AI that is capable of helping us solve our problems at a societal level. [This is pretty clickbaity but could be worth it! Then later clarify what I mean: that we are not just on our way to doing this, but we have been doing this since we were born! bc society IS an ai!]

# 2. THE BEAUTY OF AI. Lessons from AI about values: evaluation needs values from outside the system and impetus for exploration



### A model of optimal decision-making
[Note that this part is kind of the first big punch of the argument, that optimal decision-making requires the interrogratoin, interpretatoin, and clarification of values. May not want to bury it too far. Part of the effectiveness of this piece is the convenienve with which people can obsorb its message].
    
I find AI beautiful as attempts at formalizing notions of agency and meaning. In the case of agency, it gives us a precise way of talking about agency in general, agnostic of any particular scale or location of agency. It says that, agents are things that exist in some environment, which is has a particular way of working according to some transition model which may be of any variety or complexity (but the agent-environment distinction is basically superfluous in these formalizations). For this agent to work well, to achieve whatever its goals may be, to progress, it must decide on what actions to take, how to invoke its agency upon the environment. The state of the environment, really of the problem, changes and how it changes is in part bound up in the action taken by the agent (though, in highly complex problems, the state may change in some ways that are independent of the agent,; e.g., a self-driving car agent's problem state changes in response to where the agent moves the car, but also as a consequence of other environmental variables (which function simply as other agents)). Note that to define the environment is to also define the problem faced by an agent, just like Nguyen might say that designing a game is to design by invocation a particular range and timbre of agency, and so we might as well just be clear and dispense with the distinction: the agent exists within an environment-problem, and since the agent is connected by cyclical influence with the environment-problem, it can be viewed as a single system, which I also think is a quite beautiful metaphor of the notion that everything is connected.

This is a very broad way of stating what a transition model represents, in the form of a conditional probability:
[need to put into tex layout before publishing]: `new_state = f(old_state, action_taken)` or in a way that foregrounds the inherent uncertainty in most nontrivial environment-problems, `P(new_state | old_state, action_taken)`    [eq. 1]
The defined boundary between past and present, which is dictated by the specification of the problem-environment-agent, delineates a series of repeating agential junctures, the granularity at which the agent has the capacity to perceive the environment-problem. At each juncture, the agent must act (or not if the rules allow it, but in such a system, nonaction is functionally indistiguishable from action).

This probability distribution tells us how likely any possible state of the problem-environment will be as a consequence of two influences: the state of the past, and the action taken by the agent in the state of the past. Note that the statement of such a model does not suppose it must be specifiable in any particular, time-invariant or context-invariant way. All this statement gives us is a statement of how the present is the effect of the past and what was done in the past. In simplest illustrations, the transition model is often unchanging: rather than have `P(new_state | old_state, action_taken)_T=1, P(new_state | old_state, action_taken)_T=2, ... P(new_state | old_state, action_taken)_T=t, ...` (let's optimistically not put a cap on this), we can instead just have a time-invariant `P(new_state | old_state, action_taken)` without any possibility of the game mechanics themselves, changing.

Here's a beautiful model of optimal decision-making:  
optimal action = argmax_a{ SUM_s' P(s' | s, a) x U(s') }  
  
Let me try to explain exactly what this says with a simple example. 

### The ice cream problem

You, the agent, have one decision to make each day, which is the choice between two actions: attempt to obtain an ice cream from McDonald's and attempt to obtain an ice cream from Wendy's (I'm afraid this isn't the most creative illustration imaginable). Let's call the first action, `mcdonalds`, and the second action, `wendys`. All of your world boils down to three possible states: the state where you have obtained an ice cream from McDonald's, the state where you have obtained an ice cream from Wendy's, and the state where you were unable to obtain any ice cream at all as a result of the ice cream machine not working at your chosen fast food purveyor. Let's say that it is guaranteed that, in this world, if the ice cream machine is working, you *will* obtain an ice cream. Then we might describe each state as the following: 

Suppose that from past experience, you've noticed a pattern: the ice cream machine at McDonald's seems to be not working more often than the ice cream machine at Wendy's. If you are a sufficiently sophisticated agent, you might have some means of estimating and describing this pattern accurately (though some uncertainty will always be there, at least from our viewpoint since we don't know the state of every component in each ice cream machine that would be necessary for knowing with total certainty when each machine will be working or not). Perhaps you are able to formulate and build the following model of how your perspective-contingent world works: that the McDonald's ice cream machine works (at the time of your last calculation) 70% of the times that you go there, whlie the ice cream machine at Wendy's works 90% of the time. You might then derive the following model for how your world works:  
`P(today_state == mcdonalds_ice_cream | yesterdays_state, action == mcdonalds) = 0.7`  
`P(today_state == wendys_ice_cream | yesterdays_state, action == wendys) = 0.9`  
and so we can also say  
`P(todays_state == no_ice_cream | yesterdays_state, action == mcdonalds) = 0.3`  
`P(todays_state == no_ice_cream | yesterdays_state, action == wendys) = 0.1`  

Since, as far as you know, there is no discernible relationship between yesterday's state and today's (though such a relationship migh exist outside of this contingent perspective), we can simplify this to just  
`P(mcdonalds_ice_cream | mcdonalds) = 0.7`  
`P(no_ice_cream | mcdonalds) = 0.3`
`P(wendys_ice_cream | mcdonalds) = 0.0`  

`P(wendys_ice_cream | wendys) = 0.9`  
`P(no_ice_cream | wendys) = 0.1`  
`P(mcdonalds_ice_cream | wendys) = 0.0`  

It's tempting to assume that optimal decision-making ought to require nothing else, that knowing how the world works, how to best describe the future, is sufficient for acting rationally. AI's success is predicated on this being untrue. Instead, another equally ingredient, equally critical, is needed: the evaluation of possible futures, expressing the agent's desires for different realities, states of the problem-environment, in the form of a utility function. In other words, the agent-environment-problem system cannot provide us with any notion of correct action unless we determine how much we value the three possible states. To act optimally necessitates having clarity around my values. 

Suppose then, that you interrogate, reflect on, or generally clarify your values and come to the following realization on this particular day, prior to acting: you really do not like going without an ice cream and would much prefer to have an ice cream from either McDonald's or Wendy's. But on further reflection, you will realize that, if you had to pick one over the other, you have a slightly higher preference for McDonald's. If we're going to use this model of optimal decision-making, we will need to fill in the utility function U(s) for each possible state. Here's one possibility:  
`U(mcdonalds_ice_cream) = 10`  
`U(wendys_ice_cream) = 7`  
`U(no_ice_cream) = 0`  
  
Only now do we have the required ingredients for making a reasonable choice about which action to take, since we can now fill in all the blanks in eq. 1. The $arg max$ bit says we need to loop through each action, calculate the expected utility of taking an action, and returning the action which results in the maximum expected utility. Argmax is kind of like max except that, instead of returning the numerical value, it returns the variable associated with that numerical value, here, actions. 

`argmax{expected_utility(mcdonalds), expected_utility(wendys)`  
where  
`expected_utility(mcdonalds) = [P(mcdonalds_ice_cream | mcdonalds) * U(mcdonalds_ice_cream)] + [P(no_ice_cream | mcdonalds) * U(no_ice_cream)] + [P(wendys_ice_cream | mcdonalds) * U(wendys_ice_cream)]`.  
Filling in the blanks, we get that  
`expected_utility(mcdonalds) = (0.7 * 10) + (0.3 * 0) + (0.0 * 7) = 7`  

One way of interpreting what the 7 means here, is that it is the proportion of utility we can expect to receive on average. But more on that in a bit. Now let's see how the expected utility of the `mcdonalds` action compares with that of `wendys`:  
`expected_utility(wendys) = [P(wendys_ice_cream | wendys) * U(wendys_ice_cream)] + [P(no_ice_cream | wendys) * U(no_ice_cream)] + [P(mcdonalds_ice_cream | wendys) * U(mcdonalds_ice_cream)]`  
`                         = (0.9 * 7) + (0.1 * 0) + (0.0 * 10)` 
`                         = 6.3`  

Therefore, `argmax{expected_utility(mcdonalds), expected_utility(wendys)} == mcdonalds`. This tells us that, given the semantics of our values, the relationships between their numerical representations, the optimal action to take is to go to McDonald's today, despite that it carries a greater risk of winding up without ice cream. The goodness of eating McDonald's ice cream, for you, is so good, that it's worth it to try. 
  
If you now start to choose the `mcdonalds` every day, as a result of this insight, and if the transition model continues to be accurate, then over the next 100 days that you go to McDonald's, you end up with ice cream on 70 of those days, but without any on the other 30. Another way to look at it is that you have obtained 70(10) units of ice cream goodness. Over these 100 days, your average ice cream goodness comes out to `(70*10)/100` which is 7. This is what maximum expected utility *really* tells us: that if we repeat the choice in a consistent agent-environment-problem, our average utility will converge on the expected utility over time.  

But let's say your utility function is dynamic, and that, as you eat the same kind of ice cream over and over, you start to get a little burned out on it. One day, you decide to revisit your values and you find that your utility function needs updating. You no longer derive as much pleasure from McDonald's ice cream and ice cream from Wendy's is starting to sound even better. 

[The following is just one possible way of re-describing the values, but could simply lessen McDonald's to be something like 8 (-> 5.6) and wendys to be 7 still (-> 6.3)]:
mcdonalds = 0.7 * 8 = 5.6
wendys = 0.9 * 7 = 6.3

Note that even though we still have a slight preference for McDonalds in this scheme, the pragmatic meaning of the values cause wendys to rise as the more attractive choice. 

#### a. Maximum expected utility and ice cream [check Russell Norvig for earliest citation of MEU in this form]
#### b. Utility (one operationalization of values) is defined as part of the system's specification (subject to Godel's incompleteness as a set up to Nguyen on the inarcticulable): Where do rewards come from? They are part of the system's specification, just like the transition model, and therefore unassailable from within the system. This will set up Nguyen's defense of the inarticulable as well as wonder and awe later on. Also, perhaps the use of features and how that can go wrong: assigning large weights to overly gameable features such as GPA (resulting in high utility estimations but low rewards received due to optimizing for the grade rather than for the learning) or publication count (see Smaldino on the selection of bad science), though maybe rather than features, these are just really bad proxies to use partly because of the way they reduce uncertainty and seduce us with transparency a la Nguyen).
#### b. Exploration (another way values are operationalized) pulls agents to learn more, to avoid a feedback loop of self-fulfilling prophecy. (For our agent, the optimistic reward functions in a similar way to De Cruz's account of wonder/awe, by pulling the agent to perceive the call of the unknown and to have the motivation to answer it; but maybe don't develop it too much just yet, just plant a seed so that there's no massive confusion when going into more later on) (Consider including the bit from De Cruz about the caribou-hunting tribe's ritual)
  
### 3. Society is an AI
#### a. It's kind of laughable to worry about building an AI that has armageddon-levels of potential destructive force alongside divine potential for salvation. That's because WE'VE ALREADY BUILT SUCH A THING: SOCIETY [seinfeld pic with george "we're living in a soceity" but cross out society and replace with AI
#### b. Agent: humanity (which loses its distinction from the environment-problem as we previously saw)
  #### c. Extremely complex network of distributed computation: we're all Picard on the Enterprise (which is both horrifying and beautiful in equal measure, truly awful in the sense that it is full of awe [de cruz]).
#### d. The game (and its self-referential complications): humanity vs extinction. mutually exclusive outcomes, 
#### e. Surviving the game: We know our agent must have clarity around how the world works AND clarity around values as they relate to utility estimation/evaluation/exploration
#### e. My fear is that we are massively undercutting some of our most advanced technologies in our agent's value-clarifications systems (the collective die-off of the humanities). Link back to this in conclusion where I give a brief bit of biographical motivation: humanities BA has been so fundamentally important in my role as scientist. I truly think every undergraduate student, regardless of major, should end up with a blend of coursework that reflects both sciences and humanities: the classic liberal arts model! With a series of courses belonging to a particular area of study in which all of this other coursework may come to bear to produce a unique insight into the chosen area (regardless of humanities or sciences). 
#### f. What the humanities give us: encounters with the unmetricizable, the interpretation and interrogation of values, brushing against the inarticulable, the self-referential/cultural in such a way that reaches out toward the ground of the system's specification, the enhanced capacity for agential layering via story and narrative, a crucial technology of wonder/awe [de cruz] and therefore something like the battery of our values system's warp core, the unknown pulling us to explore. I think this is really the place to revel in De Cruz and Nguyen's points, even if they've been primed or alluded to elsewhere. 
  #### g. The humanities as abbey under attack, at the gate there are model-rich weapons at hand, unwilling to tolerate the wealth that such a clearly pointless thing holds, unaware that no power/weapon is strong enough to show them the borders of their values.
### 4. Conclusion
#### a. Possible tie-in with motivation and just a drop of biography? (See note on "e. My fear is that we are massively undercutting..."). Or maybe save this after the abbey under attack (since it functions as a good hook); could fit under "Make the point about non-binarism...".
#### b. Maybe introduce the abbey under attack metaphor here?
#### c. Make the point about nonbinarism in knowledge production and training. That a scholar of 18th century literature is, ultimately, contributing to our foundational decision-making model, a scientist of story using the tools that make sense. The story scientist might like to approach story with what can be formally articulated (a beautiful thing happening in the CA/DH/Comp Hum world that I owe so much to in terms of purpose and trajectory), BUT it's also important that another story scientist approach stories with mistrust of what can be measured, of finding where the inarticulable lay. Our tools do not change our discipline, but rather change the location of our various objects of study along an aritculable-inarticulable spectrum, all points equally critical. 
#### d. Perhaps make the point that we don't just need to save the "useful" humanities (e.g., phil of science/lang) but that we truly do need the full spectrum of things with inarticulable value, because it is precisely *by their inarticulable value that we know they are deeply valuable as enhancers of our sensitivity to the inarticulable/wonder/awe.
#### e. Wrap it up with a nice bow. I have no delusions about being a needed champion. Many humanists are daily making better, more in depth arguments for their existence. But my desire is that this particular framing might land with mny fellow modelers and metricizers, and especially their materially influential supporters. Spread the word. If you're a comp sci/tech/ai person with lots of money: YOU SHOULD BE THROWING MONDEY INTO THE EXPANSION OF THE HUMANITIES, GUIDED BY HOW THE HUMANITIES WANT TO DO THAT (not your necessarily metricized assumptions about what they should look like). Please, somebody send this to Bill Gates! We need your wonder about the destructive and creative capacities of AI, even if speculative, but we also need to support broader honing of this kinds of tools which is done in humanities. We need to spread our ability to step back and articulate the ends to which our species' tools are put to use.
  
Earlier in the year, I gave a presentation with this title at a local bioinformatics conference. The session was on AI and ethics. My basic point was that AI makes it clear that it is in humanity's best interests to support the kind of knowledge-production and skills training which happens to be done in a large-scale, efficient manner through the so-called humanities. The discourse around the broader values of humanities programs relative to their economic or scientific value, which by their nature tend to turn such broader values into measurable qualities, has always struck me as fraught. The bad takes are endless and it's honestly just kind of hard to watch remarkable scholars have to endlessly justify their existence. Part of the problem is that one's ability to appreciate the hard-to-articulate value of such skills depends on having gained exactly those skills. It's not surprising that there are people who see something like a scam in all this; certainly not something worth expending our limited resources on. *What are we getting out of all this navel-gazing? What have scholars of Greek myths, of classical Chinese thought, of games, etc. ever done that's put food on my table?*
    
Another tedious discursive faultline I find myself wishing (and failing) to avoid is that which is centered around so-called artificial intelligence. There's a funhouse mirror effect of the just-mentioned discourse present here: The salient question is how to evaluate the value of the spectrum of tools that people often mean by AI. Caricatures of the pro-AI (which sadly are what proliferate in dense social-information networks) might say that it's easy to evalute the value of such tools: there's metrics for that! When a metric gets bigger (or perhaps smaller), that means better—it's math! Or that the consistency of what such tools distill and remix with our expectations of what natural information manipulation looks like indicates, qualitatively and beyond what we can say in numbers, what it means to be better. Even those of us with a basic capacity for critical thinking can spot what's missing, what is necessary yet out of the boundaries of the system under discussion: *Yes, but what is the context in which such ends can be said to be valuable or not? What does it mean for my quality of life when that number is able to get bigger or smaller? Why should we assume it is good for a formal system to decompose and recompose the things we have made in such a way that feels like the products of humans?*
    
On a sid note, missing this line of questioning really ought to be inexcusable for those of us who have studied computing given the role played by Gödel's incompleteness theorems in our discipline's founding myths (see Petzold's The Annotated Turing for a riveting telling of this story). The parable Gödel gives us, achingly beautiful, is that anything can be unambigously distinguished, said to be true or false, within an unambiguously described system *except for the assumptions necessary for the articulation of the system itself.* We can't use claims endogenous to the system to prove the utility of the system. Instead, we have to upend the system, articulate its boundaries, expand beyond it, in order to evaluate the system; a recursive meta-perspectival loop. We can get pretty far saying things inside the system, but it's impossible to articulate, within the system, why the system has value. To articulate the system's value necessitates a change in scope that renders the system unable to resolve  There's something epistemilogically damning about this, but also liberating, I think. It makes me appreciate chaos, novelty, and humanity, but I'm getting ahead of myself.
    
One point that I made in my presentation is that AI gives us a profound articulation of why the hard-to-articulate skills, efficiently honed in humanities programs, are essential for societal decision-making. A foundational model of agency tells us that there are two equally essential ingredients in decision-making: knowledge about how things work and knowledge about the values of things. We tend to see the effects of increasing our knowledge about how things work in a very immediate, direct way in the form of evolving technologies. It requires a bit more sensitivity to see the effects of our knowledge about our values. The kinds of technologies we tend to see are an outgrowth of those values, but it's kind of hard to see this since we don't have the contrast provided by an awareness of all the other technologies we might have alternatively pursued. This also causes a very weird feedback loop: our values feed into the way things work. Our models (broadly defined) that are essential for our survival (e.g., our knowledge about how to create sufficient food) are always trying to estimate some ground truth about how things work. Yet, our values are always feeding into the actions we take, and those actions have an effect on that ground truth about how things work. Climate change is heavily influenced by our species' actions which in turn are heavily influenced by our species' values. When the climate changes, the truth about how things work changes (e.g., with respect to growing food). Culture is not just software running on separate hardware, but is actually modifying the hardware too!
    
Let's call all activities related to the interrogation, interpretation, and clarification of values the domain of evaluation. In highly complex environments with a lot of unknowns and lot of actions to consider, it's not enough for an agent to only evaluate things. Choosing to evaluate this thing over that thing is also an expression of values. In an environment where some locus of agency finds itself in an infinitely large environment of possible states and actions, an agent's ability to act reasonably also depends on how it explores. Exploration is something different from evaluation on one level, but they are intertwined given that the way in which we explore, how we evaluate which unknowns to make known, involves evaluating our options.

## Wonder, awe, and the inarticulable
        
I recently started reading Helen De Cruz's new book, *Wonderstruck*. I can't recommend it enough [include a link to it on amazon or whatever link helen has used to promote it]. I was also sent a wonderful article by C. Thi Nguyen [the limits of data] by a colleague (thanks Sharon!), which also led me to check out a podcast episode with Nguyen and Paul Smaldino from the Santa Fe Institute [link to the podcast episode]. I'm not surprised by my appreciation for Nguyen's thinking in these pieces. I have been slowly working my way through his phenomenal book, *Games*, for a while now and, as someone who thinks a lot about agency in the context of AI, I cannot recommend his deep dive into agency enough.

I want to use De Cruz and Nguyen as stand-ins for some of the ideas they express. Specifically, De Cruz's argument that wonder and awe are epistemic in nature, that they motivate us to accommodate the unknown by attempting to articulate what is currently inarticulable. At the same time, Nguyen has a lot to say in defense of what is not transparent, not clear, not articulable, and I think that fits in quite nicely here. Along this line, he also has a lot to say about why values are often lost when we mistake convenient, consistent proxies for them. There's a tie-in here with Gödel: fully and unambiguously articlating our values dooms them to only say things within the system, making our values incapable of evaluating the ground on which the system rests. Being able to unambiguously and completely define a problem is to be quite a long ways toward its solution. This is a lesson that much of computing's brief history has given us time and again, and it finds another beautiful articulation in AI (if you can hold the full game tree in memory, the algorithm for perfect play is beauitfully simple and elegant, and true for all deterministic games). Of course, the idea isn't unique to computer science. [Insert john dewey quote about stating problems and solving them here].

Here's a summary of relevant points:

-
-
-
-
## The beauty of AI
The thing that most bothers me about the discourse around AI is that its terms make it hard to see what is beautiful about AI. This is due to the fact that the discourse is always about what AI means for things external to AI, namely, us. This is unfortunate, but I don't mean to suggest that it's unnecessary. Given the myriad ways in which AI is being misguidedly used has a direct effect on people's lives and so the debate is necessary while also being unfortunate. Setting all that aside for the moment, I'd like to share a few ideas from AI that I happen to find beautiful.

### A model of optimal decision-making
[Note that this part is kind of the first big punch of the argument, that optimal decision-making requires the interrogratoin, interpretatoin, and clarification of values. May not want to bury it too far. Part of the effectiveness of this piece is the convenienve with which people can obsorb its message].
    
I find AI beautiful as attempts at formalizing notions of agency and meaning. In the case of agency, it gives us a precise way of talking about agency in general, agnostic of any particular scale or location of agency. It says that, agents are things that exist in some environment, which is has a particular way of working according to some transition model which may be of any variety or complexity (but the agent-environment distinction is basically superfluous in these formalizations). For this agent to work well, to achieve whatever its goals may be, to progress, it must decide on what actions to take, how to invoke its agency upon the environment. The state of the environment, really of the problem, changes and how it changes is in part bound up in the action taken by the agent (though, in highly complex problems, the state may change in some ways that are independent of the agent,; e.g., a self-driving car agent's problem state changes in response to where the agent moves the car, but also as a consequence of other environmental variables (which function simply as other agents)). Note that to define the environment is to also define the problem faced by an agent, just like Nguyen might say that designing a game is to design by invocation a particular range and timbre of agency, and so we might as well just be clear and dispense with the distinction: the agent exists within an environment-problem, and since the agent is connected by cyclical influence with the environment-problem, it can be viewed as a single system, which I also think is a quite beautiful metaphor of the notion that everything is connected.

This is a very broad way of stating what a transition model represents, in the form of a conditional probability:
[need to put into tex layout before publishing]: `new_state = f(old_state, action_taken)` or in a way that foregrounds the inherent uncertainty in most nontrivial environment-problems, `P(new_state | old_state, action_taken)`    [eq. 1]
The defined boundary between past and present, which is dictated by the specification of the problem-environment-agent, delineates a series of repeating agential junctures, the granularity at which the agent has the capacity to perceive the environment-problem. At each juncture, the agent must act (or not if the rules allow it, but in such a system, nonaction is functionally indistiguishable from action).

This probability distribution tells us how likely any possible state of the problem-environment will be as a consequence of two influences: the state of the past, and the action taken by the agent in the state of the past. Note that the statement of such a model does not suppose it must be specifiable in any particular, time-invariant or context-invariant way. All this statement gives us is a statement of how the present is the effect of the past and what was done in the past. In simplest illustrations, the transition model is often unchanging: rather than have `P(new_state | old_state, action_taken)_T=1, P(new_state | old_state, action_taken)_T=2, ... P(new_state | old_state, action_taken)_T=t, ...` (let's optimistically not put a cap on this), we can instead just have a time-invariant `P(new_state | old_state, action_taken)` without any possibility of the game mechanics themselves, changing.

Here's a beautiful model of optimal decision-making:  
optimal action = argmax_a{ SUM_s' P(s' | s, a) x U(s') }  
  
Let me try to explain exactly what this says with a simple example. 

### The ice cream problem

You, the agent, have one decision to make each day, which is the choice between two actions: attempt to obtain an ice cream from McDonald's and attempt to obtain an ice cream from Wendy's (I'm afraid this isn't the most creative illustration imaginable). Let's call the first action, `mcdonalds`, and the second action, `wendys`. All of your world boils down to three possible states: the state where you have obtained an ice cream from McDonald's, the state where you have obtained an ice cream from Wendy's, and the state where you were unable to obtain any ice cream at all as a result of the ice cream machine not working at your chosen fast food purveyor. Let's say that it is guaranteed that, in this world, if the ice cream machine is working, you *will* obtain an ice cream. Then we might describe each state as the following: 

Suppose that from past experience, you've noticed a pattern: the ice cream machine at McDonald's seems to be not working more often than the ice cream machine at Wendy's. If you are a sufficiently sophisticated agent, you might have some means of estimating and describing this pattern accurately (though some uncertainty will always be there, at least from our viewpoint since we don't know the state of every component in each ice cream machine that would be necessary for knowing with total certainty when each machine will be working or not). Perhaps you are able to formulate and build the following model of how your perspective-contingent world works: that the McDonald's ice cream machine works (at the time of your last calculation) 70% of the times that you go there, whlie the ice cream machine at Wendy's works 90% of the time. You might then derive the following model for how your world works:  
`P(today_state == mcdonalds_ice_cream | yesterdays_state, action == mcdonalds) = 0.7`  
`P(today_state == wendys_ice_cream | yesterdays_state, action == wendys) = 0.9`  
and so we can also say  
`P(todays_state == no_ice_cream | yesterdays_state, action == mcdonalds) = 0.3`  
`P(todays_state == no_ice_cream | yesterdays_state, action == wendys) = 0.1`  

Since, as far as you know, there is no discernible relationship between yesterday's state and today's (though such a relationship migh exist outside of this contingent perspective), we can simplify this to just  
`P(mcdonalds_ice_cream | mcdonalds) = 0.7`  
`P(no_ice_cream | mcdonalds) = 0.3`
`P(wendys_ice_cream | mcdonalds) = 0.0`  

`P(wendys_ice_cream | wendys) = 0.9`  
`P(no_ice_cream | wendys) = 0.1`  
`P(mcdonalds_ice_cream | wendys) = 0.0`  

It's tempting to assume that optimal decision-making ought to require nothing else, that knowing how the world works, how to best describe the future, is sufficient for acting rationally. AI's success is predicated on this being untrue. Instead, another equally ingredient, equally critical, is needed: the evaluation of possible futures, expressing the agent's desires for different realities, states of the problem-environment, in the form of a utility function. In other words, the agent-environment-problem system cannot provide us with any notion of correct action unless we determine how much we value the three possible states. To act optimally necessitates having clarity around my values. 

Suppose then, that you interrogate, reflect on, or generally clarify your values and come to the following realization on this particular day, prior to acting: you really do not like going without an ice cream and would much prefer to have an ice cream from either McDonald's or Wendy's. But on further reflection, you will realize that, if you had to pick one over the other, you have a slightly higher preference for McDonald's. If we're going to use this model of optimal decision-making, we will need to fill in the utility function U(s) for each possible state. Here's one possibility:  
`U(mcdonalds_ice_cream) = 10`  
`U(wendys_ice_cream) = 7`  
`U(no_ice_cream) = 0`  
  
Only now do we have the required ingredients for making a reasonable choice about which action to take, since we can now fill in all the blanks in eq. 1. The $arg max$ bit says we need to loop through each action, calculate the expected utility of taking an action, and returning the action which results in the maximum expected utility. Argmax is kind of like max except that, instead of returning the numerical value, it returns the variable associated with that numerical value, here, actions. 

`argmax{expected_utility(mcdonalds), expected_utility(wendys)`  
where  
`expected_utility(mcdonalds) = [P(mcdonalds_ice_cream | mcdonalds) * U(mcdonalds_ice_cream)] + [P(no_ice_cream | mcdonalds) * U(no_ice_cream)] + [P(wendys_ice_cream | mcdonalds) * U(wendys_ice_cream)]`.  
Filling in the blanks, we get that  
`expected_utility(mcdonalds) = (0.7 * 10) + (0.3 * 0) + (0.0 * 7) = 7`  

One way of interpreting what the 7 means here, is that it is the proportion of utility we can expect to receive on average. But more on that in a bit. Now let's see how the expected utility of the `mcdonalds` action compares with that of `wendys`:  
`expected_utility(wendys) = [P(wendys_ice_cream | wendys) * U(wendys_ice_cream)] + [P(no_ice_cream | wendys) * U(no_ice_cream)] + [P(mcdonalds_ice_cream | wendys) * U(mcdonalds_ice_cream)]`  
`                         = (0.9 * 7) + (0.1 * 0) + (0.0 * 10)` 
`                         = 6.3`  

Therefore, `argmax{expected_utility(mcdonalds), expected_utility(wendys)} == mcdonalds`. This tells us that, given the semantics of our values, the relationships between their numerical representations, the optimal action to take is to go to McDonald's today, despite that it carries a greater risk of winding up without ice cream. The goodness of eating McDonald's ice cream, for you, is so good, that it's worth it to try. 
  
If you now start to choose the `mcdonalds` every day, as a result of this insight, and if the transition model continues to be accurate, then over the next 100 days that you go to McDonald's, you end up with ice cream on 70 of those days, but without any on the other 30. Another way to look at it is that you have obtained 70(10) units of ice cream goodness. Over these 100 days, your average ice cream goodness comes out to `(70*10)/100` which is 7. This is what maximum expected utility *really* tells us: that if we repeat the choice in a consistent agent-environment-problem, our average utility will converge on the expected utility over time.  

But let's say your utility function is dynamic, and that, as you eat the same kind of ice cream over and over, you start to get a little burned out on it. One day, you decide to revisit your values and you find that your utility function needs updating. You no longer derive as much pleasure from McDonald's ice cream and ice cream from Wendy's is starting to sound even better. 

mcdonalds = 0.7 * 20 = 14
wendys = 0.9 * 16 = 14.4

Note that even though we still have a slight preference for McDonalds in this scheme, the semantics of these values cause wendys to rise as the more attractive choice. 


## Society as an AI
[* add that quote from Peli Grietzer about economic systems being algorithms with misaligned values *]

## An example of all the disparate things that come into my particular scientific trajectory (or does this just sound really self-centered actually?)

A simple example: finding a new level of pedagogical effectiveness in explaining [Actually, maybe just make this integrated into my explanation of optimal decision-making--showing but not telling.    ]

## Humanities as societal dreaming, therapy, 
[point from Why We Sleep about the important role played by dreams]

[point from ACT stuff about the therapeutic value of letting our values guide our lives; almost an independent discovery of MEU]

