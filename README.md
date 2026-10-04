# Support Fins – SolidWorks Add-in

A native SolidWorks Add-in that generates 3D printing support fins with tines, tear-off perforations, and bed pads directly inside SolidWorks, powered by **Matthew Trahan's Support Fins engine**.

## Key Features
- **Zero External Dependencies:** Embeds [Jint](https://github.com/sebastienros/jint) (pure C# JavaScript interpreter) to run the bundled engine in memory. No Node.js or Python runtime required on the user's machine.
- **Coordinate System Adaptation:** Automatically aligns SolidWorks coordinates ($Y$-Up vs. $Z$-Up / Front Plane vs. Top Plane) with the 3D-printing coordinate space.
- **Native SolidWorks UI:** Accessible via the CommandManager tab (*Support Fins*), the Tools menu, and the SolidWorks command search.
- **Direct B-Rep / STL Import:** Writes computed fins as a binary STL and imports them directly into the active part document as a distinct body with a 0.2 mm air gap.
- **Wide Bed Pads:** Pre-configured with `padStyle: 'sure'` for optimal bed adhesion.

## Project Structure
- `SupportFins.SolidWorks/`: The C# Add-in solution and SolidWorks API integration.
- `engine/`: Source files and bundled JavaScript engine (`index.js`, `fins_entry.js`, `supportfins-engine.js`).

## Requirements & Building
- SolidWorks 2021 or newer
- .NET Framework 4.8 / Visual Studio 2022
- COM Interop registration (`RegAsm.exe /codebase SupportFins.SolidWorks.dll`)

## Credits
- Support Fins core algorithm & concept by **Matthew Trahan** ([Support Fins](https://github.com/matthewtnt/support-fins))
- SolidWorks Add-in implementation by **Hayen Iggena**
