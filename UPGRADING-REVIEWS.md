# Biology Review Center: How to upgrade ONE standard

The homepage, publishing workflow, and other reviews should not be edited when replacing a single built-in lesson.

## Improve an existing interactive lesson

Change only `review-content/<code>.js` (for example, `review-content/sp1.js`).
- `hook`: motivating question
- `teach`: teaching sections
- `steps`: guided practice hints / reasoning steps
- `extra`: independent mastery questions, with code, level, prompt, correct response, three distractors, explanation

The original `reviews.js` and `reviews-extra.js` are preserved as legacy question banks. An optional `window.BIO_QUESTION_OVERRIDES[code]` can replace the legacy questions if a complete revised bank is prepared.

## Use a complete Claude-generated standalone review

1. Put the HTML in `standalone/<code>.html` (for example `standalone/ct1.html`).
2. Edit **only** `review-routes.js` to add the matching code and relative path: `CT1: 'standalone/ct1.html'`.
3. Commit those two files together. The Unit / Standard chooser automatically opens the new version.
4. Leave the existing complete Unit 2 review in its separate repository; its original link is preserved.

## Deployment safety

The existing `.github/workflows/deploy.yml` must remain unchanged.
Batch all intended file updates into one commit so it starts only one Pages deploy.
Avoid retries while an earlier Pages deployment remains in progress.

## Review status

Instructional candidate: needs teacher validation against live V1 standards, unit notes, and actual unit tests. Do not treat draft mastery checks as official standard proficiency evidence.
