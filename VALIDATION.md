# Dev Translator validation

Build date: 2026-09-07.

Version 0.1.0.

## Method

The skill passed the bundled skill-creator structural validator. Independent subagents with fresh context read the authored skill and produced actual responses to nine realistic requests. One subagent saw only the discovery description and evaluated four routing requests. The primary agent reviewed the returned responses against intent preservation, language matching, useful terminology, uncertainty handling, prompt usability, and execution boundaries.

The screenshot trials used a synthetic 960 × 580 Projects page with a navigation header, search/filter bar, and three labeled project cards. The evaluating agent inspected the image using the image-viewing tool.

## Behavioral results

| ID | Request | Observed result | Assessment |
| --- | --- | --- | --- |
| E1 | English: profile menu options disappear behind page content | Explained dropdown, stacking order, and clipping without asserting a cause. Generated a focused prompt with visibility/clickability checks | Pass |
| E2 | English: file-copy command should continue after interruption | Explained resumable copying and generated a prompt with an interruption/resume and output-integrity check. Did not prescribe a storage mechanism | Pass |
| E3 | English: an unclear request to make the search area smaller | Asked whether the user meant width, height, surrounding space, or a combination before generating a definitive prompt | Pass |
| L1 | Arabic: text touches the inside edges of a button | Responded in Arabic, taught padding in context, produced an Arabic prompt, and gave a reusable Arabic sentence | Pass |
| L2 | Arabic explanation requested with an English prompt about a resetting dark-mode preference | Kept the lesson and reusable sentence Arabic, made only the implementation prompt English, and described preference persistence accurately | Pass |
| L3 | Spanish: three boxes should stack on a phone | Used Spanish throughout, introduced relevant English technical terms, and preserved the desktop arrangement | Pass |
| S1 | Arabic plus screenshot: “keep the thing at the top visible when I scroll” | Asked whether the target was the navigation header, Projects title, or search/filter bar. Did not choose fixed/sticky positioning | Pass |
| S2 | English plus screenshot: stack Projects cards on phones | Identified the page and actual card labels, generated a standalone prompt, and reminded the user to attach the image in another conversation | Pass |
| S3 | Request refers to a circled screenshot but no image is available | Acknowledged the missing screenshot and requested the image or a description instead of inventing its contents | Pass |

## Discovery-description results

| ID | Request | Decision | Assessment |
| --- | --- | --- | --- |
| R1 | Direct request to inspect, implement, and verify a theme-preference fix | Do not select the translator | Pass |
| R2 | Informal direct request to fix mobile boxes so they stack | Do not select the translator | Pass |
| R3 | Arabic request for help explaining mobile stacking and learning its name | Select the translator | Pass |
| R4 | Explicit `$dev-translator` invocation followed by “Fix the text touching the button edges” | Select the translator | Pass |

## Live-use evidence

After installation, `dev-translator` appeared in the Codex conversation's available-skills catalog. Following instructions for testing it in that conversation, the user reported that it was working successfully. This is user-reported live-use evidence, recorded separately from the controlled behavioral trials. The exact request, response, model, and application version were not captured.

Native Claude Code invocation has not been verified end to end. Installation layout and file contents were checked, which does not establish runtime behavior in Claude Code.

## Release packaging checks

The 0.1.0 release preparation includes the MIT license in the repository and installable skill, public installation instructions, complete illustrative English and Arabic examples, and explicit compatibility evidence.

- Both documented installation commands passed on macOS against an isolated temporary user-directory layout, including a repeated installation to check updates and folder nesting.
- Local documentation links resolved. The public files contained no machine-specific absolute paths or unfinished scaffold markers.
- The repository and bundled skill license notices matched, and the version and license metadata passed validation.
- The skill's behavior rules match the version used in the nine behavioral trials. Later edits only adjusted punctuation.
- An independent read-only release review found no blockers and verified the external installation documentation links.

These are packaging and review checks, not additional behavioral trials. Installed copies and distribution archive contents are compared with the source during export.

## Limits

These are nine behavioral trials and four metadata routing checks, not measured success rates across models or users. They validate responses generated from the skill and a review of its discovery description. They do not prove that a particular host will always activate it automatically.

The controlled trials did not exercise native host invocation end to end. The separate Codex catalog observation and user-reported live success are described above. Local installed files and the exported package are checked separately for structure and identical contents. Speech input follows the host-provided transcript. Audio transcription itself was not tested. English, Arabic, and Spanish were exercised. Support for other languages is an instruction rather than an exhaustive validation claim.
