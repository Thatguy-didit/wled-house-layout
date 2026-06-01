# Compliance Notes For Customer Installations

This is a practical checklist for distributing controllers flashed with this
modified WLED firmware. It is not legal advice.

WLED is licensed under the EUPL v1.2 or later. The license allows modification
and distribution, but customer-distributed firmware should be accompanied by
license, attribution, modification, and source-code availability notices.

## Required Practical Steps

1. Keep the original WLED copyright and license files in this repository.
2. Keep this repository public, or otherwise make the exact source code
   available to customers.
3. Put the public source URL in customer handoff materials.
4. State clearly that this is a modified WLED build.
5. Do not imply this build is official WLED.
6. Do not add terms that restrict customers from exercising the EUPL rights
   for the WLED-derived firmware.
7. Keep third-party license notices from the original WLED repository.

## Recommended Public Repo Setup

Create a public repository, for example:

`https://github.com/Thatguy-didit/wled-house-layout`

Push this source tree there, then create a release/tag for each firmware you
install for customers.

See `GITHUB_SETUP.md` before pushing. This working tree may still have the
official WLED repository configured as `origin`, and your modified source should
go to your own public repository or fork.

Suggested tag format:

`wled-16.0.0-house-layout-v1`

## Customer Notice

Give each customer either a printed note, invoice note, support page, or QR
code that points to the source repository. Use `CUSTOMER_SOURCE_NOTICE.md` as
the starting text.

## If You Ship A Firmware Binary

If you publish or send a `.bin` file, publish or provide the matching source
for that exact binary. The easiest workflow is:

1. Commit the source.
2. Tag the commit.
3. Build the firmware from that tag.
4. Attach the `.bin` to the tagged GitHub release.
