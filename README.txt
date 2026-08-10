SMASH HOUSE — GITHUB PAGES DIRECT-LAUNCH BUILD v2

This build lets one artwork contain pieces from more than one smashed object.

WHAT CHANGED
- Choosing another breakable item no longer clears the pieces already collected.
- Each item remembers its own partial damage if the user switches away and back.
- A broken item is marked with the number of pieces it added to the room.
- The current smash target appears above collected pieces while it is being hit.
- After it breaks, the target disappears and all old and new pieces remain usable.
- Auto Art arranges every collected piece, including mixed pieces from several
  objects, throughout the full room.
- Saved Mission Gallery artwork includes every collected object and every piece.
- RESET remains the only control that clears the complete room and starts over.
- The initial page no longer requests every object and shard at once. The
  selected object loads first; remaining artwork is cached in small background
  batches so One Home can open the game sooner.
- Duplicate image requests are joined instead of downloading the same asset
  more than once.
- A verified One Home session pauses additional hits while the server confirms
  the current hit. If verification stops, the game and One Home both show an
  error instead of continuing with misleading green status.

PROTECTED WORK THAT DID NOT CHANGE
- The approved Vase still breaks into exactly the same 20 artwork-only pieces.
- All 20 approved Vase piece files are byte-for-byte unchanged.
- White fracture lines remain removed.
- Progressive damage and transparent backgrounds remain fixed for every object.
- Piece appearance, size, dragging, rotation, layering, and touch targets remain
  unchanged.

GITHUB UPLOAD
1. Download and unzip the GitHub package.
2. Open the existing Smash-House repository on GitHub.
3. Select Add file, then Upload files.
4. Drag every extracted file and folder into the repository root. The ZIP is
   intentionally root-ready: index.html and the assets folder belong together.
5. Commit the upload and wait for GitHub Pages to publish it.
6. Do not upload only index.html. The nested assets/vase-damage-v3 and
   assets/vase-pieces-v3 folders are required.

EXACT TEST
1. Open https://rare-ink-studio.github.io/Smash-House/ in a private window.
2. Open the new deployment and choose Vase.
3. Hit Vase five times and confirm exactly 20 Vase pieces appear.
4. Choose Mug. Confirm all Vase pieces stay in the room and Mug appears as the
   next smash target.
5. Hit Mug twice, switch to Camera, then switch back to Mug. Confirm Mug returns
   with its first two hits still showing.
6. Finish breaking Mug. Confirm its pieces are added without removing any Vase
   pieces and the total PIECES number increases.
7. Break Camera and Blue Mug. Confirm each new set joins the same artwork.
8. Press AUTO ART. Confirm all mixed pieces spread throughout the room rather
   than forming one center pile. Drag and rotate pieces from different objects.
9. Press SAVE. Open the Mission Gallery result and confirm all mixed pieces are
   present.
10. Press RESET only after the test. Confirm RESET clears the complete session.
11. Repeat the same test on a phone.

Piece-resizing controls are not included in this isolated build.

After this GitHub test passes, deploy the matching One Home v13.99 Edge Function
and Netlify package. All three layers must be on their matching versions.
