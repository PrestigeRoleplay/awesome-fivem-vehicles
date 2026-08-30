# Awesome FiveM Vehicles [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, resources, and guides for working with vehicles on FiveM servers.

## Contents

- [Tools](#tools)
- [GTA V Enhanced (gen9)](#gta-v-enhanced-gen9)
- [Engine Sound Packs](#engine-sound-packs)
- [Guides & Tutorials](#guides--tutorials)
- [Vehicle Sources](#vehicle-sources)
- [Frameworks & Scripts](#frameworks--scripts)
- [Performance Tips](#performance-tips)
- [File Format Reference](#file-format-reference)

---

## Tools

- [FiveMRides Vehicle Converter](https://fivemrides.com/converter/) - Convert any GTA V vehicle to FiveM with 102 engine sounds, handling presets, and auto fxmanifest generation.
- [FiveMRides Resource Optimizer](https://fivemrides.com/optimizer/) - Reduce vehicle file sizes 40-70% with smart BC5/BC7 compression and polygon decimation.
- [fivem-vehicle-validator](https://github.com/PrestigeRoleplay/fivem-vehicle-validator) - CLI tool to validate FiveM vehicle resources for missing files, bad references, and common mistakes.
- [fivem-joaat-hash](https://github.com/PrestigeRoleplay/fivem-joaat-hash) - JOAAT hash calculator for FiveM vehicle model names and other identifiers.
- [fivem-handling-presets](https://github.com/PrestigeRoleplay/fivem-handling-presets) - Ready-to-use handling presets for common vehicle classes (sedans, sports, SUVs, trucks, etc.).
- [ToolKitV](https://github.com/UmbrellaRE/ToolKitV) - Texture optimizer for GTA V/FiveM resources. Texture-only; does not support 3D model optimization.
- [OpenIV](https://openiv.com/) - The essential GTA V file editor for browsing and extracting game archives (RPF), textures, and models.
- [CodeWalker](https://github.com/dexyfex/CodeWalker) - 3D map and model viewer for GTA V. Useful for inspecting YFT/YDR models and YTD textures.

## GTA V Enhanced (gen9)

FiveM for GTA V Enhanced runs as a separate client (early access since July 2026). Legacy YFT/YTD assets do not load on it - every vehicle must be converted, and a clean conversion is not proof it works in game.

- [FiveM on GTA V Enhanced: Install and Run Custom Vehicles](https://fivemrides.com/fivem-enhanced-vehicles-guide/) - Full field guide: Alchemist refine + convert pipeline, Enhanced FXServer setup, and the common failure signatures (streaming timeouts, client crashes, silent engines).
- [FiveM Enhanced Cars overview](https://fivemrides.com/fivem-enhanced-cars/) - What the gen9 client changes for vehicle mods and how in-game verification works.
- [Alchemist](https://docs.fivem.net/) - Official Cfx.re Legacy-to-Enhanced asset conversion tool. Always run `--refine` before the convert pass; a straight convert can produce files that crash the Enhanced client despite valid headers.
- **DLC audio bank trap** - On the Enhanced client, DLC vehicle sound banks (`kanjo`, `nero`, `xa21`, `jugular`, `trophytruck`, `schafter3`, `minivan2`, `elegy`...) play no engine sound, while base-game banks (`adder`, `baller`, `infernus`, `sandking`...) work. Remap `<audioNameHash>` to a base-game bank of the same class (e.g. `elegy` to `elegy2`, `schafter3` to `schafter2`).
- **Edition check** - `curl http://<ip>:30120/info.json` returns `"gamename": "gta5enhanced"` on an Enhanced server, `"gta5"` on Legacy.

## Engine Sound Packs

- [SpiritsCreations FiveM-Engine-Sound-Pack](https://github.com/SpiritsCreations/FiveM-Engine-Sound-Pack) - Open-source collection of engine sound files ready for FiveM integration.
- V8 muscle car sound packs — popular on GTA5-Mods.com, realistic idle and rev samples.
- JDM/tuner engine sounds — turbocharged inline-4 and boxer engine audio replacements.
- European supercar sound packs — high-RPM V10/V12 exhaust and intake sounds.
- Diesel truck engine sounds — deep-tone diesel idle and acceleration audio.
- Electric vehicle sound mods — EV whine and regenerative braking audio for Tesla-style builds.

## Guides & Tutorials

- [How to Install Custom Cars on FiveM](https://fivemrides.com/how-to-install-fivem-cars/) - Step-by-step guide covering resource setup, fxmanifest, and server.cfg.
- [How to Fix Texture Loss on FiveM](https://fivemrides.com/fivem-texture-loss-fix/) - Diagnose and fix texture streaming issues on your server.
- [FiveM Vehicle Optimization Guide](https://fivemrides.com/fivem-vehicle-optimization/) - Best practices for reducing file sizes and improving client performance.
- [Debadged vs Lore Friendly Vehicles](https://fivemrides.com/fivem-debadged-vs-lore-friendly/) - Understand the difference and when to use each type.
- [Best FiveM Cars 2026](https://fivemrides.com/best-fivem-cars/) - Curated picks for the best vehicle mods this year.
- [FiveM Car Not Spawning - 9 Causes & Fixes](https://fivemrides.com/fivem-car-not-spawning/) - Diagnostic checklist for the tanker/trailer bug, invalid model errors, and streaming failures.
- [FiveM Resmon High Fix](https://fivemrides.com/fivem-resmon-high-fix/) - Find and fix the scripts inflating your resource monitor times.
- [FiveM Vehicle LOD Fix](https://fivemrides.com/fivem-vehicle-lod-fix/) - Stop vehicles from disappearing at distance with proper lodDistances tuning.
- [Cfx.re Documentation](https://docs.fivem.net/) - Official FiveM documentation covering natives, resource manifests, and server configuration.

## Vehicle Sources

- [FiveMRides Shop](https://fivemrides.com/) - Premium debadged vehicles, car packs, and more.
- [GTA5-Mods.com](https://www.gta5-mods.com/) - The largest GTA V modding community. Many vehicle mods can be converted for FiveM use.
- [5Mods](https://www.gta5-mods.com/vehicles) - Dedicated vehicles section with filters for car, truck, bike, and emergency categories.
- [Cfx.re Forums](https://forum.cfx.re/) - Official FiveM community forums with a releases section for free vehicle resources.

## Frameworks & Scripts

### Frameworks

- [ESX Legacy](https://github.com/esx-framework/esx-legacy) - The most widely used FiveM roleplay framework. Built-in garage and vehicle ownership systems.
- [QBCore](https://github.com/qbcore-framework/qb-core) - Modern RP framework with robust vehicle management, garages, and mechanic job support.
- [ox_lib](https://github.com/overextended/ox_lib) - Utility library used across both ESX and QBCore for UI elements, callbacks, and shared functions.

### Vehicle Scripts

- [jg-advanceddealership](https://github.com/JoeSzymkowiczFiveworx/jg-advanceddealership) - Advanced vehicle dealership with test drives, financing, and showroom displays.
- [qb-garages](https://github.com/qbcore-framework/qb-garages) - Garage system for QBCore with impound lot and multi-location support.
- [AdvancedParking](https://github.com/kibook/AdvancedParking) - Persistent parking — vehicles stay where you left them across server restarts.
- [brz-tunerchip](https://github.com/JEFRFRANCISCO/brz-tunerchip) - In-game vehicle tuning chip for modifying handling on the fly.
- [VehicleDeformation](https://github.com/Flavor-Project/VehicleDeformation) - Realistic vehicle deformation and damage model improvements.
- [LegacyFuel](https://github.com/InZidi):LegacyFuel) - Fuel system that adds gas stations, fuel consumption, and jerry cans.

## Performance Tips

- **16 MB YTD streaming limit** — FiveM cannot stream texture dictionaries larger than 16 MB. Split oversized YTDs or compress textures to stay under the limit.
- **Server convars for texture quality** — Use `str_maxVehicleTextureRes` (default 1024) and `str_maxVehicleTextureResRgba` (default 512) to cap client-side texture resolution and prevent VRAM spikes.
- **LOD management** — Ensure your vehicles include proper LOD levels (high, med, low). Missing LODs force the client to render the high-detail model at all distances.
- **Texture compression matters** — Use BC5 for normal maps, BC7 for specular maps, and DXT1/DXT5 for diffuse. This is what the [FiveMRides Optimizer](https://fivemrides.com/optimizer/) does automatically.
- **Polygon count targets** — Aim for under 50k triangles for the high LOD. Anything above 80k will cause noticeable frame drops in populated areas.
- **Test with multiple vehicles** — A single vehicle may run fine, but performance problems appear when 10+ custom vehicles are in view simultaneously.
- **Read the full guides** — [FiveM Vehicle Optimization Guide](https://fivemrides.com/fivem-vehicle-optimization/) and [Texture Loss Fix](https://fivemrides.com/fivem-texture-loss-fix/) cover these topics in depth.

## File Format Reference

| Format | Extension | Description |
|--------|-----------|-------------|
| **YTD** | `.ytd` | Texture dictionary. Contains all textures (diffuse, normal, specular) for a vehicle in DDS format inside a RAGE container. |
| **YFT** | `.yft` | Fragment type (model). The main 3D model file for vehicles, including physics, breakable parts, and LODs. |
| **YDR** | `.ydr` | Drawable model. Static 3D models used for props, wheels, and non-fragmented objects. |
| **handling.meta** | `.meta` | Vehicle physics and handling data — mass, acceleration, braking, suspension, traction. |
| **vehicles.meta** | `.meta` | Vehicle definition — model name, make, type, class, dashboard type, wheel type, and flags. |
| **carvariations.meta** | `.meta` | Paint colors, liveries, extras, and modification kits available for the vehicle. |
| **fxmanifest.lua** | `.lua` | FiveM resource manifest. Declares all files the resource contains so the server knows what to stream to clients. |

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding resources to this list.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this work. See [LICENSE](LICENSE) for details.
