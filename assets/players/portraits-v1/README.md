# Player portraits v1

Created: 2026-09-10. Built-in image_gen tool.

Asset: sheet.png. Verified 1254 x 1254 RGB PNG, 6 x 6 = 36 portraits.
Each equal cell is 209 x 209 pixels. The selected sheet has an opaque light background.
This original art sheet is preserved unchanged. The game now uses src/ui/player-portrait-assets/ with a transparent detail layer and four independent clothing masks (cap, jersey, brim, trim). See docs/club-appearance/README.md for the current 40-color uniform/logo editor; docs/portrait-implementation/README.md records the first implementation.
Faces are fictional, not likenesses of named real players.

Implemented 2026-09-10: all 36 portraits were separated into background, detail, primary, secondary and point regions. Preserve face/hair and clothing shading; recolor only masked clothing from a team palette. Preview at 44/48 pixels using two team colors before expanding to 36 faces.
Use a stable portrait ID per player; only the palette changes on transfers.
Team-colored variants can be generated and cached in code rather than maintaining a separate sheet for every team.
SVG masks are optional; embedding this PNG in SVG does not convert it to editable vector art.
Keep this original sheet unchanged.

The first transparent generation contained edge artifacts, so a background cleanup edit was selected.
Actual file properties above take precedence over requested output properties in the prompts below.

## Generation prompt

Use case: stylized-concept.
Asset type: a single production-oriented baseball player portrait atlas / sprite sheet for a Korean mobile baseball club management game.
Primary request: create exactly THIRTY-SIX distinct adult male professional baseball player portraits, in an EXACT 6 columns by 6 rows grid, one portrait per equal square cell. This is the first art-direction sheet in a restrained, clean 2D sports manga / sports comic illustration style (담백한 스포츠 만화풍). It must look like one coherent artist drew all 36.
Canvas and framing: square canvas, as high resolution as available, ideally 3072 by 3072. Divide the entire canvas conceptually into 6 equal columns and 6 equal rows, with NO drawn grid lines. Each portrait centered within its own cell, the same scale, same baseline and eye line. Each has an even generous clear margin within its cell; no overlap or touching neighboring cells; no clipping of caps or shoulders. Head and short neck, with only a small upper-shoulder jersey bust, not half-body figures. The face and cap together occupy about 76% of each cell height. Uniform front-facing near-frontal pose, visible both eyes and ears, consistent cap fit. Favor large readable head silhouettes and simple facial features recognizable at 40–48 pixel thumbnail size.
Style: handsome but varied and believable adult athletes, mature restrained cartoon proportions, subtly enlarged heads, clearly inked clean dark warm-charcoal outlines, simple flat color and one firm cel-shadow tone, economical detail. Friendly, calm, grounded, modest sports comic aesthetic suitable for a soft cream and sage-green management UI. Natural eyes, no oversized anime eyes. No chibi baby proportions. No photorealism, 3D, painterly textures, gradients, heavy highlights, dramatic lighting, collectible-card effects, shiny plastic, sketch construction marks, or noisy hatching.
Character variation: predominantly Korean / East Asian ballplayers with a small handful of visibly varied international ballplayers, all fictional and no specific real person likeness. Adults roughly early 20s through late 30s. Make all 36 recognizably different using face outline, jaw width, cheek shape, eyebrow shape and thickness, eye shape, nose silhouette, ears, subtle hairstyle visible below the cap, and selected clean-shaven versus light stubble or short facial hair. Include lean and broad-faced athletes and youthful and mature faces. Balanced quiet confident expressions: neutral, slight smile, focused; avoid exaggerated grimaces. Natural varied skin tones. Do NOT change art style or head scale between rows.
Palette-swap preparation: every player wears the SAME plain unbranded baseball cap and matching simple jersey collar/bust silhouette. All cap fabric, visor and jersey fabric must be ONLY neutral achromatic grays, with a very limited flat palette: light-gray base, middle-gray shadow, charcoal outlines, and off-white trim. Keep skin and hair naturally colored, clearly bounded and visually distinct from uniform regions. Absolutely NO logos, letters, team names, colored badges, stripes, patterned fabrics, embroidery or sponsor marks. The neutral cap and jersey are intentionally prepared for later team-color masks; do not tint the entire portrait monochrome.
Background: genuinely transparent alpha behind and between every isolated portrait, with no checkerboard illustration, no white tile rectangles, no decorative shapes or drop shadows.
Text: none anywhere. No title, labels, cell numbers, watermark or signatures.
Critical checks: exactly 6 across AND exactly 6 down = 36 complete unique portraits. Perfectly regular equal-cell layout, uniform eye height, matching cap placement, crisp economical art, calm sports comic identity, genuinely transparent background. This is an asset atlas, not a presentation page.

## Cleanup prompt

Edit the attached generated 6 by 6 baseball portrait atlas. Preserve exactly all 36 portraits, all facial identities, the same positions, grid, eye lines, scale, cap shapes, grayscale uniforms and sports-comic drawing style. This is strictly a background cleanup pass. Remove every stray red, yellow, white and black speck, fragment, halo, debris and unwanted edge artifact outside the intended portrait silhouettes, including the gaps between rows and columns. Replace ALL transparency/background with a perfectly uniform opaque warm off-white solid color #F4F6EF across the entire canvas; no texture, no gradient, no shadows, no checkerboard, no transparency. Portrait contours must be clean and smooth, with no fringe. Keep facial skin, hair, cap gray colors, jersey colors, and facial linework inside silhouettes unchanged. Do not add, remove, resize, shift or redraw any player. No text, labels, numbers, frames or grids. Exactly six columns and six rows of complete, cleanly separated portraits on flat off-white.

