# Blocks

A Block is an executable code with an associated context. It can be passed around in code to be executed at a later time or on a different thread. 

### Block Literal Syntax

```Objective-C
  ^(arguments) { body };
  
  ^(int a, int b) { return a * b; };
  
  ^(void) { return 10; };
```

### Blocks in GCD

Blocks are extensively used in the Grand Central Dispatch (GCD). A block represents a unit of work that GCD can execute.

