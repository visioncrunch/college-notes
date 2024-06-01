## Module 3: Problems in AI

### Introduction
- Welcome back to Module 3 of DA 109, AI Basics.
- In this module, we will delve into various problems encountered in AI and explore methodologies to address them.

### Recap of Module 2
- Module 2 focused on the concept of an agent, its interaction with the environment, and the decision-making process.
- Key concepts covered:
  - **Agent:** Perception and action within an environment.
  - **Agent Function:** Specifies actions based on perception.
  - **Performance Measure:** Evaluates agent behavior.
  - **Task Environment:** Specification of the agent's operational environment.
  - **Agent Program:** Implements the agent function.
- Examples:
  - Taxi case: Safe and fast performance measure.
  - Medical diagnosis system: Healthy patient as the performance measure.
  - Various agent program designs: Simple reflex, model-based reflex, goal-based, and utility-based.

### Module 3 Objectives
- Aim: Equip learners with a solid understanding of problem-solving principles in AI.
- Divided into five parts:
  1. **Problem Definition:** Terms and requirements for defining problems in AI.
  2. **Problem Characteristics:** Categorization and characteristics of AI problems.
  3. **State Space Search:** Basic idea of problem-solving.
  4. **Significance of Search:** The role of search in AI problem-solving.
  5. **Search Strategies:** Overview of search techniques in AI.

### 1. Problem Definition
- How problems are defined in AI.
- Mandatory terms for defining AI problems.
- Crucial step in AI problem-solving.

### 2. Problem Characteristics
- Categorization and characteristics of AI problems.
- Understanding the nature of problems encountered in AI.
- Helps in selecting appropriate problem-solving methodologies.

### 3. State Space Search
- Fundamental approach to problem-solving in AI.
- Process of navigating through possible states to reach a solution.
- Key step after defining a problem in AI.

### 4. Significance of Search
- The importance of search as a problem-solving tool in AI.
- Utilized to explore solution spaces efficiently.
- Integral part of various AI algorithms and methodologies.

### 5. Search Strategies
- Overview of different search techniques in AI.
- Techniques employed to efficiently explore solution spaces.
- Selection of appropriate search strategy depends on problem characteristics.

### Conclusion
- Module 3 aims to provide a comprehensive understanding of problem-solving methodologies in AI.
- Understanding problem definition, characteristics, state space search, significance of search, and search strategies is crucial for AI practitioners.

# Lecture Notes: Problem Definition in AI

## Introduction to Problem Definition
- **Definition**: A specific task or challenge requiring a solution or decision-making process.
- **Scope**: Ranges from simple arithmetic calculations to complex tasks like image recognition, natural language processing, game playing, and optimization.
### Components of a Problem
- **Initial State**: Starting conditions for the problem-solving process.
- **Possible Actions**: Choices or steps available to navigate from one state to another.
- **Goal State**: Desired outcome or condition to be achieved.
#### Examples:
- **Game of Chess**: Finding a sequence of moves resulting in a checkmate.
- **Route Planning**: Determining the shortest path between two locations on a map.

## Problem Definition Process
- **Description of the Problem**: Clearly articulating what needs to be solved or achieved.
- **Goal Identification**: Defining the desired outcome.
- **Scope Definition**: Setting boundaries and limitations.
- **Constraint Identification**: Recognizing restrictions or limitations.
- **Assumption Statement**: Stating any assumptions made.
- **Criteria for Success**: Establishing performance metrics.

### Importance of Problem Definition
- Guides problem-solving efforts.
- Prevents ambiguity and misinterpretation.
- Aligns stakeholder expectations.
- Focuses resources effectively.

## Problem Space
- **Definition**: Set of all possible states, actions, transitions encountered while solving a problem.
- **Representation**: Defines configurations, arrangements of elements, and valid moves or actions.
- **State**: Represents a specific configuration.
- **Action**: Represents a possible move from one state to another.

### Example: Route Planning
- **Problem Space**: Includes all locations on the map as states and valid roads or paths between them as actions.
- **Optimization**: Evaluating different routes based on distance, time, fuel efficiency.

#### Importance of Understanding Problem Space
- Guides exploration and evaluation of solutions.
- Facilitates identification of optimal paths.
- Informs decision-making during problem-solving.

```python
# Example of problem space representation for route planning
locations = ["A", "B", "C", "D", "E", "F"]
valid_paths = [("A", "B"), ("A", "C"), ("A", "D"), ("A", "E"), ("A", "F")]
# Define distances between locations
distances = {("A", "B"): 30, ("A", "C"): 25, ("A", "D"): 28, ("A", "E"): 27, ("A", "F"): 32}
# Example: finding optimal route from A to B based on distance
optimal_route = min(valid_paths, key=lambda x: distances[x])
print("Optimal route:", optimal_route)
```

---
### Lecture Notes: Introduction to Search Algorithms

#### What is Search?

- **Definition**: Search is the process of exploring the problem space to find the sequence of actions or moves that lead to the goal state or satisfactory solution.
  
- **Example**: Finding the shortest route between two locations on a map using a navigation app.
  
- **Search Algorithm**: Explores various paths and evaluates different routes to determine the optimal sequence based on criteria such as fuel or time consumption.

#### Search in AI

- **Purpose**: Search algorithms are used to systematically navigate through the problem space and discover paths or solutions that satisfy problem constraints and objectives.
  
- **Process**: 
  - Start from an initial state.
  - Explore possible actions to generate new states.
  - Evaluate states based on criteria like distance to the goal, cost, or utility.
  - Continues iteratively until the goal state or a satisfactory solution is reached.

#### Components of Well-Defined Problems and Solutions

- **Initial State**: Where the agent starts from.
- **Actions**: Description of possible actions available to the agent.
- **Transition Model**: Description of what each action does.
- **Goal Test**: Determines whether a given state is a goal state.
- **Path Cost**: Assigns numeric cost to each path.

#### Formulating Problems

##### Example: Vacuum World

- **Description**: A cleaner equipped with AI designed to navigate indoor environments and perform cleaning tasks autonomously.
  
- **Components**:
  - **States**: Determined by agent and dirt locations.
  - **Initial State**: Any state from which the goal can be achieved.
  - **Actions**: Left, right, or suck.
  - **Transition Model**: Actions have expected effects.
  - **Goal Test**: Checks whether all squares are clean.
  - **Path Cost**: Each step costs one.

##### Example: 8-Puzzle [Puzzle (murhafsousli.github.io)](https://murhafsousli.github.io/8puzzle/#/)

- **Description**: A sliding puzzle game with a 3x3 grid and one empty space.
  
- **Components**:
  - **State**: Location of tiles and blank space.
  - **Initial State**: Any state.
  - **Actions**: Movement of the blank space (left, right, up, down).
  - **Transition Model**: Returns resulting state given a state and action.
  - **Goal Test**: Checks whether the state matches the goal configuration.
  - **Path Cost**: Each step costs one.

#### Conclusion

- **Summary**: Problem definition includes states, initial states, actions, transition model, goal test, and path cost.
  
- **Importance**: Understanding these components is crucial for solving problems optimally.

### Suggestions and Tips

- **Understanding**: Take time to understand the components of a well-defined problem before attempting to solve it.
- **Practice**: Work on various problem formulations to strengthen problem-solving skills.
- **Adaptation**: Adapt algorithms and strategies based on specific problem characteristics for optimal results.

# Lecture Notes: Understanding Problem Characteristics

## Introduction
Understanding the characteristics of a problem is crucial for effective problem-solving. It helps in tailoring appropriate problem-solving strategies by analyzing complexity, scope, constraints, and underlying patterns.

### Importance
- Foundation for selecting suitable problem-solving techniques.
- Efficient resource allocation and effective solution planning.
- Anticipation of potential challenges and proactive solution devising.

## Problem Characteristics

## Choosing an Appropriate Problem

To select an appropriate problem for problem-solving, consider the following checklist:

- **Decomposability:** Can the problem be broken down into smaller, manageable sub-problems?
- **Ignoring or Undoing Steps:** Can solution steps be ignored or undone during the problem-solving process?
- **Predictability:** Is the outcome of the problem predictable based on available information?
- **Solution Absoluteness:** Is the solution to the problem absolute or relative?
- **Solution Type:** Is the solution represented as a state (final configuration) or a path (sequence of steps)?
- **Role of Knowledge:** What role does knowledge play in understanding and solving the problem?
- **Human Interaction:** Does solving the problem require human interaction or collaboration?

Considering these factors helps in selecting a problem that aligns with available resources, expertise, and problem-solving strategies, leading to more effective and efficient solutions.
### Decomposability
- **Definition:** Can the problem be broken down into smaller problems to be solved independently?
- **Criteria:** 
  - Easily decomposable?
  - Utilizing the divide-and-conquer technique?
- **Use of Decomposing Problems:**
  - Each sub-problem is simpler to solve.
  - Each sub-problem can be handled by different processors, enabling parallel processing.
- **Implication:**
  - Decomposable problems facilitate parallel solving, improving efficiency.
  - Example: Large-scale transportation network design can be decomposed into traffic flow optimization, infrastructure planning, and urban development.
- **Is Travel Salesman Problem Decomposable?**
	- No because it just needs the shortest path there is nothing else to decompose to solve.

Got it, I'll incorporate this information about ignoring or undoing steps into the lecture notes:

I'll incorporate the provided information about ignoring or undoing steps into the lecture notes:

### Ignoring or Undoing Steps
- **Definition:** Can solution steps be ignored or undone during the problem-solving process?
- **Theorem Proving:**
  - Can be solved using a simple control strategy.
  - Example: Suppose a lemma is proven to be unhelpful in proving a theorem; it can be ignored, and another lemma can be pursued.
- **The 8-Puzzle:**
  - Solved by backtracking, requiring a control strategy implemented using a stack.
  - Example: Moves in the puzzle can be undone and backtracked, allowing exploration of alternate paths.
- **Playing Chess:**
  - Solved through a planning process.
  - Example: Moves in chess cannot be retracted, making the process irrevocable.
  - It is as similar to the irreversible step of cooking food on flame.


## Conclusion
Understanding problem characteristics is essential for selecting appropriate problem-solving techniques, fostering innovation, and promoting informed decision-making across various domains and contexts. It enhances problem-solving efficacy and fosters a systematic approach to tackling complex problems efficiently.

### Lecture Notes: Is the Universe Predictable?

#### Determinism vs. Unpredictability:
- **Deterministic Outcomes**:
  - Results known, predictable with certainty based on given conditions/rules.
  - Example: Eight puzzle - every move leads to known outcome.
- **Non-deterministic Outcomes**:
  - Involves uncertainty or randomness.
  - Example: Playing bridge - uncertainty about cards, others' actions.
- **Real-world Examples**:
  - Weather patterns: Meteorological models face uncertainty due to chaotic nature of atmosphere dynamics.
  - Challenges in predicting complex phenomena underscore limits of predictability.

#### Planning for Predictability:
- **Certain Outcome Problems**:
  - Use planning to generate sequence of operators leading to guaranteed solutions.
- **Uncertain Outcome Problems**:
  - Sequences have probabilistic solutions; plan revision required during execution.
- **Example**: Eight puzzle vs. playing bridge.

#### Absolute vs. Relative Solutions:
- **Objective Evaluation**:
  - Absolute: Solution quality objectively assessed based on predefined criteria.
- **Subjective Evaluation**:
  - Relative: Solution quality depends on subjective factors, individual perspectives.
- **Example**: Marcus's lifespan - inference based on historical context.

#### Traveling Salesman Problem (TSP):
- **Objective**: Find shortest route visiting all cities once.
- **Heuristic vs. Exhaustive Search**: 
  - Heuristic suggests good paths; exhaustive search for best path.
- **Absolute vs. Relative Evaluation**: Minimalist vs. visually rich interface in mobile app design.

#### Solution as State or Path:
- **State vs. Path Problems**:
  - State: Configuration/arrangement of states.
  - Path: Sequence of actions to reach configuration.
- **Example**: Water jug problem - transferring water to achieve target volume.

#### Ambiguity in Language:
- **Contextual Interpretation**: 
  - Ambiguity arises from multiple meanings of words/phrases.
  - Importance of contextual cues for consistent interpretation.
- **Example**: Bank president eating pasta salad with a fork.

#### Maze Problem:
- **State vs. Path Perspective**:
  - State: Reaching specific location within maze.
  - Path: Sequence of movements to navigate through maze.

## Role of Knowledge in Problem Solving

### Introduction
The role of knowledge in problem solving is fundamental as it provides the necessary information, insights, and strategies to guide the decision-making process towards achieving desired outcomes efficiently and effectively.

### Chess Knowledge Example
- **Example**: In chess, knowledge is essential to constrain the search for a solution.
- **Explanation**: Players rely on their knowledge of chess principles, tactics, and patterns to anticipate opponent moves and formulate winning strategies.
- **Code Snippet**: 
  ```python
  # Example of using chess knowledge in a game
  from chess import Board, Move

  board = Board()
  move = Move.from_uci("e2e4")
  board.push(move)
  ```

### Newspaper Story Example
- **Example**: Understanding a newspaper story requires a lot of knowledge to recognize the solution.
- **Explanation**: Readers need background knowledge about politics, current events, and social issues to interpret the news accurately.
- **Scenario**: Scanning daily newspapers to determine political affiliations during an election.

#### Factors to Consider
- Identifying political biases
- Analyzing editorial content
- Examining coverage biases
- Considering historical context
- Recognizing regional influences
- Utilizing external resources

### Knowledge in Medical Diagnosis
- **Example**: Diagnostic medical systems rely on knowledge to contextualize crucial information for healthcare professionals.
- **Explanation**: Doctors leverage their medical expertise, training, and experience to diagnose illnesses and recommend treatments.
- **Code Snippet**:
  ```python
  # Example of medical diagnosis using knowledge-based systems
  from medical_system import MedicalSystem

  symptoms = ["headache", "fever", "cough"]
  diagnosis = MedicalSystem.diagnose(symptoms)
  ```

### Summary
- Knowledge empowers individuals and organizations to make informed decisions, overcome challenges, and achieve desired outcomes across various domains.

## Does the Task Require Human Interaction?

### Solitary Problems
- **Definition**: Problems where individuals work independently without communication.
- **Example**: Student solving math problems at home.
- **Explanation**: The focus is solely on individual skills and knowledge without collaboration.

### Conversational Problems
- **Definition**: Problems requiring interaction and collaboration among participants.
- **Example**: Engineers brainstorming to optimize product design.
- **Explanation**: Collaboration leads to collective exploration of solutions and refinement of ideas.

### Customer Service Example
- **Scenario**: Answering customer inquiries via email or chat.
- **Explanation**: Automated chatbots handle routine inquiries, but human intervention is necessary for complex issues requiring empathy and understanding.

### Striking the Right Balance
- Achieving the right balance between automated and human interaction is crucial for optimizing problem-solving processes and delivering value to stakeholders.

## Conclusion
Understanding the role of knowledge and the necessity of human interaction are essential for designing efficient problem-solving solutions across various domains.

## Lecture Notes: State Space Search in AI

### Introduction

- **Problem Space:** The set of all possible states a problem can be in.
- **State:** A specific configuration or arrangement within the problem space.
- **State Space Search:** A method to systematically explore the state space to find a solution.

### Key Components of State Space Search

1. **Set of Legal Positions (States):** Every possible state the problem can take.
2. **Initial State:** The starting point of the search.
3. **Set of Rules:** Define how to transition from one state to another.
4. **Goal State:** The desired ending state of the problem.

### Chess Example

- **States:** Each possible board configuration represents a state.
- **Initial State:** The standard starting position of the game.
- **Goal State:** Checkmate (opponent has no legal moves, or their king is under attack).
- **Rules:** Describe how pieces can move legally.

### Water Jug Problem

**Problem Definition:**

Given two jugs, one 4-liter and one 3-liter, without measuring markers, fill the 4-liter jug with exactly 2 liters of water using a pump.

**Steps:**

1. **Represent the State:**
    
    - `x`: Liters of water in the 4-liter jug
    - `y`: Liters of water in the 3-liter jug
    - Possible states for `x`: 0, 1, 2, 3, 4
    - Possible states for `y`: 0, 1, 2, 3
2. **Initial State:** (0, 0) (both jugs empty)
    
3. **Goal State:** (2, *) (2 liters in the 4-liter jug, any amount in the 3-liter jug)
    

**Production Rules (Operators):**

|Current State (x, y)|Condition|Action|Resulting State|
|---|:--|:--|:--|
|(x, y)|x < 4|Fill 4-liter jug|(4, y)|
|(x, y)|y < 3|Fill 3-liter jug|(x, 3)|
|(x, y)|x > 0|Pour out some water from 4-liter jug|(x-d, y) (d is the amount poured out)|
|(x, y)|y > 0|Pour out some water from 3-liter jug|(x, y-d) (d is the amount poured out)|
|(x, y)|x > 0|Empty 4-liter jug|(0, y)|
|(x, y)|y > 0|Empty 3-liter jug|(x, 0)|
|(x, y)|x + y >= 3 and y < 3|Pour water from 4-liter jug into 3-liter jug until the 3-liter jug is full|(x - (3 - y), 3)|
|(x, y)|x + y <= 4 and x < 4|Pour water from 3-liter jug into 4-liter jug until the 4-liter jug is full|(4, y - (4 - x))|

**Solution Path:**

1. (0, 0) -> Fill 3-liter jug -> (0, 3)
2. (0, 3) -> Pour into 4-liter jug -> (3, 0)
3. (3, 0) -> Fill 3-liter jug -> (3, 3)
4. (3, 3) -> Pour into 4-liter jug (1 liter remaining in the 3-liter jug) -> (4, 2)
5. (4, 2) -> Empty 4-liter jug -> (0, 2)
6. (0, 2) -> Pour into 4-liter jug -> (2, 0) (Goal State)

**Visual Representation:**

```
Start:
 4L: |   | (0)
 3L: |   | (0)

Goal:
 4L: |   | (2)
 3L: |   | (*) 
```

### General State Space Search Problem

1. **Define State Space:** All possible configurations of the problem.
2. **Specify Initial State:** The starting configuration.
3. **Specify Goal State:** The desired ending configuration.
4. **Specify Set of Rules:** Actions to move between states.

### Unstated Assumptions and Considerations:

- **Generality of Rules:** How broad or specific should the rules be?
- **Knowledge in Rules:** How much problem-solving knowledge should be embedded in the rules themselves?
- **Control Strategy:** The order in which rules are applied, impacting the efficiency and effectiveness of the search.

Let me know if you'd like me to elaborate on any specific aspect or provide more examples!