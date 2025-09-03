# A Philosophy of Software Design 
## John Ousterhout
### This is a few notes and quotes from my readings.


- The author and I share the same day of birth. Neat.

## Preface
- "The most fundemental problem in computer science is problem decomposition: how to take a complex problem and  divide it up into pieces that can be solved independently." 
- "The overall goal is to reduce complexity; this is more important than any particular principle or idea you read here."


## Chapter 1: Introduction 
- "Complexity increases inevitably over the life of any program. The larger the program, and the more people that work on it, the more difficult it is to manage complexity."
- The waterfall method can cause explosions in complexity since many groups of people can work on different points of the work. Ex. The designers will work solely on the design portion until they are finished and the work is passed off to developers and the designers work on a new project. 
- Because of these issues most software development now a days use incremental approaches such as agile development. 
- "When you read other people's code, think about whether it conforms to the concepts discussed here and how that related to the complexity of the code. It's easier to bsee design problems in someone else's code than your own." 
- Red flags: Signs a piece of code is probably more complicated than it needs to be


## Chapter 4: Modules should be deep
- One important technique for managing software complexity is to design systems so that developers only need to face a small amount of the overall complexity at a time. 
- A software system in modular design is composed of a collection of modules that are relatively independent. Modules can be classes, subsystems, or services. 
- Interfaces contain two kinds of information: formal and informal. The formal parts are specified explicitly in the code, and some of these can be checked for correctness by the programming language. The formal interface for a method is its signature which has the names and types of its parameters and the type of its return value along with information about exceptions that can be thrown by the method. 
- Each interface also includes informal elements, such as high-level behavior like the fact that a function deletes the file named by one of its arguments. 
- "In general, if a developer needs to know a piece of information in order to use a module, then that information is part of the module's interface. The informal aspects of an interface can only be described using comments"
- Abstractions are closely related to the idea of modular design where abstractions are a simplified view of an entity which omits unimportant details. 
- Abstraction is something as simple as a microwave. The microwave itself converts AC to microwave radiation to distribute that radiation throughout the cooking cavity. The users see a simple abstraction to press buttons to control timing and intensity of the microwaves. 
- The best modules are those that provide powerful functionality yet have simple interfaces.  
- RED FLAG: SHALLOW MODULE. A shallow module is one whose interface is complicated relative to the functionality it provides. Shallow modules don't help much in the battle against complexity, because the benefit they provide (not having to learn about how they work internally) is negated by the cost of learning and using their interfaces. Small modules tend to be shallow.
- Don't have classitis where classess are good, so more classes are better. Classitis may result in classes that are individually simple, but increases the complexity of the overall system. Small classes don't contribute much functionality, so there have to be alot of them each with an interface. Small classes also result in a verbose programming style due to boilerplate. 

## Chapter 12: Why write comments? The four excuses
- In code documentation plays a crucial role in software design. Comment are essential to help developers understand a system and work efficiently, but the role of comments goes beyond this. 
- "Finally, the process of writing comments if done correctly will actually improve a system's design."
- Excuses that might arise
    - "Good code is self-documenting"
    - "I don't have time to write comments."
    - "Comments get out of date and become misleading"
    - "The comments I have seen are all worthless; why bother?"
- "If users must read the code of a method in order to use it, then there is no abstraction: all of the complexity of the method is exposed."


