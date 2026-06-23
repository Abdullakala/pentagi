```markdown
# pentagi Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides a comprehensive guide to the development patterns used in the `pentagi` TypeScript codebase. It covers coding conventions, file organization, commit standards, and testing patterns, enabling contributors to maintain consistency and quality throughout the project.

## Coding Conventions

### File Naming
- **Style:** PascalCase  
  *Each word in the filename starts with a capital letter, no underscores or hyphens.*
  ```
  // Good
  UserProfile.ts
  GameEngine.ts

  // Bad
  user_profile.ts
  game-engine.ts
  ```

### Import Style
- **Relative Imports:**  
  *Modules are imported using relative paths.*
  ```typescript
  import { GameEngine } from './GameEngine';
  import { UserProfile } from '../models/UserProfile';
  ```

### Export Style
- **Named Exports:**  
  *Functions, classes, or constants are exported by name.*
  ```typescript
  // In GameEngine.ts
  export class GameEngine { ... }

  // In another file
  import { GameEngine } from './GameEngine';
  ```

### Commit Messages
- **Conventional Commits:**  
  *Commits use a type prefix (e.g., `fix:`) and a concise description (average 60 characters).*
  ```
  fix: corrects player movement logic in GameEngine
  ```

## Workflows

### Fixing a Bug
**Trigger:** When a bug is identified in the codebase  
**Command:** `/fix-bug`

1. Create a new branch for the fix.
2. Locate the bug in the relevant PascalCase file.
3. Apply the fix, following the coding conventions.
4. Write or update a test in a corresponding `.test.ts` file.
5. Commit using the `fix:` prefix and a descriptive message.
6. Push the branch and open a pull request.

### Adding a New Feature
**Trigger:** When implementing a new feature  
**Command:** `/add-feature`

1. Create a new PascalCase file for the feature.
2. Implement the feature using relative imports and named exports.
3. Write tests in a `.test.ts` file.
4. Commit with a conventional message (e.g., `feat: add new scoring system`).
5. Push and open a pull request.

## Testing Patterns

- **Test File Pattern:**  
  Test files are named with the `.test.` infix, e.g., `GameEngine.test.ts`.
- **Framework:**  
  No specific testing framework detected; use standard TypeScript test patterns.
- **Example Test File:**
  ```typescript
  // GameEngine.test.ts
  import { GameEngine } from './GameEngine';

  describe('GameEngine', () => {
    it('should initialize correctly', () => {
      const engine = new GameEngine();
      expect(engine).toBeDefined();
    });
  });
  ```

## Commands
| Command      | Purpose                                 |
|--------------|-----------------------------------------|
| /fix-bug     | Start the bug fixing workflow           |
| /add-feature | Start the new feature implementation    |
```