# Zendesk WFM CSV Upload Schema

## File Format
- File type: CSV (comma-separated values)
- Encoding: UTF-8
- Header row: Required
- One row per agent per day (an agent working Monday through Friday = 5 rows)

## Required Columns

| Column | Format | Description | Example |
|---|---|---|---|
| `agent_id` | String | Unique agent identifier matching Zendesk user ID | `AGT-001` |
| `date` | `YYYY-MM-DD` | The scheduled work date | `2026-04-20` |
| `start_time` | `HH:MM` (24-hour) | Shift start time in ET (Eastern Time) | `09:00` |
| `end_time` | `HH:MM` (24-hour) | Shift end time in ET (Eastern Time) | `17:30` |
| `break_start` | `HH:MM` (24-hour) | Break start time in ET | `12:00` |
| `break_end` | `HH:MM` (24-hour) | Break end time in ET | `12:30` |
| `role_assignment` | String | Channel/role for this shift | `chat` |

## Validation Rules

1. **Date format**: Must be `YYYY-MM-DD`. No other formats accepted.
2. **Time format**: Must be `HH:MM` in 24-hour format. No AM/PM. Leading zeros required (e.g., `08:00` not `8:00`).
3. **Break requirement**: Shifts longer than 6 hours MUST include a break. Break duration must be exactly 30 minutes.
4. **Break timing**: Break must start at least 2 hours after shift start and end at least 2 hours before shift end.
5. **Shift length**: Minimum shift is 4 hours. Maximum shift is 10 hours (including break).
6. **Role assignment values**: Must be one of: `chat`, `voice`, `email`, `social`, `qa_review`, `lead_support`
7. **Agent ID**: Must match an existing agent in the Zendesk system. IDs are case-sensitive.
8. **No overlapping shifts**: An agent cannot have two rows for the same date.
9. **Time zone**: All times are in Eastern Time (ET). BPO sites must convert their local times to ET.

## Optional Columns

| Column | Format | Description |
|---|---|---|
| `notes` | String | Free-text notes visible to the agent | 
| `overtime_flag` | Boolean (`true`/`false`) | Whether this shift is overtime |

## Sample Rows

```csv
agent_id,date,start_time,end_time,break_start,break_end,role_assignment
AGT-001,2026-04-20,09:00,17:30,12:30,13:00,chat
AGT-002,2026-04-20,08:00,16:30,12:00,12:30,voice
AGT-003,2026-04-20,13:00,17:00,,,email
AGT-004,2026-04-20,10:00,18:30,14:00,14:30,chat
```

Note: For shifts of 6 hours or less, `break_start` and `break_end` can be left empty.

## Upload Notes
- Maximum 500 rows per upload
- Uploading a schedule for a date that already has entries will OVERWRITE the existing schedule for those agents on that date
- Upload endpoint: Zendesk Admin > WFM > Schedules > Import CSV
