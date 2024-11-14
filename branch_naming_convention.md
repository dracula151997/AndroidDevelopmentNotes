## Branch Naming Convention

### General Structure
- Branch names follow this structure:  
  `prefix/JIRA-ISSUE-KEY-description`

### Components
1. **Prefix**:
   - `feature/`: For new features
   - `bugfix/`: For bug fixes
   - `hotfix/`: For urgent fixes that need immediate attention
   - `chore/`: For maintenance tasks, like updating dependencies
   - `refactor/`: For improving existing code without changing functionality

2. **Jira Issue Key**:
   - Always include the Jira ticket ID (e.g., `PROJECT-123`) in your branch name.

3. **Description**:
   - A short, descriptive phrase summarizing the work being done.
   - Use lowercase letters and hyphens (`-`) for word separation.
   - Avoid spaces, camelCase, and special characters.

### Examples
- New Feature:  
  `feature/PROJECT-123-user-authentication`
- Bug Fix:  
  `bugfix/PROJECT-456-login-crash`
- Hotfix:  
  `hotfix/PROJECT-789-currency-issue`
- Refactor:  
  `refactor/PROJECT-101-code-cleanup`

### Benefits
- **Traceability**: Easily link branches to Jira tickets.
- **Clarity**: Clear purpose and context for each branch.
- **Consistency**: Improved team collaboration through consistent naming.
