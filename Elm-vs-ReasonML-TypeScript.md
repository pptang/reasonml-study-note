# Comparison
Good stackoverflow answer:
- https://stackoverflow.com/a/51027309

## Mutability
**Elm** is a purely functional language, which is great in theory but challenging in practice since the surrounding world cares little about Elm's quest for purity. Elm's preferred solution to this, I think, is to isolate the impurity by writing the offending code in JavaScript instead, and to then access it in Elm through either web components or ports. This means you might have to maintain significant amounts of code in a separate and very unsafe language, quite a bit of boilerplate to connect them, as well as having to figure out how to fit the round things though the square holes of ports and such in the first place.

**Reason** on the other hand is... pragmatic, as I like to call it. You sacrifice some safety, ideals and long-term benefits for increased productivity and short-term benefits. Isolating impurity is still good practice in Reason, but you're inevitably going to take short-cuts just to get things done, and that is going to bite you later.


## Another answer

But as it is I think the biggest trade-off is between ReasonML's sound and flexible type system, and TypeScript's ability to easily "sneak" comprehensive static checks into an existing JavaScript code base.

**TypeScript**'s type system is explicitly designed to not be sound, and so while it will give you a hand most of the time, it won't be able to give you many guarantees. You really can't fully trust the type system to have your back, which is one the biggest advantages of having a proper static type system.

**TypeScript** is also limited by its decision of avoiding runtime type information, which is necessary for features such as pattern matching and a major benefit of working with typed data in ReasonML.

ReasonML on the other hand requires that the boundary between itself and existing JavaScript code is explicitly defined. Types can to some extent be inferred, but they must still be determined at compile-time. This makes JavaScript interoperation more laborious, especially if the boundary gradually moves as an existing JavaScript code base is converted. It's also not always obvious how to type some of the weird stuff that goes on In JavaScript, but it's usually possible, and hopefully just temporary until everything has been converted to ReasonML anyway :)