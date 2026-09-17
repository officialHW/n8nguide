# Publishing the guide

## Recommended public experience

1. Visitor opens the guide.
2. Visitor reads the guide.
3. Visitor reaches the review section.
4. Visitor submits a short review.
5. The confirmation page or workflow reveals the download link.

## Why use an external gate?

A Notion page can present the guide and link to a review form, but a strict `review submitted → download unlocked` flow requires a system that can verify the form submission before serving the downloadable file.

Suitable implementations can use:

- A form platform with a post-submit redirect.
- A landing-page builder with form gating.
- A small serverless endpoint that records the submission and returns a signed/temporary download URL.

## Keep the review lightweight

Ask for only what is useful, for example:

- What was most useful?
- What could be clearer?
- What would you like in the next guide?

Avoid making the review gate unnecessarily intrusive.

## Repository assets

Keep downloadable files and visual assets in version-controlled folders so the published guide can be updated without losing the source materials.
