# Pet360 — Testing Plan

This plan is a proposed checklist. Mark tests as passed only after running them and recording evidence.

## UI and usability

- Confirm the UI matches the approved Figma design.
- Verify layout on supported screen sizes.
- Check text readability, contrast, touch target size, and keyboard behavior.
- Verify loading, empty, success, and error states.
- Confirm navigation does not lose important form state unexpectedly.

## Authentication and authorization

- Valid and invalid sign-in cases.
- Expired session behavior.
- Sign-out and account switching.
- User A cannot read or modify User B's pet data.
- Admin/provider permissions are checked server-side.
- Firebase security rules are tested in a safe environment.

## Pet records

- Create, read, update, and delete flows where implemented.
- Required fields and invalid values.
- Ownership checks.
- Date and numeric validation.
- Network failure and retry behavior.

## Services, orders, and appointments

- Search/filter behavior.
- Unavailable service handling.
- Date/time validation.
- Duplicate request prevention.
- Server-side total and status validation for orders.
- Cancellation and state-transition rules.

## AI demos

- Normal and empty prompts.
- Long or unsupported input.
- Timeout, rate limit, and provider error.
- Clear educational disclaimer.
- Image picker cancellation.
- Unsupported format and oversized file.
- Poor-quality image handling.
- No fabricated success result after an error.
- Privacy notice for third-party processing.

## Release checks

- No secrets in Git history.
- No debug credentials or private logs.
- Dependency and static analysis checks completed.
- Release build tested on target devices.
- Backup and rollback plan reviewed.
- Known limitations documented.

## Evidence record template

| Test ID | Scenario | Expected result | Actual result | Status | Evidence |
|---|---|---|---|---|---|
| T-01 | Open app / prototype | Entry screen appears | Fill after testing | Not run | Add screenshot or test record |
| T-02 | Select image then cancel | Returns safely to prior screen | Fill after testing | Not run | Add test record |
| T-03 | AI service unavailable | Clear error; no false result | Fill after testing | Not run | Add test record |
