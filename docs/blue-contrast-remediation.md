# Bright-blue critical text remediation plan

## Problem statement

A paid third-party database front end is used by 10 staff members. Some critical characters are rendered in bright light blue, but staff must focus on those characters to confirm that no typing mistakes were entered. Because those characters carry operational risk, they must be treated as the highest-priority contrast problem.

## Color-change policy

1. **Critical bright-light-blue characters must be changed first.** Replace them with a high-contrast color that is easy to read against the production background.
2. **Non-critical blue text is optional.** Leave it unchanged if changing it creates vendor-support risk, excessive regression testing, or confusion for staff.
3. **Do not rely on color alone.** If the third-party program allows it, add a second cue such as bold weight, underline, an icon, or a label for the critical characters.
4. **Prefer vendor-supported configuration.** Use the program's theme, field-formatting, style, or report-template settings before attempting operating-system overlays, database changes, or unsupported binary/resource edits.
5. **Keep a rollback path.** Record the old color value, the new color value, where it was changed, who approved it, and how to restore the original setting.

## Recommended replacement colors

Use one of these replacements for the critical bright-light-blue characters after checking it against the actual application background:

| Use case | Replacement | Hex | Notes |
| --- | --- | --- | --- |
| Light or white background | Navy | `#003B73` | Strong contrast while preserving a blue semantic meaning. |
| Light or white background | Black | `#000000` | Maximum readability if blue has no required meaning. |
| Dark background | Warm yellow | `#FFD166` | High visibility without using bright cyan/light blue. |
| Dark background | White | `#FFFFFF` | Maximum readability if yellow conflicts with existing warnings. |

Avoid pale cyan, sky blue, and low-saturation blue for critical characters because they are easy to miss on light backgrounds and can be difficult for users with color-vision deficiencies.

## Rollout checklist

1. Capture screenshots of the current screen containing the critical bright-light-blue characters.
2. Identify every screen, dialog, report, and print/export path where those critical characters appear.
3. Ask the vendor or check administration settings for a supported way to change the foreground color or text style for those fields.
4. Apply the change in a test environment or during a low-risk maintenance window.
5. Have at least two staff members validate that the critical characters are easier to find and read.
6. Confirm that non-critical blue text still makes sense if it is left unchanged.
7. Save before/after screenshots, configuration values, approval notes, and rollback steps.

## Acceptance criteria

The fix is acceptable when staff can reliably spot and verify the critical characters during normal data-entry work, the application remains vendor-supportable, and the team has documented rollback instructions.
