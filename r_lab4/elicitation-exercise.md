# Lab 4: Simulated Requirements Elicitation

## Elicitation Objective

We want to learn how central Lost & Found staff verify ownership before releasing property, and how passengers experience submitting reports and proving ownership. Our Sprint 0 requirements (R-008 and R-009) separate matching from verification, but leave the evidentiary standard and escalation paths undefined. This exercise gathers simulated evidence from both staff and claimant perspectives to clarify those workflows.

## Stakeholder Roles

1. Central Lost & Found Staff Member (STK-04 in stakeholder register): Processes recovered items, reviews candidate matches, and makes approval, rejection, or escalation decisions.
2. Passenger / Lost-Item Claimant (STK-01 in stakeholder register): Reports lost property through the system and provides evidence to recover it.

## Interview Transcripts

*[SIMULATION] The following records reflect questions asked and answers given during the simulated in-lab interview rounds.*

### Round 1: Central Lost & Found Staff

1. How does the user submit the form, and what details are needed to submit it?
Response: A generic submission like just writing "jacket" will not work. Claimants must provide a detailed form covering specific aspects: color, brand, design patterns, button types, zippers, and other specific construction features.

2. How do you verify that the user actually owns the item?
Response: Staff compare the specific details submitted on the form against the physical item in inventory. Because the public listing does not reveal these specific attributes, a match between the claimant's detailed description and the physical item confirms ownership.

3. What happens if the user does not remember the descriptive details of the item?
Response: When a claimant cannot recall specific details on the initial form, staff place a phone call to the user to talk through the item and try to draw out additional distinguishing memories or evidence.

4. What is your most complicated case?
Response: A lost gaming mouse. Staff could not get enough information from the claimant to verify ownership. Because it was considered a high-value item, it was forwarded to the police to handle.

5. What happens generally if an item is of high value and ownership cannot be verified?
Response: If an item has high monetary or security value and staff cannot definitively verify ownership through claimant details or telephone follow-up, staff forward the case and physical property to the police.

### Round 2: Passenger / Claimant

1. How was it submitting the form?
Response: The passenger submitted a form for a lost wallet. They found it easy to identify because their ID was inside, and they were able to verify specific credit card numbers to complete the recovery and get the wallet back.

## Interview Synthesis Notes

*[SIMULATION] The following synthesis is based on the simulated interviews.*

The two interviews demonstrate a sharp divide between intrinsically identifiable items and generic or high-value electronic peripherals.

On the claimant side, items containing personal identification (like wallets with government IDs, student cards, or credit cards) present a smooth, low-friction recovery path. Claimants can readily confirm specific alphanumeric details, such as the name on an ID card or the last four digits of a payment card, providing definitive proof with minimal staff doubt.

On the staff side, items lacking visible personal identifiers create significant administrative friction. The staff member highlighted a lost gaming mouse as their most complicated case. Gaming peripherals often carry high retail value (frequently exceeding $100 to $200), yet their external appearance is typically uniform black plastic without visible owner names. When claimants cannot recall specific serial numbers, model variations, or unique wear patterns, staff reach an evidentiary dead end.

Because staff cannot verify ownership for expensive items through standard descriptions or phone outreach, they escalate the item to the police. This indicates that high value coupled with low identifiability forms the primary failure case for the in-house verification process.

## Coded Findings

*[SIMULATION] All findings below are drawn from the simulated interview and must be labeled as simulation evidence if referenced in project deliverables.*

1. Wallets and personal documents have a streamlined, high-confidence verification mechanism because claimants can match unambiguous credentials like photo IDs and partial credit card numbers. *[Source: direct statement in simulation]*

2. Lost-item intake forms reject generic category entries. Submissions for items like apparel must include brand, color, design, buttons, and zipper details. *[Source: direct statement in simulation]*

3. Staff use outbound telephone calls as an active fallback when claimants submit insufficient descriptive detail online. *[Source: direct statement in simulation]*

4. High-value electronics lacking personal identification, such as gaming mice, represent the most difficult category to verify because claimants rarely know serial numbers and external features look identical across units. *[Source: direct statement in simulation]*

5. When high-value items cannot be verified through submitted details or phone outreach, staff transfer both the case and physical custody to the police. *[Source: direct statement in simulation]*

6. The system currently lacks a defined verification threshold for electronics that are expensive but lack serial numbers or software accounts, forcing staff to use subjective judgment to categorize them as police matters. *[Source: analyst inference based on direct statement]*

7. Calling claimants by phone assumes staff have the time and language capacity to conduct manual interviews for every incomplete claim, which may not scale during peak transit periods. *[Source: analyst assumption]*

## Contradictions and Ambiguities

1. Verification difficulty depends on item category rather than claimant credibility. A claimant with a wallet recovers it almost instantly with card numbers, whereas a claimant with an expensive gaming accessory may face an indefinite delay and police referral simply because hardware lacks personal labels.

2. The criteria for what makes an item "high value" remain subjective. A gaming mouse can range from $30 to $250; treating it as a police matter rather than a standard lost-and-found item demonstrates that staff lack a clear price boundary or policy guideline.

3. The system requires exhaustive physical descriptions (such as zipper styles and button counts) on web forms, but the passenger's actual wallet recovery relied entirely on private contents (ID and credit card digits), suggesting that form fields should adapt to item categories rather than asking for the same physical attributes across all items.

## Follow-Up Questions

1. If two claimants report the same item model—such as two identical campus hoodies—and one recovered hoodie is visibly older or more worn than the other, what specific criteria do staff use to decide who gets which item when neither claimant documented wear conditions?
2. What fallback verification procedure applies if a claimant paid for transit or the lost item with cash, leaving no electronic transaction trail, and station CCTV footage is too degraded, obstructed, or unavailable to confirm their presence?
3. What clear dollar value or item classification officially mandates that an unverified item be turned over to the police rather than retained for standard 90-day disposal?
4. When an item like a gaming mouse is transferred to the police, does Lost & Found retain a tracking record in the system, and can the claimant still check its status online?
5. How does the system handle security and privacy when verifying credit card numbers, ensuring staff only view the last four digits rather than full card details?
6. When a passenger reports a lost electronic peripheral without a serial number, what alternative evidence (such as store receipts, box barcodes, or photos of their home desk setup) will staff accept before initiating a police transfer?
7. If an item sent to the police is subsequently claimed by its owner, does the claimant retrieve it from the local police division or through the central Lost & Found office?

