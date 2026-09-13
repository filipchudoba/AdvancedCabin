# Advanced Cabin

Advanced Cabin adds configurable passenger seats, overhead panels, oxygen masks,
an enhanced FAP and AnyAirline seatback IFE to X-Plane 12.

[Download version 1.0.0](https://github.com/filipchudoba/AdvancedCabin/releases/tag/v1.0.0)
 · [AnyAirline IFE provider](https://anyairline.app/)

> **Loading seats:** Seats may take up to about **one minute** to appear in X-Plane. Please allow the cabin to finish loading.

## Before downloading

Version 1.0.0 supports **already prepared Advanced Cabin ToLiss A319/A320/A321
installations**. Aircraft object attachments, click regions and sound integration
are required; this package does not retrofit an untouched ToLiss aircraft.
A339/A346 support is not included in this release.

Use the plugin to fly, Cabin Studio to create layouts and liveries, and the
optional PSD paintkit to paint textures in Photoshop or another PSD editor.
Download only the products you need. This repository contains the user guide
and downloadable releases.

## Downloads

- [Native X-Plane plugin — all operating systems](https://github.com/filipchudoba/AdvancedCabin/releases/download/v1.0.0/AdvancedCabin-Plugin-all-platforms.zip)
- [PSD paintkit](https://github.com/filipchudoba/AdvancedCabin/releases/download/v1.0.0/Advanced-Cabin-Paintkit.zip)
- [Cabin Studio — Windows x64](https://github.com/filipchudoba/AdvancedCabin/releases/download/v1.0.0/Cabin-Studio-windows-x64.zip)
- [Cabin Studio — Linux x64](https://github.com/filipchudoba/AdvancedCabin/releases/download/v1.0.0/Cabin-Studio-linux-x64.zip)
- [Cabin Studio — macOS Apple Silicon](https://github.com/filipchudoba/AdvancedCabin/releases/download/v1.0.0/Cabin-Studio-macos-arm64.zip)
- [Cabin Studio — macOS Intel](https://github.com/filipchudoba/AdvancedCabin/releases/download/v1.0.0/Cabin-Studio-macos-x64.zip)

<a href="https://buymeacoffee.com/filipchudoba"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Support the project — Buy Me a Coffee" height="40"></a>

## Current limitations

External apron lighting can still reach some instanced cabin objects. The independent IFE backlight fix does not provide fuselage light isolation. The new IFE appearance needs an in-simulator visual check.


## User guide

[Public downloads](https://github.com/filipchudoba/AdvancedCabin/releases/latest)
 · [Online guide](https://github.com/filipchudoba/AdvancedCabin#readme)

## Choose your download

| Download | Purpose | Location |
| --- | --- | --- |
| `AdvancedCabin-Plugin-all-platforms.zip` | Native plugin: Windows, Linux and universal Intel/Apple Silicon macOS binaries together | X-Plane `Resources/plugins` |
| `Cabin-Studio-windows-x64.zip` | Windows desktop editor | Outside X-Plane |
| `Cabin-Studio-linux-x64.zip` | Linux desktop editor | Outside X-Plane |
| `Cabin-Studio-macos-arm64.zip` | Apple Silicon desktop editor | Applications |
| `Cabin-Studio-macos-x64.zip` | Intel Mac desktop editor | Applications |
| `Advanced-Cabin-Paintkit.zip` | Layered PSDs and starter cabin folder | Your artwork folder |

Only the plugin is needed to use an existing cabin. Studio and the paintkit are
optional authoring tools. Studio includes its own export engine; users do not
install or link Blender, Python or Node.js. The native plugin contains none of
those programs. The paintkit has 4K source artwork; texture resolution is not
part of the livery folder name.

**Compatibility:** prepared Advanced Cabin ToLiss A319/A320/A321 installations.
Aircraft object attachments, click regions and sound integration must already
be installed. This ZIP alone does not convert an untouched ToLiss aircraft.
A339/A346 work is deferred. Automated checks cover the repaired native plugin;
the performance repair has been confirmed in X-Plane; the new IFE lighting still needs visual confirmation.

> **Loading seats:** Seats may take up to about **one minute** to appear in X-Plane. Allow the cabin to finish loading.

## 1. Install or update the plugin

Close X-Plane. Back up `Resources/plugins/AdvancedCabin` outside X-Plane, then
replace it with the complete `AdvancedCabin` folder from the plugin ZIP:

```text
X-Plane 12/
  Resources/plugins/AdvancedCabin/
    64/
      win.xpl
      lin.xpl
      mac.xpl
    data/
    ...
```

Keep every file. X-Plane chooses the binary automatically. Avoid an extra nested
`AdvancedCabin/AdvancedCabin` folder. Disable previous Advanced Cabin Python or
embedded-host copies before starting: two implementations must not run together.
Keep XPPython3 if another add-on needs it; the native plugin does not require it.
The AnyAirline Connector and `AnyAirline_IFE/feed` folder are separate IFE services,
not duplicate Advanced Cabin installations.

Use X-Plane 12 exposing SDK 4.2 or later. Windows/Linux are x86-64; macOS is
universal. Preview Mac binaries are ad-hoc signed, not Apple-notarized. Approve
only the downloaded app/plugin you trust through normal OS security controls.

## 2. Install a cabin livery

Put **advanced cabin** inside **objects** of the aircraft's external livery:

```text
Aircraft/<aircraft>/liveries/<livery>/objects/advanced cabin/
  layout.json
  profile.json
  manifest.json
  objects/
    seatgen_type1_ALB.png
    business_ALB.png
    lie-flat_ALB.png
    ...
```

Keep exported filenames and case, especially on Linux. Paths with spaces and
Unicode are supported. Do not add `2k`, `4k` or `miq` directories. The inner
`objects` folder contains textures, not seat geometry.

Selecting that external livery loads its cabin automatically. Put Turkish cabin
artwork only in a Turkish livery; other liveries use default colors unless they
provide their own customization.

Only **layout.json** is needed for configuration with default textures. A full
custom appearance also needs **profile.json**, **manifest.json** and its textures.
JSON alone does not contain painted images. Keep complete exports together.

## 3. Use Cabin Studio

Extract the complete OS-specific ZIP. On Windows launch `Cabin Studio.exe` from
the extracted folder. On macOS copy `Cabin Studio.app` to Applications. On Linux
use an archive manager preserving Unix permissions and symbolic links, then
launch `Cabin Studio`. Linux needs a graphical desktop and Qt/WebEngine system
libraries; Windows uses WebView2 and macOS uses WebKit. The preview needs WebGL.

Studio opens in its own window. An external browser, X-Plane installation and
manually linked helper programs are not required for editing.

1. Start with A319, A320 or A321, or drag in a cabin ZIP, `layout.json` or an
   `advanced cabin` folder. **Open file / Open folder** is available too.
2. Choose seat types, screens and overhead panels. Add cabin sections, choose
   business row counts and place the curtain/partition. Studio validates space
   and keeps a local draft.
3. Adjust colors or drop artwork into **Magazine**, **Safety card** or
   **Advertisements**. Magazine and safety-card artwork are separate inputs.
4. Open **Export cabin**. **Export layout.json** saves configuration without new
   textures. **Export cabin folder** prepares the full cabin, then opens the
   destination dialog. A completed build can be saved again without rebuilding.
   Older Studio packages label these actions **Export JSON only** and **Export cabin**.
5. Install the result in the livery's `objects` folder.

Exports run locally. Keep Studio open until the build finishes. Existing
destination cabin folders are backed up before saving; the imported source
package is not edited in place.

**Manual paints:** configuration-only changes retain imported textures. Changing
Studio colors or artwork requires rebuilding textures and can replace manual
paint. Use **Export layout.json** for row changes when keeping painted PNGs. The
current preview shows editor colors/equipment, not all imported painted images;
verify final artwork in X-Plane.

## 4. Use the PSD paintkit

The paintkit contains nine layered PSDs, original maps and a portable
`advanced cabin` starter folder. Studio is optional for this workflow.

1. Open the PSD matching the target texture. For example,
   `seatgen_type1_ALB.psd` exports to `advanced cabin/objects/seatgen_type1_ALB.png`.
2. Keep **Original texture** visible. Enable the relevant **Colour** layer,
   lock transparent pixels and fill it. Preserve its alpha, which isolates the
   material. Color blending keeps underlying shading/details. Use the matching
   mask with Levels/Curves when changing brightness.
3. Export RGB PNG under the original filename, replacing that livery texture.
   PSDs and guide layers stay outside X-Plane. Manifest checksums do not need to
   be recalculated after painting.

Economy masks target default **Contoured / pattern 0** and the shared color atlas.
Do not use them on another UV atlas, upholstery pattern or individual-seat color
atlas. Recliner and lie-flat business seats have separate PSDs.

`ALB` is color. `NRM` contains special normal/surface-property channels and is not
for ordinary recoloring. `LIT` controls lit/night appearance: update it too after
a major color change if the old color remains at night. Original maps are included
for recovery. Export resolution can vary without renaming folders; larger maps
use more memory.

## 5. Edit layout.json by hand

Use UTF-8 in a plain-text editor and back up the original. JSON has no comments
or trailing commas. **example-layout.json** is a full A321 example with two
business rows and a curtain at the class boundary. Use the appropriate aircraft
layout in Studio when creating a different cabin.

| Field | Meaning |
| --- | --- |
| `equipment.seats.family` | `0` original ToLiss; `1` Type 1; `2` lowcost small table; `3` lowcost inset table |
| `equipment.seats.ife` | `0` none; `1` modern touch screen; `2` classic buttons. Economy IFE requires Type 1 |
| `equipment.seats.live` | Live AnyAirline feed for installed seat screens |
| `equipment.overhead.style` | `-1` auto; `0` original; `1` Classic CEO; `2` CEO/NEO; `3` Latest NEO |
| Business section `type` | `miq` recliner; `solo` lie-flat. Compatibility IDs remain in JSON only |
| Section `rows` / `pitch` | Row count / row pitch in meters; spatial limits still apply |
| Separator `type` | `none`, `curtains`, `partition` |
| Separator `position` | `after-business` follows the class boundary automatically |

For compatibility, `position: "economy-row"` and its `row` count within economy
in JSON. Studio/FAP display the continuous cabin row number. Prefer
`after-business` for the class boundary. Preserve other aircraft entries and
sections. Re-import into Studio to validate syntax, space and aisles before use.

## 6. FAP configuration

**Settings** is the fictional add-on configuration/help page. **System Info**
remains aircraft system information.

- **Settings → Cabin configuration:** edit Layout, Seats and Overhead as a draft.
  **Save layout.json to livery** validates, backs up and applies it. Select an
  external livery first. Reload if another tool changed the file; FAP rejects
  overwriting that newer version.
- **Reload saved layout / Discard draft changes:** discard the layout draft.
  This does not reset oxygen masks.
- **Display:** screen-saver settings and display behavior.
- **Maintenance:** repack oxygen masks and perform the supported ToLiss
  passenger-oxygen reset. Manual **MASK MAN ON** and automatic aircraft triggers
  latch deployment. Repacking is the maintenance action that puts them back.
- **AnyAirline / Help:** IFE provider connection help.

Normal tray, seat, reading-light/call and screen controls remain in the cabin.
Settings does not replace aircraft operational controls.

## 7. Get IFE content

**AnyAirline is the IFE provider.** Download the free **AnyAirline Connector**
from [anyairline.app](https://anyairline.app/).

1. Open the Connector’s **Settings**.
2. Select **X-Plane Experimental**.
3. Link your **X-Plane folder**.
4. Set the feed rate to **1 FPS** (recommended).
5. Click **Start Experimental Feed**.

Keep the Connector running for live content. Optional paid AnyAirline features
are separate.

Choose an IFE-equipped seat, enable its live feed and power the screen on.
Economy IFE belongs to **Type 1**. Overhead monitors have separate enable/live
options and require a compatible panel style. A layout installs screens; it
does not itself provide their live content.

Seatback IFE has its own backlight. Dimming or switching off the cabin lights
does not dim either the default seatback image or the live AnyAirline feed.
Screens cast a faint blue light onto nearby seats using the existing short-range
screen lights. Live black frames produce no screen spill. FAP brightness and
overhead monitor controls remain separate.

If blank, check power, brightness, screen-saver timeout, IFE type and live-feed
setting, then the Connector connection. Advanced Cabin consumes the local
`AnyAirline_IFE/feed` transport data. Preserve that folder during runtime cleanup.
See FAP help and [AnyAirline Guides](https://anyairline.app/guides) for more context.

## 8. Troubleshooting and updates

| Symptom | Check |
| --- | --- |
| No cabin changes | Prepared aircraft integration, plugin enabled, correct folder nesting, no duplicate runtime |
| Wrong livery colors | Selected external livery; exact `objects/advanced cabin` path; include textures, not only JSON |
| White seats | Complete repaired plugin; missing texture messages in `Log.txt`. This revision fixes paths with spaces/Unicode |
| Very low FPS in the first native preview | Replace with this repaired build while X-Plane is closed; the expensive renderer array-copy path is removed |
| Models remain after disabling the old preview | Restart with the repaired build, which removes its instances during disable |
| Wrong night colors | Matching LIT map |
| Studio import fails | JSON syntax, supported atlas/layout and space for the chosen rows |

Compare performance using the same aircraft, camera, weather and graphics
settings after loading. Keep `Log.txt`, the package version/build-check and a
screenshot for reports. Automated SDK checks do not render X-Plane.

Update only while X-Plane is closed. Keep livery folders and Studio projects
separately. Roll back by restoring the complete backed-up plugin, not a mixture
of old and new binaries.
