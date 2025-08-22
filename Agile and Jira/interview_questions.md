
# 📘 Agile & Jira Interview Preparation

## 1. What is Agile?
Agile is an iterative approach to software development that emphasizes **flexibility**, **collaboration**, and **customer feedback**.

## 2. What are the values of the Agile Manifesto?
1. Individuals and interactions over processes and tools  
2. Working software over comprehensive documentation  
3. Customer collaboration over contract negotiation  
4. Responding to change over following a plan  

## 3. What are the 12 principles of Agile?
- Customer satisfaction via early and continuous delivery  
- Welcome changing requirements  
- Deliver working software frequently  
- Business & developers must work together  
- Build projects around motivated individuals  
- Face-to-face communication  
- Working software is the primary measure of progress  
- Maintain sustainable pace  
- Continuous attention to technical excellence  
- Simplicity  
- Self-organizing teams  
- Regular reflection and adjustment  

## 4. What is Scrum?
Scrum is a **framework** within Agile to develop complex products using **empirical process control**, involving:
- Roles: Product Owner, Scrum Master, Development Team
- Events: Sprint, Planning, Daily Scrum, Review, Retrospective
- Artifacts: Product Backlog, Sprint Backlog, Increment

## 5. What is a Sprint?
A **time-boxed** period (usually 2 weeks) during which a potentially shippable product increment is developed.

## 6. What are Scrum Ceremonies?
- **Sprint Planning** – Define work for the sprint  
- **Daily Scrum** – Stand-up meeting to inspect progress  
- **Sprint Review** – Demonstrate completed work  
- **Sprint Retrospective** – Reflect & improve process  

## 7. What are the pillars of Scrum?
1. **Transparency**  
2. **Inspection**  
3. **Adaptation**  

## 8. What is the Product Backlog?
An **ordered list of work** to be done, maintained by the Product Owner. Includes features, enhancements, fixes, technical debt, etc.

## 9. What is a User Story?
A simple description of a feature from an end-user’s perspective.  
**Format**:  
`As a [user], I want [goal] so that [benefit].`

## 10. What is INVEST?
Guidelines for good user stories:
- **I**ndependent  
- **N**egotiable  
- **V**aluable  
- **E**stimable  
- **S**mall  
- **T**estable  

## 11. What is a Definition of Done (DoD)?
A **checklist** agreed upon by the team to define when a task is considered **complete**.

## 12. What is velocity?
The amount of work a team completes in a sprint, usually measured in **story points**.

## 13. What is a Burndown Chart?
A visual representation of **remaining work** vs. **time**.

## 14. What is a Burnup Chart?
Shows the **total scope** and **completed work** to track progress and scope changes.

## 15. What happens if priorities change mid-sprint?
- Stick to the sprint goal  
- Push changes to the next sprint  
- In critical cases, cancel and replan sprint

## 16. What is a Spike?
A **time-boxed research task** used to gather knowledge necessary to reduce risk or understand a requirement.

## 17. What is technical debt and how to manage it?
**Technical debt** refers to shortcuts or poor solutions that require refactoring later.  
Manage by:
- Creating separate tickets  
- Allocating time in each sprint  
- Prioritizing based on impact

## 18. What is Jira?
A **project management tool** used to plan, track, and manage Agile projects. Popular for Scrum, Kanban, and Bug Tracking.

## 19. What are Epics, Stories, and Tasks in Jira?

| Item  | Description                          |
|-------|--------------------------------------|
| Epic  | Large body of work, broken into stories |
| Story | User feature/requirement             |
| Task  | Technical or operational work        |

## 20. What is JQL?
**Jira Query Language** to search and filter issues.  
Example:
```jql
project = "ABC" AND status = "In Progress" AND assignee = currentUser()
```

## 21. What are Jira Workflows?
Define how an issue transitions from one state to another. Includes:
- **Statuses** (To Do, In Progress, Done)  
- **Transitions**  
- **Validators**, **Conditions**, **Post-functions**

## 22. What are Jira Schemes?
Configuration sets that define:
- Permissions  
- Notifications  
- Workflows  
- Issue types

## 23. How do you manage dependencies in Jira?
- Use **Linked Issues** (blocks, is blocked by, relates to)  
- Visualize using **Advanced Roadmaps** or Gantt plugins

## 24. How do you handle over-commitment?
- Track and analyze **velocity**  
- Adjust planning in next sprint  
- Reflect in retrospectives

## 25. What tools integrate well with Jira?
- **Confluence** for documentation  
- **Bitbucket/GitHub** for code  
- **Slack** for communication  
- **Jenkins/GitLab** for CI/CD  
- **Xray/TestRail** for test cases  
