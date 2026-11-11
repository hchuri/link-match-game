# PatchPlanner — AV & Network Patching Tool

A browser-based tool for planning and documenting how audio, video, network and power gear is patched across sites and racks. It's a single HTML file with no install, no server and no build step, and it works offline.

**Open it:** open `patch/index.html` in any modern browser, or host it with GitHub Pages at `/patch/`.

## Features
- **Sites & racks.** Model buildings, rooms, stages or OB trucks, each with racks of any U height and a power budget.
- **Rack elevations.** Drag equipment into rack slots. Overlaps and out-of-range positions are blocked.
- **Equipment library.** About 30 generic templates: switches, patch panels, Dante stageboxes, consoles, DSPs, amps, speakers, PTZ cameras, switchers, SDI routers, AV-over-IP encoders/decoders, displays, PDUs, UPS and more. You can save your own templates.
- **Patching.** Pick a FROM port and a TO port; compatible free ports are highlighted. The tool checks:
  - connector compatibility (RJ45, fibre, XLR, BNC, HDMI, speakON, power and others)
  - direction (output→output and input→input)
  - protocol and VLAN mismatches
  - ports that are already in use
  
  Use **×N** to patch a run of consecutive ports in one go.
- **Cable schedule.** Cable IDs are assigned automatically per type (NET-001, AUD-001, VID-001, FIB-001, SPK-001, PWR-001…). You can set length, colour and route notes, sort and filter the list, renumber IDs and export to CSV.
- **Signal flow diagram.** Generated automatically, grouped by role (sources → I/O → network → processing → distribution → destinations). Click a device to highlight its connections. Exports to SVG.
- **Network / IP.** An IP schedule with duplicate detection, auto-assignment of IPs, VLAN overview and a per-switch port map with access VLANs.
- **Validation.** Flags duplicate IPs, rack overlaps, power over budget, connector mismatches, and Dante primary and secondary going to the same switch.
- **Cable labels.** Printable labels for both ends of every cable.
- **Rider / report.** A printable technical rider and patch book (or save as PDF). It includes:
  - equipment list
  - rack elevations
  - cable schedule
  - cable pull list / BOM with total lengths
  - IP schedule and switch port maps
  - power summary
  - open issues

## Data
Work is auto-saved in the browser (localStorage). Use **Save file** / **Open file** to keep `.json` project files and share them with your team. Undo is available with Ctrl+Z.
