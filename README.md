ERROR HANDLING:
1. If a tool fails: Try once more with different parameters
2. If it fails twice: Stop and report the failure
3. When reporting, include:
   - Exact error message
   - What you were trying to do
   - Suggest what the user should do next

EXAMPLE:
ACTION: send_email("john@gmail.com", "Refund Confirmation", "Your $50 refund has been processed")
OBSERVATION: Error — "Email delivery failed"

THOUGHT: Email might be wrong. Let me verify the customer ID and try a different email.
ACTION: search_database(12345) → email is actually "john.smith@gmail.com"
ACTION: send_email("john.smith@gmail.com", "Refund Confirmation", "Your $50 refund has been processed")
OBSERVATION: Success — Email sent

IF that also failed:
STOP and REPORT: "Email delivery failed twice. The customer's email may be invalid. Suggest asking customer for correct email before retrying."
