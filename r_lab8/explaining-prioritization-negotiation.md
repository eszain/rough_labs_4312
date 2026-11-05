# Explaining Lab 8: Requirements Prioritization & Stakeholder Negotiation

This guide explains every section, formula, and decision in prioritization-negotiation.md in plain language with simple everyday examples.

---

## 1. Overview of Lab 8

In software engineering, you never have enough time, money, or developers to build every feature at once. If you try to build everything at the same time, you end up with a broken, buggy system that misses its deadline.

Prioritization is how a team decides what to build first, what to build second, and what to push to next month.

Stakeholder negotiation is how teammates with different goals agree on what to build without getting into a shouting match or just taking a lazy majority vote.

Simple example:
Imagine you and two roommates have 100 dollars to furnish a brand-new empty apartment. You want a 65-inch television, your second roommate wants groceries and a microwave, and your third roommate wants to pay the electric bill so the lights turn on. You cannot buy all three right now. You must score each item, discuss the trade-offs, and negotiate who gives up what.

---

## 2. Activity A: Prioritization Method and Scoring

We use a weighted scoring model. Instead of guessing or arguing about what feels important, we grade every requirement on three objective rules using a 1 to 5 scale, then multiply each grade by its importance percentage.

The three rules we use:

1. User Value (35% weight):
How much does this feature directly help a transit rider get their lost property back?
Simple example: A feature that helps an elderly passenger find life-saving prescription medicine gets a 5. A feature that lets someone pick the background color of their receipt gets a 1.

2. Risk Reduction and Compliance (35% weight):
How much does this feature protect the transit agency from legal trouble, privacy lawsuits, stolen property, or fraud?
Simple example: Hiding credit card numbers and serial numbers so identity thieves cannot steal them gets a 5. A feature with no legal or fraud impact gets a 1.

3. Implementation Simplicity (30% weight):
How quick and easy is it for our software team to build? Note that 5 means super easy and cheap, while 1 means super hard, slow, and expensive.
Simple example: Sending a standard email confirmation is easy and gets a 4. Setting up a credit card payment system that connects to third-party shipping couriers is complicated, requires legal contracts, and gets a 2.

How the math works:
Take R-010 (Urgent Property Classification):
User Value is 5. Multiply by 0.35 = 1.75.
Risk Reduction is 5. Multiply by 0.35 = 1.75.
Implementation Simplicity is 4. Multiply by 0.30 = 1.20.
Add them together: 1.75 + 1.75 + 1.20 = 4.70. This makes it Rank 1.

Simple breakdown of the 8 scored requirements:

1. R-010 Urgent Property Classification (Score 4.70, Rank 1):
The system tags emergency items like insulin, passports, or house keys so staff look at them first.
Simple example: An ambulance crew treats a patient with chest pain before someone with a paper cut. Tagging asthma puffers ahead of lost umbrellas saves lives.

2. R-008 Candidate Match Ranking (Score 4.05, Rank 2):
A smart search algorithm that compares a lost report against found items and shows the best matches at the top.
Simple example: When you search for black backpack on Google, you want the closest matches on page 1, not scattered across 10,000 unorganized files.

3. R-026 Automated Claim Notifications (Score 4.00, Rank 3):
The system sends an automated text message or email whenever your claim status changes.
Simple example: Getting a text from Domino's saying your pizza is out for delivery stops you from calling the store every five minutes.

4. R-030 Telephone Triage Management (Score 4.00, Rank 3):
If someone writes a vague description like lost black jacket, staff can log a phone call and give the person 48 hours to describe the jacket before rejecting the claim.
Simple example: A teacher asks a student to clarify a messy answer on a test instead of immediately giving them a zero.

5. R-013 Privacy-Bounded Public Browsing (Score 3.70, Rank 5):
Putting a public list of found items on the website, but hiding serial numbers and unique stickers.
Simple example: Posting found black iPhone downtown so the real owner knows to contact transit, but hiding the lock-screen photo so a random stranger cannot claim it.

6. R-028 Public Catalog Search and Filter (Score 3.30, Rank 6):
Search boxes and dropdown filters on the public website.
Simple example: Filtering by station Union Station and category Keys so you do not have to read through 500 lost winter coats.

7. R-018 Delivery Fee Settlement Gate (Score 3.05, Rank 7):
A system check that stops staff from shipping an item until the claimant pays the courier fee.
Simple example: Amazon will not dispatch a package until your credit card charge clears. Transit cannot afford to pay 30-dollar courier bills out of taxpayer money.

8. R-017 Remote Courier Dispatch Record (Score 2.35, Rank 8):
Software integration to generate FedEx or Canada Post shipping labels to mail items directly to people's houses.
Simple example: Ordering a package online to avoid driving to the post office. It is helpful, but difficult to build and expensive to run.

---

## 3. Activity B: Sensitivity Analysis

Sensitivity analysis means checking whether your decisions change when real-world conditions change. It answers the question: Is our plan stable, or will it fall apart if our assumptions change?

Simple example:
Imagine planning a picnic based on the assumption that it will be sunny. Sensitivity analysis asks: What happens if it rains? If rain ruins the entire birthday party, your plan is fragile. If you have an indoor gazebo ready, your plan is stable.

What we tested:
We pretended our development team ran out of time before the Sprint 2 deadline. To reflect this, we raised the weight of Implementation Simplicity from 30% to 50%, and dropped User Value and Risk Reduction down to 25% each. We wanted to see which features survived when ease of building mattered most.

What happened to the rankings:
1. Low-effort features shot up to the top. R-026 (sending texts) and R-030 (logging phone calls) tied for Rank 2 because they are easy to code and do not depend on outside companies.
2. Complicated features dropped down. R-008 (match ranking algorithm) fell from Rank 2 to Rank 4 because writing smart matching algorithms takes heavy coding time.
3. Heavy external dependencies stayed stuck at the bottom. Remote courier shipping (R-017) and payment fee collection (R-018) scored 2.25 and 2.75, remaining in dead last.

Why this matters:
It proves that features requiring outside partnerships (like courier companies and bank payment gateways) are fragile. If the team tries to build courier delivery in Sprint 2 without enough time, the whole sprint will fail.

---

## 4. Activity C: Role-Based Stakeholder Negotiation

Negotiation happens when different people on a project have legitimate, competing needs and must find an agreement. A simple majority vote is bad because two people can gang up on the third person, leaving an essential requirement completely ignored.

The three assigned roles in our team:

1. Zain as the Passenger Advocate:
Goal: Make life as easy as possible for transit riders.
Stance: Riders hate traveling downtown to the central lost and found office during business hours. Zain wants riders to browse the catalog online and have items mailed directly to their homes in Sprint 2.

2. Anirudh as the Transit Operations and Privacy Officer:
Goal: Protect passenger privacy, stop scammers, and keep staff from being overwhelmed.
Stance: If we publish photos of lost wallets online, thieves will claim them. And if we start mailing items before setting up a payment system, the transit agency will lose thousands of dollars in unpaid shipping bills.

3. Muhammad as the Technical Lead:
Goal: Deliver working, tested software on time without the servers crashing.
Stance: The team only has three days before Sprint 2 is due. Building credit card processing and FedEx shipping API integrations takes weeks of setup and security testing. If we try to build it now, we will fail the sprint.

The conflict:
Zain wants remote shipping (R-017, R-018) and public catalog browsing (R-013, R-028) right now in Sprint 2. Sufyan and Anirudh say building both right now is impossible and unsafe.

The three options considered:
1. Option 1: Try to build everything right now. Rejected because Sufyan proved the team would run out of time, leaving broken code.
2. Option 2: Build nothing public; keep the system for staff eyes only. Rejected because Zain explained riders would get zero public benefit in Sprint 2.
3. Option 3: The compromise. Build public catalog browsing with hidden private details (R-013) and search filters (R-028) right now in Sprint 2. Push courier shipping and credit card processing (R-017, R-018) to Sprint 3 once contracts are signed.

The concessions made:
A concession means giving up something you wanted today to reach a shared agreement.
Simple example: Agreeing to watch your friend's favorite movie tonight if they agree to try your favorite restaurant tomorrow.
In our team:
Zain conceded remote shipping for Sprint 2 so the team can focus on getting public catalog search working smoothly.
Anirudh conceded staff time to answer public inquiries generated by the new online catalog, as long as identifying serial numbers remain hidden from public view.

Resulting project changes:
In our MoSCoW backlog:
R-013 (Public Browsing) stays as Should Have for Sprint 2.
R-028 (Public Search and Filter) gets promoted from Could Have to Should Have for Sprint 2.
R-017 and R-018 (Remote Courier and Payments) are moved back to Could Have and scheduled for Sprint 3.

