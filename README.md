# Causal Loop Diagramming With Mermaid JS

Causal Loop Diagram Style Guide for MermaidJS 
## Table of Contents
  - [About The Project](#about-the-project)
  - [Getting Started](#getting-started)
  - [Organization Rules/ Style Guide](#style-guide)
  - [Why](#why)
  - [Next Steps](#next-steps)
  - [Contribute](#contribute)


# About the project
This is a quick guide for creating casual loop diagrams with mermaidjs this will allow you to quickly generate shareable, iteratively editable Casual Loop Diagrams.

# Getting Started 
To use this simply go to [MermaidJS Live](https://mermaid.live) and copy the example from the [template.mmd](template.mmd) file and launch or 
Use this from your IDE like [VS-code](https://code.visualstudio.com/) or just get started on your own with a blank graph 
```
graph LR

%% class def at the bottom adds a transparecy to the nodes
classDef tr fill:#00000000, stroke:#00000000;
```

## Style Guide

1. Nodes should be initialized at the top of the graph
```
graph LR
    fooState["foo"]:::tr
    barState["bar"]:::tr
    %% fooState[some label text here] allows us to initialize node with no connections
    %% it allows us to have an easy reference to the label

    %% class def at the bottom adds a transparecy to the nodes
classDef tr fill:#00000000, stroke:#00000000;
```

2. Nodes names should be camelCased 
```
graph LR
    camelCaseState["camel"]:::tr
    barState["bar"]:::tr
    %% initialized 
    camelCaseState --> |+|barState
    barState --> |-|camelCaseState

%% class def at the bottom adds a transparecy to the nodes
classDef tr fill:#00000000, stroke:#00000000;
```

3. Outgoing links should be grouped together
```
graph LR
    fooState["foo"]:::tr
    barState["bar"]:::tr
    bazState["baz"]:::tr
    carState["car"]:::tr

    fooState -->|+| barState 
    fooState -->|-| carState 
    barState -->|+| bazState 
    barState -->|-| carState 
    bazState -->|-| carState 
    carState -->|+| barState 

%% class def at the bottom adds a transparecy to the nodes
classDef tr fill:#00000000, stroke:#00000000;
```

4. Directions should be normalized to point one way
```
graph LR
    someState["some"]:::tr
    otherState["other]:::tr
    someState --> otherState
    otherState --> someState
%% class def at the bottom adds a transparecy to the nodes
classDef tr fill:#00000000, stroke:#00000000;
```
Avoid
```
graph LR
    someState["some"]:::tr
    otherState["other]:::tr
    someState --> otherState
    someState <-- fooState

%% class def at the bottom adds a transparecy to the nodes
classDef tr fill:#00000000, stroke:#00000000;
```

5. classDefs go at the bottom of the file '
```
graph LR 
    someAction["action"]:::tr
    corrAction["correlated action"]:::tr

%% makes the node background transparent and outline transparent
classDef tr fill:#00000000, stroke:#00000000;
```

6. Delays in the graph are represented by //
```
graph LR 
    someAction["action"]:::tr
    corrAction["correlated action"]:::tr

    someAction -->|-//| corrAction
    corrAction -->|+| someAction

%% makes the node background transparent and outline transparent
classDef tr fill:#00000000, stroke:#00000000;
```

## Why ?
Diagrams are an essential tool in token engineering. Not having a way to share,reuse, iterate,extend and collaborate on diagrams hurts. 

Let's start this token diagrams in code movement, with one of the most important diagrams that you encounter in token engineering, the [Causal Loop Diagram](https://en.wikipedia.org/wiki/Causal_loop_diagram).
![](https://i.imgur.com/8BYWw4K.png)

Causal Loop Diagrams are diagrams that help us visualize the relationships between entities. **‘+’** represent positively correlated relationships and **‘-’** negatively correlated relationships.  


## Next Steps 
- Style Linter 
- improved naming convention think char limit
- ability to add notes to diagram
- rules around subgraphs
- rules around spacing

## Useful Communication Channels Discord
[Token Engineering Academy](https://discord.gg/2mNwEgrcGm)
[Token Engineering Commons](https://discord.gg/nRprMgkMcs)
[Ships](https://discord.gg/SmJv96G9PX)

## Contribute
Create an issue and contribute to making codeable diagrams 
more widespread in the token engineering community
