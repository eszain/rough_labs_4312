# Lab 4: Simulated Requirements Elicitation

## Elicitation Objective

We want to learn how central Lost & Found staff actually verify ownership claims before releasing items. Our Sprint 0 requirements (R-008 and R-009) separate matching from verification, but we do not know what evidence staff consider sufficient, how they handle ambiguous cases, or what happens when a claimant cannot produce strong proof. This interview targets those gaps.

## Stakeholder Role

The interviewee plays a central Lost & Found staff member (STK-04 in our stakeholder register) who processes incoming recovered items, reviews candidate matches, and makes approval or rejection decisions on ownership claims.

## Interview Questions and Responses

*[SIMULATION] The following transcript records questions asked and responses given during the in-lab simulation.*

1. How does the user submit the form, and what details are needed to submit it?
Response: A generic submission like just writing "jacket" will not work. Claimants must provide a detailed form covering specific aspects: color, brand, design patterns, button types, zippers, and other specific construction features.

2. How do you verify that the user actually owns the item?
Response: Staff compare the specific details submitted on the form against the physical item in inventory. Because the public listing does not reveal these specific attributes, a match between the claimant's detailed description and the physical item confirms ownership.

3. What happens if the user does not remember the descriptive details of the item?
Response: When a claimant cannot recall specific details on the initial form, staff place a phone call to the user to talk through the item and try to draw out additional distinguishing memories or evidence.

4. What if the item is of high value and ownership cannot be verified?
Response: If an item has high monetary or security value and staff cannot definitively verify ownership through claimant details or phone follow-up, staff forward the case and the item to the police.

## Interview Synthesis Notes

*[SIMULATION] The following synthesis is based on the simulated interview.*

The interview highlighted two major operational patterns: a strict intake filter on descriptive detail, and an escalation path for unverified high-value property.

First, the staff member emphasized that standard lost-item forms cannot accept vague or generic submissions. For clothing items like jackets or bags, staff require granular details before treating the claim as actionable. These include brand names, exact color shades, closure mechanisms like zippers or specific buttons, and internal or external design marks. This granularity prevents individuals from claiming commonly lost items simply by browsing general descriptions.

Second, the verification process includes an active human fallback. Rather than issuing an immediate automated rejection when a report lacks detail, staff contact the claimant by phone. The goal is to prompt the claimant verbally to recall details they may have missed while filling out the form online.

Third, high-value items follow a separate branch when ownership remains ambiguous. If staff cannot establish ownership for high-value property through submitted details or telephone contact, they do not hold it for regular auction or disposal. Instead, the property is transferred to the police for investigation and custody.

## Coded Findings

*[SIMULATION] All findings below are drawn from the simulated interview and must be labeled as simulation evidence if referenced in project deliverables.*

1. Lost-item submissions require exhaustive physical attributes rather than broad item categories. A submission stating only "jacket" is rejected or blocked; users must provide brand, color, design, zipper style, and button details. *[Source: direct statement in simulation]*

2. Phone contact serves as the primary fallback when online submissions lack sufficient detail. Staff call claimants directly to elicit clarifying descriptions before making a rejection decision. *[Source: direct statement in simulation]*

3. High-value property with unverified ownership is escalated to the police rather than processed through standard disposal or donation channels. *[Source: direct statement in simulation]*

4. Staff rely on unpublicized form fields to verify ownership. The system must withhold design details, zipper types, and markings from public catalogs so that matching submissions serve as proof of knowledge. *[Source: direct statement in simulation; inference: public catalog views must filter out descriptive sub-fields]*

5. Police transfer introduces an external custody boundary that Sprint 0 did not document. When an unverified high-value item leaves central storage, staff need a specific system status to track transfer to law enforcement. *[Source: analyst inference based on direct statement]*

6. The staff member assumes claimants will answer phone calls from an unknown transit number, which may delay verification if calls go to voicemail. *[Source: analyst assumption]*

## Contradictions and Ambiguities

1. The requirement for exhaustive physical details conflicts with the realistic limits of passenger memory. Claimants under stress may forget button shapes or exact zipper brands, meaning that strict form validation could prevent legitimate owners from completing a claim unless staff intervene by phone.

2. The stakeholder did not define the threshold for "high value." Without a clear dollar amount or category list, deciding whether an unverified laptop, watch, or designer jacket goes to the police or into regular storage depends entirely on individual staff discretion.

3. The transition to police custody lacks a clear resolution workflow. The stakeholder explained that unverified high-value items are handed to the police, but did not specify what happens if the claimant later produces a receipt or serial number after the police transfer has occurred.

## Follow-Up Questions

1. What specific dollar amount, item category, or condition triggers the rule to forward an unverified item to the police instead of keeping it in standard lost-and-found storage?
2. When staff call a claimant to gather missing descriptions, how is that conversation logged in the system to ensure other staff members know what was discussed?
3. If an item has already been forwarded to the police and the legitimate owner subsequently contacts Lost & Found with proof of ownership, what handoff procedure exists between the transit office and the police?
4. How many failed contact attempts or days of no response occur before staff close an incomplete claim that was flagged for phone follow-up?
5. How does the online form balance requiring detailed descriptions (such as zippers and buttons) with allowing claimants who genuinely do not remember those specifics to complete their report?
