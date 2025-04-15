# Code Complete

## Part I. Laying the Foundation

### Chapter 1. Welcome to Software Construction

This chapter introduces the concept of **software construction**, defining it as the central, hands-on part of software development, analogous to the building phase in physical construction.

**Key points covered:**

1.  **Definition:** Software construction isn't just "coding." While coding and debugging are central, it also encompasses activities like **detailed design, unit testing, integration, integration testing, construction planning,** and more. It sits between broader activities like requirements/architecture (which precede it) and system testing/maintenance (which follow it).
2.  **Distinction from other activities:** It's distinct from requirements definition, high-level architecture, system testing, and project management, although it interacts with them.
3.  **Importance:** Construction is crucial because:
    *   It consumes a significant portion of project time (30-80%).
    *   It's the pivotal activity around which others revolve.
    *   Improving construction practices can dramatically boost individual programmer productivity (citing studies showing 10-20x variations).
    *   The source code produced during construction is often the most accurate (sometimes the *only* accurate) description of the software.
    *   It's the one activity guaranteed to occur on *every* project, regardless of how rushed or poorly planned it is.
4.  **Book's Focus:** The book *Code Complete* specifically concentrates on these construction activities, aiming to improve the quality of the software produced and the efficiency of the programmer.
5.  **How to Read:** The book can be read cover-to-cover or used as a reference by looking up specific topics.

In essence, the chapter establishes that **software construction is the core programming activity**, highlights its critical role in software quality and project success, defines its scope, and sets the stage for the rest of the book which delves into the techniques for doing it well.

### Chapter 2. Metaphors for a Richer Understanding of Software Development

This chapter explores the power of using **metaphors** to understand the complex process of software development. It argues that metaphors, while not precise algorithms, act as valuable **heuristics** – mental tools or "searchlights" that help developers conceptualize problems, communicate ideas, and choose appropriate approaches.

**Key ideas discussed:**

1.  **Importance of Metaphors:** Just as metaphors have driven scientific breakthroughs (e.g., Kekulé's benzene ring, wave theory of light), they help us grasp abstract software concepts by relating them to more familiar activities. They shape how we think about and approach development.
2.  **Metaphors as Heuristics:** Metaphors don't provide step-by-step instructions (algorithms) but offer ways to *look for* solutions and understand the landscape. They guide thinking rather than dictating actions.
3.  **Common Software Metaphors & Critiques:**
    *   **Writing Code:** Compares development to writing a letter or novel. Useful for emphasizing readability but too simplistic for large team projects and doesn't capture the iterative/maintenance aspects well. Brooks's "plan to throw one away" is often too costly.
    *   **Growing/Farming Software:** Suggests incremental development like planting seeds. While the *incremental technique* is good, the metaphor itself is weak, implying a lack of direct control.
    *   **Accretion (Oyster Farming):** A better metaphor for incremental development, comparing it to an oyster gradually adding layers to form a pearl. This effectively visualizes starting small (skeleton) and adding functionality piece by piece.
    *   **Software Construction:** A very powerful and widely applicable metaphor. It parallels building physical structures, highlighting the need for planning, architecture, foundations, different stages, varying levels of formality based on project size/complexity (doghouse vs. skyscraper), using standard components (libraries), inspections (reviews), and the cost of structural changes.
    *   **The Intellectual Toolbox:** Views programming techniques, methods, and best practices as tools. This meta-metaphor emphasizes that skilled developers have many tools and know when to apply the right one for the job, rather than rigidly adhering to a single methodology.
4.  **Using Metaphors:** They are not mutually exclusive. Developers should use the combination of metaphors that best aids their understanding and communication within their team. Extending metaphors provides insight, but overextending them can be misleading.

In essence, the chapter advocates for consciously using and understanding various metaphors, especially **software construction** and **accretion**, to gain deeper insights into the software development process, leading to better planning, design, and execution.

### Chapter 3. Measure Twice, Cut Once: Upstream Prerequisites

This chapter emphasizes the critical importance of **completing necessary upstream work (prerequisites) before starting software construction (coding)**. It uses the analogy "Measure twice, cut once" to highlight that proper preparation avoids costly rework later.

**Key concepts covered:**

1.  **Importance of Prerequisites:**
    *   **Quality:** High-quality software requires attention to quality throughout the process, starting early with problem definition, requirements, and architecture. Fixing errors found during these early stages is 10-100 times cheaper than fixing them after construction begins.
    *   **Risk Reduction:** The main goal of prerequisites is to reduce project risks, particularly those related to poor requirements and planning.
    *   **Avoiding Waste:** Prevents building the wrong product or building the right product the wrong way.
    *   **Education:** Programmers often need to educate managers (suffering from "Why Isn't Sam Coding Anything?" syndrome) on the value of this preparatory work using logic, analogies (house building, food chain), and data (cost of fixing defects).

2.  **Tailoring Prerequisites:**
    *   The *type* of software project (e.g., informal business system vs. formal life-critical system) dictates the *level* of formality and completeness needed for prerequisites.
    *   **Iterative vs. Sequential:** Iterative approaches (like Agile) interleave prerequisites with construction more than sequential (waterfall-like) approaches. However, iterative methods *do not eliminate* the need for prerequisites; they just handle them differently, often reducing the *impact* of inadequate prerequisites but still benefiting significantly from good ones. Skipping prerequisites is costly regardless of the overall approach.

3.  **Specific Prerequisites (and how to check them):**
    *   **Problem Definition:** A clear, user-language statement of the *problem* to be solved, *not* the solution. Ensures the right problem is being addressed.
    *   **Requirements:** A detailed description of *what* the system should do (functional and non-functional qualities).
        *   Crucial for ensuring the user drives functionality and minimizing expensive late-stage changes.
        *   Requirements *will* change (25% is typical); plans must accommodate this via change control, iterative development, cost awareness, and checking the business case.
        *   Provides a checklist to assess requirements quality (clarity, completeness, testability, non-conflicting, etc.).
    *   **Architecture (High-Level Design):** The overall structure of the system.
        *   Determines conceptual integrity, makes construction easier, and partitions work. Poor architecture is hard to fix later.
        *   A good architecture addresses program organization, major classes, data design, business rules, UI design, resource management, security, performance, scalability, error handling, buy-vs-build decisions, and change strategy.
        *   Provides a checklist to assess architectural quality (clarity, justification, completeness, addressing risks, conceptual integrity, etc.).

4.  **Time Allocation:** Generally, 10-20% of effort and 20-30% of the schedule should be dedicated to requirements, architecture, and planning *before* detailed construction/design begins, though this varies by project. Unstable requirements or architecture may necessitate treating them as separate, preliminary projects.

In essence, the chapter argues that **investing time in understanding the problem, defining requirements, and creating a solid architecture *before* coding begins is essential for project success, reducing costs, improving quality, and minimizing risks**, regardless of whether the overall development methodology is more sequential or iterative.

### Chapter 4. Key Construction Decisions

This chapter focuses on the crucial decisions that need to be made specifically for the construction phase, *after* the broader upstream prerequisites (like requirements and architecture) are in place. These are choices often made by programmers and technical leads.

**Key decisions covered:**

1.  **Choice of Programming Language:**
    *   This significantly impacts productivity (familiarity and language level matter – higher-level languages are generally more productive) and code quality.
    *   The language influences how programmers think and solve problems (the Sapir-Whorf hypothesis applied to programming). Programmers should aim to "program *into*" a language (expressing desired concepts using the language's features, even compensating for weaknesses) rather than just "programming *in*" it (limiting thoughts to what the language easily supports).

2.  **Programming Conventions:**
    *   Establishing clear conventions for naming, formatting, commenting, etc., *before* coding begins is vital for consistency, readability, and maintaining conceptual integrity from the architecture down to the code.
    *   Conventions reduce arbitrary variations, freeing up mental energy to focus on essential complexity. They are very difficult to retrofit later.

3.  **Location on the Technology Wave:**
    *   Recognize whether you're working with early-wave technology (less mature, buggy tools, poor documentation, requires workarounds) or late-wave technology (mature, stable tools, good support).
    *   This awareness helps set realistic expectations about how much time will be spent writing core functionality versus dealing with tool/language issues. Adapting practices (like "programming into the language") is especially important in early-wave scenarios.

4.  **Selection of Major Construction Practices:**
    *   Projects need to consciously choose *which* specific construction practices they will employ, as not all practices fit every project.
    *   Key areas for decision include:
        *   **Coding:** Approach to detailed design (up-front vs. at keyboard), specific coding standards implied by architecture (error handling, security, etc.).
        *   **Teamwork:** Integration procedures, use of pair programming vs. solo development.
        *   **Quality Assurance:** Use of test-first development, unit testing, debugging practices, code reviews/inspections.
        *   **Tools:** Selection of revision control, compiler/language version, frameworks, editors, debuggers, etc.

In essence, the chapter stresses that before diving into coding, teams must make deliberate choices about their primary language, agree on consistent coding conventions, understand the maturity of their technology stack, and select a coherent set of construction practices to guide their work effectively.

## Part II. Creating High-Quality Code

### Chapter 5. Design in Construction

This chapter delves into the crucial activity of **software design**, emphasizing its role *during* the construction phase. Design bridges the gap between requirements and coding, and while it can be a distinct phase, much design work often occurs, formally or informally, during construction, especially on smaller projects or when refining high-level architecture.

**Key concepts covered:**

1.  **Design Challenges:** Design is presented as inherently challenging:
    *   It's a **"wicked problem"** (needing partial solution to be fully defined).
    *   It's a **"sloppy"** process involving trial-and-error, mistakes, and uncertainty about when it's "good enough."
    *   It involves making **tradeoffs** between competing goals (like speed vs. size).
    *   It's **nondeterministic** (multiple valid solutions exist) and **heuristic** (relying on rules of thumb, not guaranteed algorithms).
    *   It's **emergent**, evolving through iteration and refinement.

2.  **Key Design Concepts:**
    *   **Managing Complexity:** This is identified as **Software's Primary Technical Imperative**. Good design aims to minimize both essential (inherent) and accidental (self-inflicted) complexity, making programs intellectually manageable.
    *   **Desirable Characteristics:** A good design strives for minimal complexity, ease of maintenance, loose coupling, extensibility, reusability, high fan-in, low fan-out, portability, leanness, stratification, and use of standard techniques.
    *   **Levels of Design:** Design occurs at multiple levels: the entire system, subsystems/packages (crucial for managing complexity via controlled communication), classes, routines, and finally, the internal logic of routines.

3.  **Design Building Blocks (Heuristics):** Skillful design relies on heuristics. Major ones include:
    *   **Finding Objects:** Identifying real-world and synthetic objects and their relationships.
    *   **Abstraction:** Focusing on essential qualities while ignoring irrelevant details.
    *   **Encapsulation:** Hiding the internal details of an object, exposing only a defined interface.
    *   **Information Hiding:** A core principle involving hiding design decisions ("secrets") within a module (class, routine) to isolate complexity and sources of change. Asking "What should I hide?" is a powerful design tool.
    *   **Identifying Areas Likely to Change:** Isolating potential volatility (business rules, hardware dependencies, I/O, etc.) to minimize the impact of future changes.
    *   **Loose Coupling:** Minimizing dependencies between modules (classes/routines) for better flexibility and maintainability. Avoid semantic coupling.
    *   **Using Design Patterns:** Leveraging proven, named solutions (like Factory, Singleton, Observer) to solve common problems, reduce complexity and errors, and improve communication.

4.  **Design Practices:** Effective ways to conduct design work include:
    *   **Iteration:** Trying multiple approaches, as the first idea is rarely the best.
    *   **Divide and Conquer:** Breaking down complex problems.
    *   **Top-Down and Bottom-Up:** Using both decomposition and composition strategies.
    *   **Prototyping:** Writing minimal, throwaway code to explore risky or unclear areas.
    *   **Collaboration:** Working with others (informally, pair programming, reviews) to generate ideas and find flaws.
    *   **Judging "How Much Design":** Balancing the need for design against analysis paralysis, tailoring the amount and formality based on project factors (size, criticality, team experience, etc.). Avoid the extremes of "design everything" or "design nothing." Aim for "Enough Design Up Front (ENUF)".
    *   **Capturing Design:** Using practical methods like comments, Wikis, email summaries, digital photos of whiteboards, CRC cards, or UML diagrams, rather than insisting on overly formal documentation.

5.  **Methodology:** The chapter advocates for a pragmatic, flexible approach, warning against dogmatic adherence to any single methodology ("Big Design Up Front" vs. "No Design Up Front"). Design is presented as a practical, heuristic, and iterative activity focused on achieving simplicity and managing complexity.

### Chapter 6. Working Classes

This chapter focuses on the design and implementation of **classes**, which are presented as the primary tool for managing complexity in modern programming. It emphasizes creating high-quality classes by building upon the concept of **Abstract Data Types (ADTs)** and focusing on well-designed interfaces and implementations.

**Key concepts covered:**

1.  **Class Foundations (ADTs):**
    *   An ADT is a collection of data and the operations on that data. ADTs allow programmers to work with higher-level, real-world entities (like `Employee` or `CoolingSystem`) instead of low-level implementation details (like linked list nodes or raw data structures).
    *   Benefits of ADTs (and thus classes) include hiding implementation details, localizing changes, creating more informative interfaces, improving performance isolation, making code more obviously correct and self-documenting, avoiding excessive data passing, and working at a higher level of abstraction.
    *   Classes in object-oriented languages are essentially ADTs plus inheritance and polymorphism.

2.  **Good Class Interfaces:** Creating a good interface is paramount. Key principles include:
    *   **Good Abstraction:** The interface should represent a single, consistent abstraction (like `Employee`, not `EmployeeAndListContainer`). All public routines should support this abstraction. Services should often come in pairs (e.g., `Enable`/`Disable`). Unrelated information should be moved to other classes. Interfaces should be primarily programmatic, not semantic (relying on hidden rules).
    *   **Good Encapsulation:** Enforce the abstraction by preventing access to implementation details. Minimize accessibility (use `private` over `public` or `protected`). *Never* expose member data publicly; use accessor routines instead. Hide implementation details (e.g., using the pimpl idiom in C++). Don't make assumptions about users. Avoid friend classes. Favor read-time convenience over write-time convenience. Be wary of semantic violations where client code depends on implementation knowledge. Watch for overly tight coupling.

3.  **Design and Implementation Issues:**
    *   **Containment ("has a"):** This is the preferred way to implement "has a" relationships (e.g., `Employee` "has a" `Name`). It's generally simpler and safer than inheritance. Be critical of classes with too many data members (more than ~7).
    *   **Inheritance ("is a"):** Use *only* for true "is a" relationships (Liskov Substitution Principle). Design/document for inheritance or prohibit it. Move common elements high in the hierarchy. Avoid deep inheritance trees (max 2-3 levels is better than 6+). Prefer polymorphism over explicit type checking (e.g., `switch` statements). Make base class data private. Use multiple inheritance very cautiously (mainly for mixins). Inheritance increases complexity, so use it judiciously.
    *   **Member Functions/Data:** Keep the number of routines per class small. Minimize calls to other classes (fan-out). Minimize indirect calls (Law of Demeter).
    *   **Constructors:** Initialize all member data. Use private constructors to enforce Singletons. Prefer deep copies over shallow copies unless performance dictates otherwise.

4.  **Reasons to Create a Class:** Classes serve many purposes beyond just modeling real-world objects:
    *   Model real-world or abstract objects.
    *   Reduce and isolate complexity.
    *   Hide implementation details and limit the effect of changes.
    *   Hide global data.
    *   Streamline parameter passing.
    *   Create central points of control.
    *   Facilitate code reuse and plan for program families.
    *   Package related operations.
    *   Accomplish specific refactorings.
    *   Avoid "god classes," irrelevant classes (data only), and verb-named classes (behavior only).

5.  **Language-Specific Issues:** Details like constructor/destructor behavior, overriding rules, and memory management vary significantly between languages (C++, Java, VB.NET). Programmers need to understand these nuances.

6.  **Beyond Classes (Packages):** Higher-level groupings like packages (in Java or Ada, or simulated via conventions) are needed to manage complexity by grouping related classes and controlling their interactions.

In essence, the chapter provides a comprehensive guide to creating effective classes by focusing on strong abstractions, strict encapsulation, careful use of inheritance and containment, and understanding the many valid reasons for class creation beyond simple real-world modeling. High-quality classes are presented as the fundamental building blocks for managing complexity in software construction.

### Chapter 7. High-Quality Routines

This chapter focuses on the design and implementation of individual **routines** (procedures, functions, methods), arguing that well-designed routines are crucial for program quality, readability, and maintainability. It moves from the class level (Chapter 6) down to the level of individual code units.

**Key concepts covered:**

1.  **Valid Reasons to Create Routines:** Beyond just avoiding duplicate code, routines should be created to:
    *   **Reduce complexity:** The single most important reason. Hide details so you can focus.
    *   **Introduce abstractions:** A good name summarizes purpose and improves readability.
    *   **Avoid duplication:** Saves space, eases modification, improves reliability.
    *   **Support subclassing:** Short, well-factored routines are easier to override correctly.
    *   **Hide sequences:** Isolate the order of operations.
    *   **Hide pointer operations:** Make code safer and easier to read.
    *   **Improve portability:** Isolate non-standard or platform-dependent code.
    *   **Simplify complex boolean tests:** Improve readability by putting tests into well-named functions.
    *   **Improve performance:** Centralize code for easier optimization or rewriting.
    *   **Isolate complexity and limit effects of changes.**
    *   **Hide implementation details and global data.**
    *   **Make central points of control.**
    *   Even very simple operations often benefit from being put into their own routines for clarity and future flexibility.

2.  **Design at the Routine Level (Cohesion):**
    *   Focuses on **cohesion**: how closely related the operations within a routine are.
    *   **Functional cohesion** (doing one and only one thing) is the strongest and most desirable type.
    *   Other types (sequential, communicational, temporal) are acceptable if used carefully, often by having the routine orchestrate calls to other, more focused routines.
    *   Procedural, logical (except event handlers), and coincidental cohesion are generally unacceptable and indicate poor design.

3.  **Good Routine Names:**
    *   A good name clearly describes *everything* the routine does (including side effects).
    *   Avoid vague verbs (like `Handle`, `Process`).
    *   Don't differentiate solely by number (`Part1`, `Part2`).
    *   Make names as long as necessary for clarity.
    *   **Functions:** Name based on the return value (e.g., `GetCustomerId()`).
    *   **Procedures:** Use a strong verb-object pair (e.g., `PrintDocument()`). In OO languages, the object often implies the object part (e.g., `document.Print()`).
    *   Use precise opposites (add/remove, start/stop).
    *   Establish conventions for common operations (like getting an ID).

4.  **Routine Length:**
    *   Research is mixed, but routines up to about 100-200 lines seem acceptable and no more error-prone than shorter ones.
    *   Let factors like cohesion, nesting depth, complexity, and clarity dictate length, not arbitrary limits. Be cautious above 200 lines. Many OO routines (accessors) will naturally be very short.

5.  **Using Routine Parameters:** Interfaces are error-prone. Minimize issues by:
    *   Ordering parameters consistently (e.g., input -> modify -> output).
    *   Using all parameters passed in.
    *   Putting status/error parameters last.
    *   *Not* using parameters as working variables (use local variables).
    *   Documenting assumptions (units, ranges, meanings, etc.) or using assertions.
    *   Limiting parameters to about 7 (use structured data/objects to group related parameters).
    *   Considering naming conventions for parameter roles (input/modify/output).
    *   Passing what the routine needs to maintain its abstraction (sometimes specific elements, sometimes the whole object).
    *   Using named parameters (if available) for clarity, especially with long lists or identical types.
    *   Ensuring actual parameters match formal parameter types.

6.  **Functions vs. Procedures:**
    *   Use a **function** only if its primary purpose is to return the value indicated by its name.
    *   Use a **procedure** otherwise (even if it returns a status code). Returning status via an output parameter often makes code clearer than using the function's return value for status.
    *   Ensure functions return a valid value under all possible paths. Don't return pointers/references to local data.

7.  **Macros and Inline Routines:**
    *   Use preprocessor macros for routines only as a last resort; they are risky and obscure code. If used, parenthesize carefully, use curly braces for multiple statements, and consider naming them like routines if they might be replaced by one.
    *   Use `inline` routines (like in C++) sparingly. They can violate encapsulation and potentially increase code size. Measure performance benefits before using them extensively for optimization.

In essence, this chapter emphasizes that routines are fundamental tools for managing complexity. High-quality routines are characterized by strong functional cohesion, clear descriptive names, appropriate length determined by logic, well-managed parameter lists, and careful consideration of their role as either functions or procedures.

### Chapter 8. Defensive Programming

This chapter advocates for **defensive programming**: the practice of anticipating problems and writing code that functions correctly, or at least fails safely, even when encountering unexpected conditions or invalid inputs. It's like defensive driving—protecting yourself even if problems originate elsewhere.

**Key concepts covered:**

1.  **Protecting from Invalid Inputs:**
    *   Production software should *not* follow "garbage in, garbage out." Instead, aim for "garbage in, nothing out," "garbage in, error message out," or "no garbage allowed in."
    *   Check *all* data from external sources (users, files, network) for validity, range, and potential security threats (buffer overflows, SQL injection, etc.).
    *   Check *all* routine input parameters (data from other internal routines) for validity, as appropriate.
    *   Decide *how* to handle bad inputs consistently (an architectural decision).

2.  **Assertions:**
    *   Assertions are checks used during development to verify assumptions about the code's state (e.g., `denominator != 0`). They assert conditions that should *never* be false; if they are false, it indicates a bug.
    *   Use them to document assumptions (like preconditions and postconditions in Design by Contract) and flush out errors early.
    *   They are typically compiled out of production code for performance reasons.
    *   Avoid putting executable code directly inside assertions (use temporary variables).
    *   For critical systems, consider asserting *and* handling the error in production code for maximum safety.
    *   If your language lacks built-in assertions, create your own.

3.  **Error-Handling Techniques:** When expected errors (not "never occur" conditions) happen, choose a strategy:
    *   Return a neutral value (0, empty string, default color).
    *   Substitute the next valid data (skip corrupted record).
    *   Return the previous value (last known temperature).
    *   Substitute the closest legal value (0 for negative speed).
    *   Log a warning message.
    *   Return an error code/status (to be handled higher up).
    *   Call a central error-processing routine/object.
    *   Display a user-friendly error message (careful not to reveal too much).
    *   Shut down (for safety-critical applications).
    *   Handle locally using the best method for that specific context.
    *   The choice depends on **robustness** (keep running even if inaccurate) vs. **correctness** (never return wrong results, even if it means stopping). This is an architectural decision.

4.  **Exceptions:**
    *   A mechanism to pass errors up the call stack when a routine encounters something it can't handle locally.
    *   Use them primarily for truly *exceptional* conditions that shouldn't be ignored. Don't overuse them for normal flow control.
    *   Handle errors locally if possible; don't use exceptions just to pass the buck.
    *   Avoid throwing exceptions from constructors/destructors due to complex language rules.
    *   Throw exceptions at the right level of abstraction (e.g., `EmployeeDataNotAvailable` not `EOFException`).
    *   Include all relevant context in the exception message.
    *   Avoid empty `catch` blocks (or document why they're truly needed).
    *   Know the exceptions thrown by library code.
    *   Consider a central exception reporter for consistency.
    *   Standardize exception usage across the project.
    *   Consider alternatives; exceptions are just one tool for error handling.

5.  **Barricades:**
    *   A damage-containment strategy. Designate interfaces (often at subsystem or class boundaries) as "barricades."
    *   Code *outside* the barricade treats data as unsafe and uses robust error handling.
    *   Code *inside* the barricade assumes data has been sanitized and can use assertions. This clarifies where different error strategies apply.
    *   Convert external data to proper types immediately upon input.

6.  **Debugging Aids:**
    *   Use tools during development that might be too slow or resource-intensive for production (e.g., routines that check data structure integrity).
    *   Introduce aids early.
    *   Use **offensive programming**: fail hard during development (asserts abort, fill memory/files with junk) to find problems quickly, allowing for graceful handling in production.
    *   Plan to remove or disable aids for production using version control, preprocessors, or stub routines.

7.  **How Much Defensive Code in Production?:**
    *   Leave code that checks for *important* errors (where failure is costly).
    *   Remove checks for *trivial* errors (where failure has minor consequences).
    *   Remove code that causes *hard crashes* (users need to save work).
    *   Leave code that helps the program crash *gracefully*.
    *   Log errors for technical support.
    *   Ensure any user-visible error messages are friendly and don't aid attackers.

8.  **Balance:** Too much defensive code adds complexity and can contain its own bugs. Be strategic about where defenses are needed most.

In essence, the chapter promotes a proactive approach to errors, urging programmers to anticipate invalid data and unexpected conditions. It provides a toolkit including input validation, assertions, various error-handling strategies (including exceptions), barricades, and debugging aids to build more robust and reliable software.

### Chapter 9. The Pseudocode Programming Process

This chapter details a systematic approach, called the **Pseudocode Programming Process (PPP)**, for constructing individual classes and, more specifically, their constituent routines. It emphasizes a structured, iterative process over ad-hoc coding or "hacking."

**Key concepts covered:**

1.  **Steps in Building Classes and Routines (Overview):**
    *   Class construction involves iterative steps: general class design (responsibilities, secrets, abstraction, inheritance, interfaces), constructing individual routines, and reviewing/testing the class as a whole.
    *   Routine construction also involves iterative steps: designing, coding, checking, and cleaning up.

2.  **Pseudocode for Pros:**
    *   Pseudocode is an informal, English-like notation used for detailed routine design.
    *   **Effective pseudocode:** Uses precise English, avoids target-language syntax, describes *intent* (what) rather than specific implementation (how), and is detailed enough that coding becomes nearly automatic.
    *   **Benefits:** Makes reviews easier (can review design before code), supports iterative refinement, makes changes easier (cheaper to change pseudocode than code), and minimizes commenting effort (pseudocode becomes the comments).

3.  **Constructing Routines Using the PPP:** This is the core of the chapter, detailing a step-by-step process:
    *   **Design the Routine:**
        *   Check prerequisites (requirements, architecture).
        *   Define the problem (routine's purpose, inputs, outputs, preconditions, postconditions, information hiding).
        *   Name the routine clearly and accurately.
        *   Decide how to test the routine.
        *   Research existing libraries/algorithms.
        *   Consider error handling strategy.
        *   Consider efficiency (usually focusing on clarity first, unless performance is critical).
        *   Write the pseudocode, starting general and refining until coding seems obvious.
        *   Think about data needed.
        *   Check the pseudocode (mentally, with peers).
        *   Iterate on the pseudocode design, keeping the best version.
    *   **Code the Routine:**
        *   Write the routine declaration (header).
        *   Turn the refined pseudocode into comments.
        *   Fill in the actual programming language code below each comment/pseudocode line.
        *   Check if code under any comment has become too complex; if so, factor it into a new routine or refine the pseudocode further (apply PPP recursively).
    *   **Check the Code:**
        *   Mentally check the routine for errors (desk check, peer review). Aim for understanding, not just code that "seems to work."
        *   Compile the routine (preferably after mental checks), using the highest warning levels.
        *   Step through the code line-by-line in a debugger.
        *   Test the code using planned test cases (may require scaffolding).
        *   Remove errors found. Rewrite if overly buggy; don't just patch.
    *   **Clean Up Leftovers:**
        *   Check the routine's interface, design quality (cohesion, coupling, defensiveness), variables, statements/logic, layout, and documentation (including removing redundant comments).
    *   **Repeat as Needed:** Iterate through the process if quality is unsatisfactory.

4.  **Alternatives to the PPP:** While PPP is recommended, other systematic approaches exist:
    *   **Test-First Development:** Write tests before code.
    *   **Refactoring:** Improve existing code via small, safe transformations.
    *   **Design by Contract:** Define routine behavior via preconditions and postconditions.
    *   **Hacking:** Discouraged as it often leads to rework, forgotten details, and getting stuck. PPP addresses these issues.

In essence, the chapter presents the PPP as a highly effective, structured, yet iterative technique for designing and implementing individual routines. It emphasizes careful thought and refinement in pseudocode *before* committing to programming language code, leading to better designs, easier coding, built-in documentation, and higher-quality routines.

## Part III. Variables

### Chapter 10. General Issues in Using Variables

This chapter covers fundamental best practices for using variables effectively and safely in programming, focusing on issues beyond just choosing a data type. It emphasizes that careful handling of variables is crucial for creating clear, maintainable, and less error-prone code.

**Key concepts covered:**

1.  **Data Literacy:** Programmers need a good understanding of various data types (arrays, lists, trees, stacks, etc.) to choose the right tool for the job. A self-test is provided to gauge familiarity.

2.  **Variable Declarations:**
    *   **Implicit Declarations:** Discouraged as highly hazardous (leading to typos like `acctNum` vs. `acctNo`). If the language supports it, turn off implicit declarations (e.g., `Option Explicit` in VB). Declare all variables explicitly. Use naming conventions and check compiler cross-references.

3.  **Variable Initialization:** Improper initialization is a major source of bugs.
    *   Initialize variables when declared, if possible (e.g., `int count = 0;`).
    *   If not possible, initialize close to the first use (Principle of Proximity).
    *   Ideally, declare and define (initialize) close to first use.
    *   Use `final` (Java) or `const` (C++) where possible to prevent later modification.
    *   Pay special attention to resetting counters/accumulators, especially in loops or routines called multiple times.
    *   Initialize named constants once (at startup); initialize true variables with executable code near use.
    *   Use compiler options to initialize variables or warn about uninitialized use.
    *   Check input parameters for validity.
    *   Use memory checkers or fill memory with recognizable patterns during development to expose initialization problems.

4.  **Scope:** Refers to how widely a variable is known (its visibility). Minimize scope to improve manageability and reduce errors.
    *   **Localize References:** Keep the code lines between references to the same variable (its "span") as small as possible.
    *   **Minimize "Live Time":** Keep the number of lines between the first and last use of a variable as small as possible. Shorter live times improve readability, reduce the window of vulnerability, minimize initialization errors, and facilitate refactoring.
    *   **General Guidelines:** Initialize loop variables just before the loop; assign values just before use; group related statements; break long routines into smaller ones; start with the most restricted scope (loop -> routine -> private class -> protected class -> package -> global) and expand only if necessary. Restricting scope enhances intellectual manageability over the mere convenience of widespread access.

5.  **Persistence:** Refers to the lifetime of data. Problems arise when assuming data persists longer than it does.
    *   Use assertions/debug code to check variable values.
    *   Set variables to "unreasonable" values (e.g., null pointers) after use.
    *   Assume data *isn't* persistent unless language features guarantee it (like `static`).
    *   Declare and initialize near use.

6.  **Binding Time:** The point at which a variable is bound to its value (coding time, compile time, load time, object instantiation time, just-in-time).
    *   Later binding times offer more flexibility but usually increase complexity.
    *   Use the latest binding time *necessary* for required flexibility, but no later, to manage complexity effectively. (e.g., prefer named constants over magic numbers; read from configuration files only if run-time changes are needed).

7.  **Data Types and Control Structures:** There's a natural correspondence (based on Michael Jackson's work):
    *   Sequential data -> sequential statements.
    *   Selective data (use one of several) -> `if`, `case` statements.
    *   Iterative data (repeated items) -> `for`, `while` loops.
    *   Structure code to follow the structure of the data it operates on.

8.  **One Variable, One Purpose:**
    *   Avoid reusing the same variable for unrelated purposes within a routine (use distinct variables).
    *   Avoid hidden meanings (e.g., `pageCount = -1` means error). Use separate variables (e.g., `pageCount` and `status`).
    *   Ensure all declared variables are actually used (unused variables correlate with errors).

In essence, the chapter stresses the importance of disciplined variable usage: explicit declaration, careful initialization close to use, minimizing scope (span and live time), understanding persistence, choosing binding time consciously, matching control structures to data, and assigning each variable a single, clear purpose. These practices significantly reduce complexity and prevent common programming errors.

### Chapter 11. The Power of Variable Names

This chapter argues that **good variable names are critically important for code readability, understandability, and maintainability**. Choosing names carefully is a key programming skill, as the variable and its name are essentially intertwined in the reader's mind.

**Key concepts covered:**

1.  **Considerations in Choosing Good Names:**
    *   **Most Important:** The name must fully and accurately describe the entity the variable represents. Stating the variable's purpose in words often yields the best name.
    *   **Problem Orientation:** Names should relate to the real-world problem being solved (e.g., `employeeData`) rather than programming constructs (e.g., `inputRec`). Express the "what," not the "how."
    *   **Optimum Length:** Names should be long enough to be descriptive but not so long they become unwieldy. Research suggests 10-16 characters is often optimal, but clarity is the main goal. Avoid overly short, cryptic names (like `x`, `ntm`) and overly long ones. Use the Goldilocks approach ("just right").
    *   **Scope:** Shorter names (like `i`, `j`) might be acceptable for variables with very limited scope (e.g., simple loop counters), but longer, descriptive names are better for variables with larger scope (class or global) or those used outside a few lines.
    *   **Computed-Value Qualifiers:** Place qualifiers like `Total`, `Average`, `Max`, `Min`, `Count`, `Index` at the *end* of the name (e.g., `revenueTotal`, `customerIndex`) for consistency and readability. Avoid ambiguous `Num`; use `Count`/`Total` or `Index`.
    *   **Opposites:** Use precise, standard opposites (begin/end, min/max, source/target).

2.  **Naming Specific Types of Data:**
    *   **Loop Indexes:** Use `i`, `j`, `k` only for short, simple loops. Use meaningful names (`recordCount`, `teamIndex`) for longer or nested loops, or if the index is used outside the loop.
    *   **Status Variables:** Avoid vague names like `flag` or `status`. Use descriptive names like `dataReady`, `error`, `found`, `success`, `processingComplete`. Use enumerated types or named constants for flag values.
    *   **Temporary Variables:** Avoid names like `temp` or `x`. Give temporary variables meaningful names that reflect their specific, temporary purpose (e.g., `discriminant`, `oldRoot`).
    *   **Boolean Variables:** Use names that imply true/false (like `done`, `success`, `found`, `error`). Prefixes like `is` (`isDone`, `isFound`) can work but sometimes reduce readability slightly. Use *positive* names (e.g., `found` instead of `notFound`) and negate with operators (`!found`).
    *   **Enumerated Types:** Use a common prefix or suffix for elements within the same group (e.g., `Color_Red`, `Color_Green`, or `Color.Red`, `Color.Green` if the language supports it).
    *   **Named Constants:** Name the *abstract entity* represented, not the literal value (e.g., `MAX_ENTRIES` not `FIVE`).

3.  **The Power of Naming Conventions:** Conventions provide structure and reduce cognitive load.
    *   **Benefits:** Reduce global decisions, aid knowledge transfer, speed up learning new code, reduce name proliferation, compensate for language weaknesses, emphasize relationships.
    *   **When to Use:** Always beneficial, but especially crucial for teams, long-lived projects, large projects, or maintainable code.
    *   **Formality:** Tailor the degree of formality to the project size and longevity.
    *   **Informal Conventions:** Differentiate variable/routine names, class/object names, global/member variables, types/constants/enums. Format for readability (e.g., `camelCase` or `under_scores`).
    *   **Language-Specific Conventions:** Follow established conventions for the language (C, C++, Java, VB, etc.) when possible, but prioritize cross-language consistency if needed.

4.  **Standardized Prefixes:** (Like Hungarian notation) Can add precision and compactness by combining semantic prefixes (e.g., `c` for count, `i` for index, `p` for pointer) with user-defined type (UDT) abbreviations. Use with caution; don't let prefixes replace a meaningful base name.

5.  **Creating Short Names (If Necessary):** Modern languages rarely require short names. If needed:
    *   Use standard abbreviations, remove vowels/articles, use first/last letters, truncate consistently, remove suffixes, use significant words.
    *   Abbreviate *consistently*.
    *   Create pronounceable names (telephone test).
    *   Avoid mispronunciations (e.g., `BEND`).
    *   Use a thesaurus to avoid collisions.
    *   Document abbreviations (in code comments or a project dictionary).

6.  **Kinds of Names to Avoid:**
    *   Misleading or ambiguous names.
    *   Names with similar meanings (e.g., `input` vs. `inputValue`).
    *   Names that differ only slightly (poor "psychological distance").
    *   Names that sound similar (homonyms).
    *   Numerals unless part of the real-world entity (`file1`, `total2`).
    *   Misspelled words (intentionally or unintentionally).
    *   Differentiation solely by capitalization.
    *   Mixed natural languages.
    *   Reserved words or names of standard types/routines.
    *   Totally unrelated or silly names.
    *   Hard-to-read characters (1 vs. l, O vs. 0, etc.).

In essence, this chapter hammers home that variable names are a crucial form of documentation and significantly impact code clarity. Programmers should invest effort in choosing names that are descriptive, unambiguous, appropriately long, problem-oriented, and consistent, using conventions to aid understanding and manageability. Good naming favors read-time convenience over write-time convenience.

### Chapter 12. Fundamental Data Types

This chapter delves into the practical use of the basic building blocks of data in programming: the fundamental data types. It provides guidelines and warnings for using numbers, integers, floating-point numbers, characters, strings, booleans, enumerated types, named constants, and arrays, as well as advice on creating user-defined types. The focus is on avoiding common errors and improving code clarity, reliability, and maintainability.

**Key concepts covered:**

1.  **Numbers in General:**
    *   Avoid **magic numbers** (unexplained literal numbers); use named constants instead for readability and easier changes. (0 and 1 are often acceptable exceptions).
    *   Anticipate and prevent **divide-by-zero** errors.
    *   Make **type conversions** explicit.
    *   Avoid **mixed-type comparisons**.
    *   Eliminate all **compiler warnings**.

2.  **Integers:**
    *   Be mindful of **integer division** (e.g., `7/10` is often 0, not 0.7). Reorder expressions to perform divisions last if necessary.
    *   Check for potential **integer overflow**, both in final results and intermediate calculations. Use larger integer types (e.g., 64-bit) or floating-point types if needed. Consider future growth.

3.  **Floating-Point Numbers:**
    *   Recognize that representation is often **inexact** (e.g., 1/3 cannot be represented perfectly).
    *   Avoid operations on numbers with **greatly different magnitudes** (e.g., 1,000,000 + 0.1 might just equal 1,000,000). Sort numbers before summing if necessary.
    *   Avoid **equality comparisons** (`==`) due to representation inaccuracies (e.g., 0.1 added 10 times might not exactly equal 1.0). Check if numbers are within an acceptable tolerance instead.
    *   Anticipate and mitigate **rounding errors** (e.g., use higher precision types, Binary Coded Decimal (BCD), or scaled integers like storing currency as cents).
    *   Use language/library support for specific types (like `Currency`).

4.  **Characters and Strings:**
    *   Avoid **magic characters and strings**; use named constants or resources for easier changes, localization, and better readability.
    *   Watch for **off-by-one errors** when indexing strings.
    *   Decide on a **Unicode strategy** early if needed for internationalization.
    *   Decide on a **consistent string conversion strategy** if using multiple types.
    *   **C Strings:** Be careful with pointer vs. array distinctions, declare arrays as `CONSTANT+1` but use `CONSTANT` in operations, initialize strings to nulls, prefer arrays over pointers if possible, use `strncpy()` etc. over `strcpy()` etc.

5.  **Boolean Variables:**
    *   Use them to **document** and **simplify** complex conditional tests by assigning meaningful names to sub-expressions.
    *   Use common names like `done`, `error`, `found`, `success`, `ok`.
    *   Names should clearly imply true/false (e.g., `error` not `status`). Consider `is` prefixes (`isDone`).
    *   Use *positive* names (`found`) rather than negative ones (`notFound`).
    *   Create your own boolean type (e.g., using `typedef` or `enum` in C) if the language lacks one.

6.  **Enumerated Types:** (Available in C++, VB; can be simulated elsewhere)
    *   Use for **readability**, **reliability** (compiler checks), and **modifiability** instead of mapping arbitrary numbers to meanings (e.g., `Color_Red` instead of `1`).
    *   Good for parameters.
    *   Can be a better alternative to booleans when more than two states are needed (e.g., `Status_Success`, `Status_Warning`, `Status_FatalError`).
    *   Always check for invalid values (e.g., in `else` or `default` clauses).
    *   Can define `_First` and `_Last` elements for loop limits (use consistently).
    *   Consider reserving the first value (often 0) as `_Invalid`.

7.  **Named Constants:**
    *   Use instead of literals to improve readability and maintainability (single-point control).
    *   Use even for "safe" literals (like 12 for months) if it improves clarity (`NUM_MONTHS_IN_YEAR`).
    *   Use consistently (don't mix constants and literals for the same entity).
    *   Simulate if the language lacks direct support.

8.  **Arrays:**
    *   Ensure indexes are always **within bounds**.
    *   Consider containers or sequential access as alternatives to random access.
    *   Check **endpoints** carefully (first element, last element, off-by-one errors).
    *   Ensure **multidimensional subscripts** are in the correct order.
    *   Avoid **index cross-talk** in nested loops (use meaningful index names).
    *   In C, consider using an `ARRAY_LENGTH()` macro.

9.  **Creating Your Own Types (Type Aliasing):** (e.g., `typedef` in C/C++, `Type` in Pascal)
    *   Powerful way to insulate the program from specific underlying types (e.g., `typedef float Coordinate;`).
    *   Makes modifications easier (change type definition in one place).
    *   Improves readability and self-documentation (`Coordinate x` vs. `float x`).
    *   Use functionally oriented names (what it *is*), not names based on the underlying type (`BigInteger`).
    *   Avoid redefining predefined types.
    *   Define substitute types for portability if needed (e.g., `INT32`).
    *   Consider creating a full class instead if more abstraction/control is needed.

In essence, the chapter is a detailed guide to using basic data types correctly and safely. It emphasizes replacing "magic" literals with named entities (constants, enums), being aware of the specific pitfalls of numeric types (division, overflow, rounding, comparison), handling strings carefully, using booleans and enums to improve clarity, and leveraging user-defined types for abstraction and maintainability.

### Chapter 13. Unusual Data Types

This chapter addresses data types and structures that are less common in pure object-oriented programming or require special handling due to their complexity or potential for misuse: **structures, pointers, and global data**. It provides guidelines for using them safely and effectively when their use is warranted.

**Key concepts covered:**

1.  **Structures:** (Refers to C/C++ `struct`, VB `Structure`, or data-only classes)
    *   **When to Use:** Although classes are generally preferred (offering privacy and functionality), structures can be useful to:
        *   **Clarify data relationships:** Bundle related items together, making it clear which variables belong together (e.g., grouping employee details).
        *   **Simplify operations on data blocks:** Allow operating on the whole structure (copying, swapping) instead of individual elements, reducing code and maintenance effort.
        *   **Simplify parameter lists:** Pass a single structure instead of numerous individual variables (but don't over-bundle or pass the whole structure if only a few fields are needed).
        *   **Reduce maintenance:** Changes to the structure (adding/removing fields) have less impact on code that treats the structure as a whole.
    *   **Consider Classes:** Always consider if a class (with private data and methods) would be a better, more encapsulated alternative.

2.  **Pointers:** (Acknowledges they are absent in some modern languages like Java/C# but understanding them is still valuable)
    *   **Inherent Complexity:** Pointers are error-prone, hard to debug (symptoms often unrelated to cause), can lead to memory corruption and security vulnerabilities (like buffer overruns).
    *   **Understanding Pointers:** A pointer has two parts: a memory address and the knowledge (base type) of how to interpret the data at that address.
    *   **General Tips (Defensive Programming for Pointers):**
        *   Isolate pointer operations in routines or classes.
        *   Declare and define/initialize pointers simultaneously and close to use.
        *   Delete pointers at the same scoping level where allocated.
        *   Check pointers (for valid address range) and the data they reference (for reasonable values) before use.
        *   Use "dog tags" (extra fields) or redundant data to detect memory corruption.
        *   Use extra pointer variables for clarity in complex operations (like linked list insertions) rather than complex pointer expressions (`p->q->r...`).
        *   Draw pictures to understand pointer operations.
        *   Delete linked list pointers in the correct order (next before current).
        *   Allocate a "memory parachute" to allow graceful shutdown if memory runs out.
        *   Overwrite ("shred") memory with junk data before deallocation to expose dangling pointer errors more consistently.
        *   Set pointers to `NULL` after deleting/freeing them to make dangling pointer writes crash predictably.
        *   Check for null/invalid pointers before attempting deletion.
        *   Keep track of allocated pointers to prevent double-deletion.
        *   Centralize pointer management in wrapper routines (e.g., `SAFE_NEW`, `SAFE_DELETE`).
        *   Use non-pointer techniques if feasible alternatives exist.
    *   **C++ Specifics:** Understand pointer vs. reference differences; use pointers for modifiable "pass by reference" and `const` references for non-modifiable "pass by value" of objects; use `auto_ptr` and consider smart pointers.
    *   **C Specifics:** Use explicit pointer types; avoid type casting; understand the asterisk rule for parameter passing; use `sizeof()`.

3.  **Global Data:** (Accessible anywhere in a program)
    *   **Common Problems:** Hard to manage complexity (breaks modularity); risk of inadvertent changes (side effects); aliasing problems; difficult re-entrant/multithreaded code; hinders code reuse; uncertain initialization order.
    *   **Reasons Sometimes Used (Often Better Alternatives Exist):** Preserving global state; emulating named constants/enums in limited languages; streamlining access to *extremely* common data (rarely justified); eliminating tramp data.
    *   **Use Only as Last Resort:** Start local, make class-scope if needed, only go global if absolutely necessary.
    *   **Using Access Routines Instead:** This is the *preferred alternative* to direct global variable use. Hide global data within a class (or module) and provide access routines (`Get()`, `Set()`). This provides centralized control, allows barricading/validation, offers information hiding benefits, is easily convertible to an ADT/class, supports locking for concurrency control (esp. during development), and enables a higher level of abstraction. Keep accesses at the same abstraction level.
    *   **Reducing Risks (If Globals Are Unavoidable):** Use clear naming conventions (e.g., `g_`); document all globals; don't use them for intermediate results; don't disguise them in "monster objects."

In essence, the chapter advises extreme caution with pointers and global variables due to their inherent risks and complexity. It strongly recommends isolating their use within classes or access routines. Structures are presented as a simpler, sometimes useful alternative to classes for grouping data, but classes are generally preferred for better encapsulation and functionality. The overarching theme is to use these "unusual" data types only when necessary and, when used, to employ rigorous defensive programming techniques to mitigate their risks.
