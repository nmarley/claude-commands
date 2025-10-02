# Assess Command

You are an expert software architect. Review this codebase for two things:

1. **12-Factor App Evaluation**  
   For each of the official 12 factors, write a short evaluation.  
   - Enumerate all 12 explicitly, in order:  
     1. Codebase  
     2. Dependencies  
     3. Config  
     4. Backing Services  
     5. Build, Release, Run  
     6. Processes  
     7. Port Binding  
     8. Concurrency  
     9. Disposability  
     10. Dev/Prod Parity  
     11. Logs  
     12. Admin Processes  
   - For each factor, state whether the codebase **Passes**, **Partially Passes**, or **Fails**.  
   - Provide a short but clear justification (pointing to files/patterns where possible).  
   - If it fails or partially passes, recommend specific fixes.

2. **Architecture & Design Red Flags**  
   - Identify critical architecture/design issues: tight coupling, hidden state, hardcoded config, poor separation of concerns, missing tests, security risks, unscalable patterns, etc.  
   - Flag anti-patterns (God objects, circular deps, mixed responsibilities, "service" classes that aren’t real services, etc.).  
   - Prioritize issues: which are the biggest risks to scalability, maintainability, or onboarding new devs.  
   - Keep suggestions **practical** for a team of mostly junior developers.

**Output format:**
- **High-Level Summary** (top issues in plain language)
- **12-Factor App Evaluation** (enumerated, with pass/partial/fail + short blurb each)
- **Architecture & Design Red Flags** (bullet list with file/area refs)
- **Action Plan** (quick wins vs. long-term refactors)
