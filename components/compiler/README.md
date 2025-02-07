# Compiler Component

## Overview

The Compiler translates between natural language queries and structured task representations. It produces either XML task definitions or Abstract Syntax Trees (ASTs) that can be processed by the evaluator.

## Interface

```typescript
interface Compiler {
    // Convert natural language to XML task structure
    parseToXML(input: string): Promise<string>;
    
    // Convert natural language to AST
    parseToAST(input: string): Promise<ASTNode>;
    
    // Validate XML against schema
    validateXML(xml: string): ValidationResult;
}
```

## Usage

```typescript
const compiler = new Compiler();

// Parse natural language to XML
const xml = await compiler.parseToXML(
    "Analyze the data and generate a report"
);

// Or parse to AST
const ast = await compiler.parseToAST(
    "Analyze the data and generate a report"
);
```

The Compiler integrates with the Task System for template validation and the Evaluator for dynamic reparsing when tasks need decomposition. 

TODO
