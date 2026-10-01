# Lab 4: Simulated Requirements Elicitation

## Elicitation Objective

We want to learn how central Lost & Found staff actually verify ownership claims before releasing items. Our Sprint 0 requirements (R-008 and R-009) separate matching from verification, but we do not know what evidence staff consider sufficient, how they handle ambiguous cases, or what happens when a claimant cannot produce strong proof. This interview targets those gaps.

## Stakeholder Role

The interviewee plays a central Lost & Found staff member (STK-04 in our stakeholder register) who processes incoming recovered items, reviews candidate matches, and makes approval or rejection decisions on ownership claims.

## Draft Question Set

1. Walk me through what happens from the moment a recovered item arrives at your facility until it is either returned or disposed of.
2. When a passenger contacts you about a lost item, what information do they usually give you? How often is it enough to narrow things down?
3. How do you decide whether a found item and a lost report are probably the same item? What attributes matter most?
4. What does a typical ownership verification look like? What evidence do you ask the claimant to provide?
5. Have you had cases where two people claimed the same item? How did you handle that?
6. What happens when a claimant gives a description that mostly matches but gets one detail wrong, like the color or brand?
7. Are there item categories where verification is harder or easier? For example, a phone with a lock screen versus a plain umbrella.
8. How do you handle items that might be unsafe, like leaking batteries or unlabeled medication?
9. Do you ever have items pile up because nobody claims them? What triggers the decision to dispose of them, and who makes that call?
10. Is there anything about the current process that slows you down or causes mistakes that a new system should fix?

## Interview Notes

*[SIMULATION] The following notes are from a simulated elicitation exercise. They do not represent real stakeholder testimony and must not be cited as validated evidence.*

The interview focused on how a central Lost & Found staff member handles the path from item intake to return or disposal. The simulated stakeholder described receiving items from station CSAs and transit operators, usually in batches that arrive by internal courier once or twice per day. Each item already has a tag from whoever logged it initially, but the tag quality varies. Operators tend to write short entries like "black backpack, Line 2, Tuesday morning," while CSAs sometimes add more detail because they have a counter and a few extra minutes.

When a passenger calls or files a report, the staff member pulls up recent found-item records matching the general category and date range. The stakeholder said most passengers remember the item type, color, and approximate time, but they often get the station or route wrong. Location data alone is unreliable because items move through the system before reaching central storage. The more useful matching attributes are distinctive marks: a scratch on a laptop lid, a keychain on a bag, a cracked phone screen.

For verification, the stakeholder described asking claimants to name something about the item that was not in the public catalog listing. The public listing deliberately omits details like brand, serial number, lock screen image, and bag contents. If a claimant can name two or three hidden details, the staff member considers that sufficient for most standard items. For high-value items like laptops or jewelry, they sometimes ask for a receipt, a photo on the claimant's phone showing them with the item, or a serial number match.

The stakeholder mentioned that duplicate claims happen occasionally, maybe a few times per month. When two people describe the same item convincingly, the staff member puts both claims on hold and asks each claimant for additional proof. There is no written policy for this; the staff member uses judgment and consults a supervisor if needed.

On unsafe items, the stakeholder said leaking batteries or open containers get flagged immediately and stored separately. They do not keep perishable food. Unlabeled medication is held for the retention period but staff avoid opening containers. There is no formal hazardous-materials protocol specific to lost property.

For unclaimed items, the 90-day retention window (per municipal code) is the trigger. After 90 days, items are batched for auction or donation. The decision to dispose is logged but the stakeholder said the current paper trail is minimal and they sometimes lose track of exact intake dates for items that arrived without a proper timestamp.

## Coded Findings

*[SIMULATION] All findings below are drawn from a simulated elicitation conversation. They must be labeled as simulation evidence if used in project requirements.*

1. Staff match items primarily by distinctive physical marks (scratches, stickers, accessories, case color) rather than by loss location. Passengers frequently misremember which station or route they were on, so location is treated as supporting, not primary. *[Source: direct statement in simulation]*

2. Ownership verification relies on the claimant naming details excluded from the public catalog, such as brand, serial number, lock screen content, or bag contents. Two or three correct hidden details are generally considered sufficient for standard items. *[Source: direct statement in simulation]*

3. High-value items (laptops, jewelry, phones with identifiable serial numbers) require stronger proof than standard items. Staff may request purchase receipts, photos showing ownership, or serial number confirmation. *[Source: direct statement in simulation]*

4. There is no written policy for resolving competing claims on the same item. Staff put both claims on hold and escalate to a supervisor based on personal judgment. *[Source: direct statement in simulation; inference: this is a gap that could lead to inconsistent decisions across staff members]*

5. Intake timestamps are sometimes missing or inaccurate because items arrive in batches from operators who logged them with vague time references. This causes problems when tracking the 90-day retention window. *[Source: direct statement in simulation; inference: the system should enforce a timestamp at every custody transfer to avoid ambiguity in retention deadlines]*

6. Hazardous or perishable items have no formal handling protocol beyond physical separation from regular storage. Staff use ad hoc judgment about what counts as unsafe. *[Source: direct statement in simulation; assumption: a real transit authority would likely have a policy, but staff may not be applying it consistently]*

7. Tag quality from initial intake varies by role. Operators write shorter, less detailed entries than CSAs because operators have less time during active shifts. *[Source: direct statement in simulation; inference: intake forms should have mandatory fields to set a minimum data quality floor without requiring lengthy entries]*

## Contradictions and Ambiguities

1. The stakeholder described the 90-day retention window as a hard rule from the municipal code, but also said staff sometimes lose track of intake dates. If intake timestamps are unreliable, staff cannot enforce the retention period consistently. This creates a gap between stated policy and actual practice.

2. The stakeholder said two or three hidden details are "sufficient" for standard items, but also said high-value items require stronger proof. The boundary between standard and high-value is not defined anywhere. A mid-range item (e.g., a $200 pair of headphones) could be treated either way depending on who is on shift.

## Follow-Up Questions

1. When two claimants both provide convincing hidden details for the same item, what specific criteria does the supervisor use to resolve the dispute? Is the decision ever documented?
2. What happens if a claimant correctly identifies the item but cannot produce a receipt or serial number for a high-value item? Is there a threshold below which weaker evidence is accepted, or is the claim rejected outright?
3. If an item tagged as medication turns out to be a controlled substance, does the current process involve notifying transit police or another authority, or does it stay in lost-property storage for the full 90 days?
4. How often do items arrive at central storage with no intake timestamp at all? When that happens, does staff estimate the date, use the courier delivery date, or leave it blank?
5. Has a claimant ever disputed a rejection and escalated beyond the Lost & Found office? If so, what process handled the appeal?
6. For items found on vehicles, does the transit operator's shift report or vehicle log provide a backup timestamp that could be cross-referenced, or is the operator's manual entry the only time record?
7. Are there seasonal or event-driven spikes in volume (e.g., after a major event at a downtown station) that overwhelm the current matching and verification process? If so, how does staff cope?
