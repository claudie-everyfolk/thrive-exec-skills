# Scheduling Rules — Thrive Market Member Services

## Shift Rules

1. **5-day max consecutive**: No agent may work more than 5 consecutive days without a day off.
2. **Weekly hour caps**: Respect each agent's `max_hours_week` from the roster. No exceptions without overtime approval.
3. **Minimum rest between shifts**: At least 10 hours between the end of one shift and the start of the next.
4. **QA agents weekday only**: Agents with role `QA` work Monday through Friday only. No weekend scheduling.
5. **Leads must overlap**: Lead agents must have at least 2 hours of overlap with a minimum of 2 L1 agents on the same channel during their shift.

## Coverage Rules

6. **Minimum 2 per channel**: At all times during operating hours (8:00 AM - 11:00 PM ET), there must be at least 2 agents assigned to each active channel (chat, voice, email).
7. **Peak hour staffing**: During peak hours (flagged in coverage_requirements.csv), coverage must meet or exceed the `min_*_agents` values. No exceptions.
8. **Bilingual priority for voice**: During peak hours, at least 50% of voice-assigned agents must be Bilingual or Spanish-speaking.
9. **Weekend minimum**: Weekend coverage must maintain at least 60% of weekday peak staffing levels for chat and voice.

## Site-Specific Rules

10. **HQ operating hours**: HQ agents work between 08:00 and 20:00 ET only.
11. **Manila operating hours**: Manila agents can be scheduled between 20:00 and 08:00 ET (overnight coverage) OR 08:00-17:00 ET (daytime overlap). No split shifts.
12. **Bogota operating hours**: Bogota agents work between 08:00 and 22:00 ET.
13. **New agent restriction**: Agents with less than 30 days tenure (hired after March 20, 2026) should not be scheduled for voice channel during their first 2 weeks on the floor.

## PTO and Preferences

14. **PTO is absolute**: If an agent has a date in `days_off_requested`, they cannot be scheduled that day. No overrides.
15. **Shift preferences are soft**: Prefer to honor `shift_preference` (morning/mid/evening/flexible) but coverage needs take priority.
16. **Flexible agents fill gaps**: Agents marked `flexible` should be used to fill coverage gaps before overriding other agents' preferences.

## Escalation

17. **Understaffing alert**: If any hour falls below minimum coverage for any channel, flag it in the output. Do not silently leave gaps.
18. **Overstaffing warning**: If any hour exceeds 150% of required coverage, flag it as potential overstaffing for cost review.
