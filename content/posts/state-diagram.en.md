--- 
title: "State Diagram"
description: "Describe the behavior of systems" # update text !
date: 2021-02-25T15:44:30+01:00 # update date !

draft: true # toggle to false when final version is approved !

languageName: "English"
author: ["Giacomo", "Nicolò", "Lorenzo", "Stefano"] 

tags: ["Software Requirements"]      
categories: ["Software Requirements"]   
---  

<!-- Write content Down Here :) -->
<!-- placeholder text || you can use Markdown or HTML to add some content -->

A **state diagram** consists of *states*, *transitions*, *events*, and *activities*. You use state diagrams to illustrate the **dynamic view** of a system. They are especially important in modeling the behavior of an *interface*, *class*, or *collaboration*. State diagrams emphasize the **event-ordered** behavior of an object, which is especially useful in modeling reactive systems.

# Basic State Chart Diagram Symbols and Notations

## State

A **state**is a condition during the life of an object during which it *satisfies some condition*, *performs some activity*, or *waits for some external event*.

![State_simple](State%20Diagram/State_simple.svg)
State is represented by a rectangle
![State_complex](State%20Diagram/State_complex.svg)
A state with internal activities

## Initial and Final States

- The **initial state** of a state machine diagram, known as an *initial pseudo-state*. A *transition*from this state will show the **first real state.**

![InitialState](State%20Diagram/InitialState.svg)
A filled circle followed by an arrow represents the object's initial state

- The **final state** of a state machine diagram. An *open loop* state machine represents an object that may *terminate before the system terminates*, while a *closed loop* state machine diagram does *not have a final state*; if it is the case, then the object lives until the entire system terminates.

![FinalState](State%20Diagram/FinalState.svg)
An arrow pointing to a filled circle nested inside another circle represents the object's final state

## Event

An **event** is the *specification*of a *significant occurrence*. For a state machine, an event is the occurrence of a stimulus that can trigger a state transition.

## Action

An **action** is an *executable computation*. Actions may include *operations*, the *creation*or *destruction* of other objects, or the *sending*of signals to other objects.

## Transition

A **transition**is a *relationship* between *two states* indicating that an object in the *first state* will, when a specified set of events and conditions are *satisfied*, perform certain *action/s*and enter the *second state*.

A transition has:

1. source state
2. event trigger
3. action/s
4. target state

![Arrow](State%20Diagram/Arrow.svg)
A solid arrow represents the path between different states of an object

```text
A **self-transition** is a transition whose *source* and *target states* are *the same*
```

# Advanced State Chart Diagram Concepts

## Constraints

It is possible to add **constraints**to transitions, the semantics is that a transition is *enabled*when the constraint is *true*

![Contraint](State%20Diagram/Contraint.svg)
Constraint ”[not last copy]” and ”[last copy]” are used to distinguish the two transitions with the event ”copyBorrowed()”

## Substates

A **sub-state** is one which has *no substructure*. A state which has *sub-states*(nested states) is called a **composite state**. Sub-states may be nested to any level. A nested state machine may have at most one initial state and one final state. Sub-states are used to simplify complex flat state machines by showing that some states are only possible within a particular context.

![Substates](State%20Diagram/Substates.svg)
The Cooling composite state has 3 nested state (sub-state) that run in sequence

## History States

When a transition enters a *composite state*, the action of the nested state machine starts *over again* at the *initial state*. **History states** allow the state machine to **re-enter the last sub-state** that was active in it prior to leaving the composite state.

![HistoryState](State%20Diagram/HistoryState.svg)
The Shallow History State is represented by an H in a circle

## Concurrent State

**Concurrent Sub-states** are *independent*and can complete at different times and each sub-state is separated from the others by a dashed line.

![ConcurrentState](State%20Diagram/ConcurrentState.svg)
Into the On state 4 nested state run into 2 different parallelism. The 2 sub-states are divided by a dashed line

# Example

Here is an example of the process life in a CPU.

When a **new process** is *ready for the execution*, it will **moved to the ready queue** where it wait for the CPU assignment. When the *CPU is free* for this process, it will **moved to the running queue**. In the running state 2 cases can occur: the *process finished or terminated* his life, so it will **moved out of the running state**; or the *resource is unavailable*, so it will **moved to the blocked queue** and when the *resource is freed*, it will **moved again to the ready queue**.

[![CPUStateDiagram](State%20Diagram/CPUStateDiagram.svg)
State Diagram - CPU Execution
