# Pair Programming

> Pair programming is the practice where two developers work together on the same coding problem, sharing terminals on the same computer.

### Types

#### Driver/Navigator:

Driver writes code, Navigator provides guidance and reviews. The driver focuses on the implementation details, while the navigator focuses on reviewing, strategize, and providing feedback. In this approach, which many development teams prefer, one programmer handles the mechanical and tactical elements, and the other is in control of the strategic or architectural elements. This style works well for a novice paired with an expert programmer. In fact, it works best with that combination, where the novice is the driver and the expert acts as the navigator.

The navigator can take anything from a reserved approach to a tactical hands-on role. The skill level of the driver should determine the navigator's involvement. In extreme cases, for example, the expert navigator may lead a novice driver through each step to b

#### Ping-Pong Style :

It is a specific approach to pair programming that promotes a test-driven development (TDD) mindset and a focus on small, incremental steps.\
Person 1 writes a failing test.\
Person 2 makes it pass.\
Person 2 writes a failing test.\
Person 1 makes it pass

#### Strong-Style:

For an idea to go from your head into the computer, it must go through someone else's hands". In this style, the navigator is usually the person much more experienced with the setup or task at hand, while the driver is a novice (with the language, the tool, the codebase, ...). The experienced person mostly stays in the navigator role and guides the novice.\\

#### The Unstructured Pair Style:

The unstructured style is more of a freestyle way to work on something together, like learning a new language or concept. The benefit of the unstructured style is the team building and creative solutions that can come from two people hacking away and figuring things out Both programmers collectively share the responsibility of understanding, implementing, and reviewing the code, making decisions, and addressing issues together. There are no predefined or formal roles such as driver or navigator. Both programmers actively collaborate and work together without distinct responsibilities.

#### Backset Navigator Style :

The backseat navigator knows what he wants to do, but doesn’t always know how to get there. In practice, you may find yourself dealing with a backseat navigator in two ways: You both can write code, or you might be pairing with a developer who's looking over your shoulder and telling you what to type. If it's one-on-one pairing and you're a veteran programmer, a backseat navigator can actually help you solve problems.

#### Tour Guide Style

This style of pairing is used for two developers with different skill sets, such as junior and senior developers. The lead is responsible for doing most of the coding and is usually paired with someone who needs guidance, has specific knowledge that can be used, or just wants to see more. The junior dev focuses on improving their skills by asking questions and learning from what’s happening around them.

Others: Promiscuous Pairing Partial Pairing

### Why

* Shared Code Ownership
* Constant code review
* Knowledge sharing and mentoring

When your team consists of solo engineers, you end up with knowledge silos. Parts of the codebase are owned by specific individuals, and no one else knows how those modules work; in fact, other people on the team are afraid to make any changes. The owner becomes a bottleneck for the team, and new features can only be developed if that person is available. If that person becomes unavailable, the progress grinds to a halt
