# CV Content Sync Design

## Intent

Update the existing academic website from the September 2026 CV while preserving the current visual design, page structure, and research narrative.

## Goals

- Keep the website email address unchanged.
- Keep the existing homepage structure and prose unless a factual employment correction is required.
- Update the global CV download to a September 2026 PDF generated from the supplied DOCX.
- Synchronize the Publications page with the CV's current publications, preprints, awards, and professional service.
- Preserve the existing Jekyll layout, styling, images, and all unrelated pages.
- Rebuild locally and verify that the homepage, image assets, Publications page, and CV link still work.

## Non-goals

- Do not add a full CV page.
- Do not add the CV's complete invited-talk, teaching, mentoring, education, or skills sections.
- Do not redesign the site or rewrite its research-topic narrative.
- Do not change the website's existing contact email.

## Chosen approach

Use a minimal factual synchronization. The supplied CV is the source of truth for publication status, preprints, awards, and service, while the user's explicit instruction overrides it for the website email. Replace the old CV download with a clearly versioned September 2026 PDF, update the existing sidebar link, and make only targeted Markdown changes.

## Alternatives considered

- **Minimal factual synchronization — chosen:** Lowest risk and keeps the current site recognizable.
- **Full CV-derived rewrite:** More complete, but would make the Publications page much longer and change the site's purpose.

## Acceptance criteria

- The displayed website email is byte-for-byte unchanged.
- The sidebar CV link resolves to the new September 2026 PDF.
- The 2026 Nature paper appears under selected publications rather than preprints.
- The CV's current preprints, Washington Research Foundation finalist entry, and professional-service list appear on the Publications page.
- Jekyll builds without warnings or errors.
- All local links and referenced assets resolve with exact filename casing.

