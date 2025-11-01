0## **Question 1: Discuss how to investigate and understand stakeholder requirements in system analysis and design. Provide practical examples of how to understand stakeholder needs.**

### **Investigating and Understanding Stakeholder Requirements:**

**Step 1: Identify Stakeholders**

- Project sponsor, users (direct and indirect), managers, customers, suppliers
- Include all who can affect or will be affected by the system
- Consider organizational hierarchy and informal influencers

**Step 2: Select Appropriate Elicitation Techniques**

- Interviews for depth and detail
- JAD sessions for collaboration
- Questionnaires for broad input
- Observation for actual practices
- Document analysis for existing processes

**Step 3: Gather Requirements Information**

- Ask about current problems and desired improvements
- Understand business goals and user tasks
- Identify functional and nonfunctional needs
- Discover exceptions and special cases

**Step 4: Analyze and Prioritize**

- Use critical thinking to discover true requirements
- Apply root cause analysis for problems
- Prioritize as high/medium/low importance
- Distinguish facts from opinions

### **Practical Examples:**

**Example 1: DrōnTeq Sales System**

- **Stakeholders identified**: Shop Manager, Parts Room Clerk, Technicians, Inventory Department
- **Method used**: JAD sessions with cross-functional team
- **Discovery**: Through use case development, team discovered need for Flight Operations Manager role that wasn't initially recognized
- **Result**: Human oversight process for bid selection was added to requirements

**Example 2: University Course Registration**

- **Stakeholder**: Students (primary users)
- **Method**: Observation of current registration process
- **Discovery**: Students access multiple reports to get needed information
- **Understanding**: New system needs integrated information format, not separate reports
- **Result**: Requirement added for consolidated student information dashboard

**Example 3: Inventory Stock-out Problem**

- **Initial stakeholder statement**: "Eliminate inventory stock-outs"
- **Investigation approach**: Root cause analysis
- **Questions asked**: What circumstances lead to stock-outs? What business practices cause these circumstances?
- **Findings discovered**:
    - On-hand inventory updated only once weekly
    - Delays in identifying best suppliers
    - Delays in approval of supply orders
- **Refined requirements**:
    - System updates inventory levels twice daily
    - System produces out-of-stock notification immediately when reorder point reached
    - System includes recommended supplier with notifications
    - System produces purchase order for manager approval
    - System sends approved orders via secure electronic communication

---

## **Question 2: Discuss the process of requirement analysis and documentation**

### **Requirements Analysis Process:**

**Phase 1: Requirements Determination**

- Transform high-level business requirements into detailed, precise specifications
- Understand what the system must do (functional) and what characteristics it needs (nonfunctional)
- Create requirements from different perspectives: business, user, functional, nonfunctional, system

**Phase 2: Apply Analysis Strategies**

1. **Problem Analysis**
    - Ask users to identify problems with current system
    - Describe how to solve them in new system
    - Results in incremental improvements
2. **Root Cause Analysis**
    - Focus on problems first, not solutions
    - Generate all possible root causes
    - Investigate each to find true underlying cause
    - Example: Stock-outs caused by infrequent inventory updates, not insufficient stock
3. **Duration Analysis**
    - Examine time to perform each process
    - Compare total time vs. sum of individual steps
    - Large differences indicate badly fragmented processes
    - Example: Mortgage approval takes 30 days but actual work is 8 hours
4. **Activity-Based Costing**
    - Examine cost of each major process
    - Focus improvements on costliest processes
5. **Informal Benchmarking**
    - Study how other organizations perform similar processes
    - Introduces new ideas not previously considered
6. **Outcome Analysis**
    - Understand fundamental outcomes that provide customer value
    - Example: Insurance company realizes customer wants repaired car, not just payment
7. **Technology Analysis**
    - Identify important/interesting technologies
    - Determine how each could benefit the business
8. **Activity Elimination**
    - Question necessity of each activity
    - Consider operating without it
    - Identify truly essential activities

### **Requirements Documentation Process:**

**Step 1: Create Requirements Definition Statement**

- Outline format listing all requirements
- Assign unique identification numbers for tracking
- Group by type: functional and nonfunctional

**Step 2: Organize Requirements**

- **Functional Requirements**:
    - Group by business area or process
    - Distinguish process-oriented (what system does) from information-oriented (what system contains)
- **Nonfunctional Requirements**:
    - Operational (technical environment)
    - Performance (speed, capacity, reliability)
    - Security (authorized access)
    - Cultural and Political (legal, organizational factors)

**Step 3: Develop Use Cases**

- Document user-system interactions
- Show step-by-step how users accomplish tasks
- Include: name, ID, actor, description, trigger, preconditions, normal course, postconditions, exceptions

**Step 4: Create Process Models**

- Develop Data Flow Diagrams (DFDs)
    - Context diagram (system overview)
    - Level 0 (major processes)
    - Level 1+ (detailed decomposition)
- Show processes, data flows, data stores, external entities

**Step 5: Create Data Models**

- Define data structures and relationships
- Show what data must be captured and maintained

**Step 6: Validate and Verify**

- Review with stakeholders
- Role-play processes
- Check for completeness and consistency
- Prioritize requirements

**Step 7: Compile System Proposal**

- Combine all deliverables:
    - Requirements definition
    - Use cases
    - Process models
    - Data models
    - Revised feasibility analysis
    - Updated work plan

**Example Documentation: DrōnTeq Requirements**

```
Functional Requirements (Clients):
1. Learn about DrōnTeq Services
   1.1 System allows clients to review drone services by categories
   1.2 System allows clients to search services by keywords
   1.3 System allows clients to view service samples

2. Create DrōnTeq Account
   2.1 System enables clients to create account
   2.2 System enables clients to specify flight service areas
   2.3 System enables clients to add services to "desired" list

Nonfunctional Requirements:
1. Operational
   1.1 System will run on any Web browser
   1.2 Native apps for iOS and Android devices

2. Performance
   2.1 Download speeds monitored and kept acceptable

3. Security
   3.1 Customer information secured
   3.2 Payment information encrypted
```

---

## **Question 3: Discuss the importance of requirement analysis and documentation**

### **Critical Importance:**

**1. Foundation of System Success**

- Requirements determination is "single-most critical aspect of entire SDLC"
- Incorrect/incomplete requirements = primary cause of project failu-re
- 2014 survey: "Clear statements of requirements" ranked as top success factor
- Changes become exponentially more expensive in later phases

**2. Prevents Costly Rework**

- Easy to change requirements during analysis (little work done yet)
- Extremely expensive to change during design/implementation (massive rework)
- Example cost impact: $5,000 project became $250,000 due to missing nonfunctional requirements

**3. Establishes Shared Understanding**

- Provides clear communication between users and developers
- Defines scope precisely
- Sets user expectations appropriately
- Prevents misunderstandings and "surprises"

**4. Enables Accurate Project Planning**

- Requirements define what must be built
- Allows realistic time and cost estimates
- Enables proper resource allocation
- Facilitates risk assessment

**5. Provides Basis for System Design**

- Requirements flow into design phase
- Define needed software components
- Establish data structures
- Guide user interface design

**6. Supports Testing and Validation**

- Requirements define test cases
- Provide acceptance criteria
- Enable verification that system meets needs
- V-model approach: tests defined while requirements defined

**7. Manages Scope and Changes**

- Documents what's in/out of scope
- Provides baseline for evaluating change requests
- Helps control scope creep
- Enables impact analysis of proposed changes

**8. Builds Political Support**

- Involving stakeholders generates interest and commitment
- Creates trust between project team and users
- Identifies and addresses concerns early
- Establishes buy-in for the system

**9. Legal and Contractual Protection**

- Detailed requirements essential for external contractors
- Provides contractual specifications
- Defines deliverables clearly
- Protects both parties in disputes

**10. Facilitates Iterative Development**

- RAD/Agile: requirements identified in small batches
- Enables incremental implementation
- Allows system to evolve over time
- Supports continuous validation with users

### **Importance of Documentation Specifically:**

**Clear Communication:**

- Written requirements prevent verbal misunderstandings
- Permanent record available to all team members
- Consistent reference throughout project

**Traceability:**

- Unique IDs enable tracking through entire SDLC
- Can trace from requirement → design → code → test
- Facilitates impact analysis of changes

**Quality Assurance:**

- Provides baseline for validation
- Enables systematic verification
- Supports quality metrics

**Knowledge Preservation:**

- Maintains organizational knowledge
- Supports maintenance and enhancement
- Aids future projects

### **Real-World Impact Examples:**

**Negative Example (from text):**

- Manager created requirements without nonfunctional requirements
- Estimated $5,000, 1-week project
- Client wanted multi-user concurrent access on old technology
- Final cost: $250,000 over 4 months
- Company absorbed $245,000 loss

**Positive Example: DrōnTeq**

- Thorough analysis with JAD sessions
- Use cases clarified complex processes
- Discovered need for Flight Operations Manager role
- Identified exception handling requirements
- Result: Well-defined system reducing implementation risks

---

## **Question 4: Evaluate and state the advantages and disadvantages of six requirements elicitation techniques**

### **1. INTERVIEWS**

**Advantages:**

- **High depth of information**: Rich, detailed understanding of issues
- **Flexibility**: Can probe and ask follow-up questions in real-time
- **Direct interaction**: Builds rapport and trust with stakeholders
- **Clarification**: Can immediately clear up misunderstandings
- **Body language**: Can observe non-verbal cues and reactions
- **Confidentiality**: One-on-one setting encourages openness
- **適用所有階段**: Useful for as-is, improvements, and to-be systems

**Disadvantages:**

- **Time-consuming**: Must visit each person individually
- **Limited breadth**: Can only gather from one person at a time
- **Expensive**: High cost per person contacted
- **Low integration**: Difficult to resolve conflicting information from different sources
- **Interviewer skill dependent**: Requires strong interpersonal skills
- **Scheduling challenges**: Difficult to coordinate busy stakeholders
- **Potential bias**: Interviewer may influence responses
- **Limited geographic reach**: Difficult with dispersed stakeholders

**Best Used When:**

- Need detailed, in-depth information
- Working with senior managers for strategic view
- Understanding complex processes
- Building political support important
- Stakeholders geographically concentrated

---

### **2. JOINT APPLICATION DEVELOPMENT (JAD)**

**Advantages:**

- **High integration of information**: Conflicts resolved immediately during session
- **Efficient use of time**: Multiple stakeholders together simultaneously
- **Builds consensus**: Shared understanding created in real-time
- **High user involvement**: Stakeholders actively participate
- **Reduces scope creep**: By 50% according to research
- **Cross-functional perspective**: Different viewpoints heard together
- **Immediate validation**: Issues clarified on the spot
- **Team building**: Develops cooperation among users

**Disadvantages:**

- **High initial cost**: Requires many people away from work simultaneously
- **Difficult scheduling**: Hard to get everyone together
- **Requires skilled facilitator**: Expensive consultant often needed
- **Group dynamics problems**:
    - Some people dominate discussion
    - Others reluctant to challenge opinions (especially boss)
    - Not everyone participates equally
    - Side conversations can disrupt
- **Office closure**: Business unit may need skeleton staff during sessions
- **Can send wrong people**: Without management support, less competent staff sent
- **Preparation intensive**: Requires significant planning

**Best Used When:**

- Identifying improvements and to-be system
- Need to integrate multiple viewpoints
- Building consensus is critical
- Complex processes requiring collaboration
- Organization supports time investment

---

### **3. QUESTIONNAIRES**

**Advantages:**

- **High breadth**: Can reach many people quickly
- **Low cost**: Inexpensive per respondent
- **Geographic reach**: Easy to distribute to dispersed locations
- **Anonymous responses**: People may be more honest
- **Standardized data**: Everyone answers same questions
- **Quantifiable results**: Easy to analyze statistically
- **No interviewer bias**: Respondents not influenced by interviewer
- **Flexible timing**: Respondents complete at convenience

**Disadvantages:**

- **Low response rates**:
    - Paper/email: 30-50% return
    - Web-based: only 5-30% return
- **Medium depth only**: Cannot probe for deeper understanding
- **No clarification**: Cannot explain confusing questions
- **Low user involvement**: Minimal interaction with project team
- **Question design critical**: Poorly worded questions ruin data
- **Cannot observe reactions**: Miss body language and tone
- **Difficult to validate**: Can't verify respondent understood questions
- **Limited to planned questions**: Cannot explore unexpected issues

**Best Used When:**

- Need input from large, dispersed population
- Gathering facts and opinions (not deep understanding)
- System affects many users across locations
- External stakeholders (customers, vendors)
- Budget constraints
- Supplementing other techniques

---

### **4. DOCUMENT ANALYSIS**

**Advantages:**

- **Low cost**: Inexpensive to review existing materials
- **Low user burden**: Minimal time required from stakeholders
- **Objective facts**: Shows what actually exists
- **Reveals formal system**: Official procedures and policies
- **Historical perspective**: Understanding of system evolution
- **No training needed**: Analysts can do independently
- **Identifies deviations**: Shows gaps between formal and informal systems
- **Baseline understanding**: Good foundation before interviews

**Disadvantages:**

- **Limited to as-is system**: Shows only current state, not improvements
- **May be outdated**: Documentation often not maintained
- **May not exist**: Many systems poorly documented
- **Shows formal, not real**: Doesn't capture actual practices
- **Low depth**: Doesn't explain "why" behind processes
- **No user interaction**: Doesn't build relationships
- **Can be misleading**: May show intended vs. actual processes
- **Passive technique**: Cannot ask questions

**Best Used When:**

- Understanding current system initially
- Need baseline before interviews
- Learning business vocabulary and terminology
- Well-documented system exists
- Preparing for other techniques
- Budget limited

**Types of Documents:**

- Technical documentation
- Paper reports and forms (blank and completed)
- Policy manuals
- User training manuals
- Organization charts
- Problem reports
- Memorandums

---

### **5. OBSERVATION**

**Advantages:**

- **Reveals reality**: See what actually happens, not what people say
- **Validates other information**: Checks accuracy of interviews/questionnaires
- **Discovers workarounds**: Finds unofficial procedures
- **No user articulation needed**: Users don't have to explain
- **Identifies problems users forgot**: Sees all activities, even routine ones
- **Low user burden**: Minimal time required from stakeholders
- **Anthropological insight**: Understand culture and context
- **Low cost**: Inexpensive technique

**Disadvantages:**

- **Hawthorne Effect**: People behave differently when watched
- **Time-consuming**: Must observe over extended periods
- **Limited scope**: Can only observe one location/person at time
- **As-is only**: Doesn't show improvements or to-be system
- **Low depth**: See actions but not reasoning
- **May miss exceptions**: Unusual events may not occur during observation
- **Can be disruptive**: Presence may interfere with work
- **Limited understanding**: See "what" but not "why"
- **Requires analyst training**: Need skill to observe effectively

**Best Used When:**

- Validating information from interviews
- Users can't articulate processes
- Suspicion of misinformation
- Understanding as-is system
- Supplementing other techniques
- Physical processes involved

---

### **6. E-JAD (ELECTRONIC JAD)**

**Advantages:**

- **All JAD benefits plus**:
- **Reduces time 50-80%**: Much faster than traditional JAD
- **Anonymous input**: People submit ideas without attribution
- **Eliminates domination**: Everyone contributes equally
- **Parallel participation**: All contribute simultaneously (not sequential)
- **Focus on ideas' merit**: Power/rank doesn't influence evaluation
- **No fear of reprisal**: Can challenge opinions safely
- **Digital capture**: Automatic recording of all input
- **Efficient rating/ranking**: Electronic voting on ideas
- **Better for introverts**: Written communication less intimidating

**Disadvantages:**

- **All JAD disadvantages plus**:
- **Requires technology**: Networked computers and groupware needed
- **Setup cost**: Investment in e-JAD facilities
- **Learning curve**: Participants must learn the software
- **Less personal**: Reduced face-to-face interaction
- **Technology failures**: System problems can derail session
- **May lose non-verbal cues**: Less body language observation
- **Requires technical support**: IT staff needed during sessions
- **Not suitable for all**: Some participants uncomfortable with technology

**Best Used When:**

- Group dynamics problems expected
- Hierarchy issues present
- Need rapid requirements gathering
- Organization has e-JAD infrastructure
- Participants technology-comfortable
- Sensitive topics require anonymity

---

### **Summary Comparison Table:**

|Technique|Depth|Breadth|Integration|User Involvement|Cost|Best For|
|---|---|---|---|---|---|---|
|**Interviews**|High|Low|Low|Medium|Medium|Detailed understanding|
|**JAD**|High|Medium|High|High|Low-Med|Building consensus|
|**Questionnaires**|Medium|High|Low|Low|Low|Large populations|
|**Document Analysis**|Low|High|Low|Low|Low|Understanding as-is|
|**Observation**|Low|Low|Low|Low|Low-Med|Validating information|
|**E-JAD**|High|Medium|High|High|Medium|Rapid collaboration|

---

### **Key Selection Criteria:**

**Choose based on:**

1. **Project phase**: As-is understanding vs. improvements vs. to-be design
2. **Number of stakeholders**: Few vs. many
3. **Geographic distribution**: Centralized vs. dispersed
4. **Complexity**: Simple vs. complex processes
5. **Budget constraints**: Available resources
6. **Time constraints**: Urgency of requirements
7. **Political considerations**: Need for buy-in and support
8. **Organizational culture**: Formal vs. collaborative

**Best Practice: Use Multiple Techniques**

- Start with document analysis (learn domain)
- Follow with interviews (senior managers for big picture)
- Use JAD sessions (identify improvements, build consensus)
- Add questionnaires (broad validation if needed)
- Include observation (validate understanding)

---

All 4 questions answered comprehensively with precision!

Retry

Claude does not have the ability to run the code it generates yet.

[Claude can make mistakes.  
Please double-check responses.](https://support.anthropic.com/en/articles/8525154-claude-is-providing-incorrect-or-misleading-responses-what-s-going-on)

  

Sonnet 4.5