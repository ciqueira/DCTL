# DCTL Collection for DaVinci Resolve

A collection of DCTL (DaVinci Color Transform Language) scripts for color manipulation and image processing in DaVinci Resolve.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Controls & Features](#controls--features)
- [Color Space Models](#color-space-models)
- [Usage](#usage)
- [Changelog](#changelog)
- [Contributing](#contributing)
- [License](#license)

## Overview

MC Saturations
Enhance saturation for different types of media, seeking maximum or desired color separation, with natural tones and cinematic or glossy results.

### Key Features

- Multiple color space transformations (HSL, HSV, Lab, LCH, etc.)
- Zone-based saturation controls
- Advanced chroma manipulation
- Support for various color gamuts
- Customizable pivot points and color ranges

## Installation

1. Download the DCTL files from this repository
2. Copy the files to your DaVinci Resolve DCTL folder:
   - **macOS**: `/Library/Application Support/Blackmagic Design/DaVinci Resolve/LUTs/`
   - **Windows**: `C:\ProgramData\Blackmagic Design\DaVinci Resolve\Support\LUTs\`
   - **Linux**: `/home/resolve/LUTs/`
3. Restart DaVinci Resolve
4. Access the DCTL from the OpenFX panel

## Controls & Features

### Saturation Controls

- **Green/Magenta**: Saturation of Magenta and Green colors only
- **Yellow/Blue**: Saturation of Yellow and Blue colors only
- **Cyan/Red**: Saturation of Cyan and Red colors only
- **Saturation Space**: Saturation Space for Space Type Selected
- **Saturation**: Saturation Standard for RGB colors
- **Subtractive Sat**: Subtractive Saturation for Space Type Selected
- **Luminance**: Luminance for Space Type Selected
- **Chroma**: Chroma for Space Type Selected

### Zone Controls

- **Zone Saturation**: "Overall Saturation Strength
- **Pivot Points**: Balances between Shadows (-) and Highlights (+)

### Color Space Models

- HSL (Derived)
- HSV (Derived)
- CIELab (Classic)
- LCHab (Classic)
- OKLab (Classic)
- ProLab (Alternative)
- Additional alternative models (HSP, Chen, Reuleaux, Cylindrical, Spherical, Cone.)

## Usage

1. Add the DCTL as an OpenFX filter in your node tree
2. Adjust the controls based on your needs:
   - Use color-specific controls for targeted adjustments
   - Experiment with different color space models

## Changelog

### Version 0.0.7
- fix SubSat

### Version 0.0.6
- Refactoring, duplicate methods, encapsulation of variables, fix functions
- Bug luminance in Cone or not working correctly
- Implement Saturation by RGB before conversion
- Bug HSL color space, pulling more red
- Miscellaneous Bugs
- Rename and Reorganize UI

## Known Issues & Limitations

### Current Bugs
- mapping of coordinates adjustments in the color group of the lab-based color space

## Roadmap & Future Implementations

### Planned Features
- [ ] Extended gamut mapping options
- [ ] Improved Coordinates in Lab-Based Spaces
- [ ] Implement Vibrancy control
- [ ] Implement Density control 

### Under Development
- [x] Enhanced zone-based controls
- [ ] Optimization for better performance
- [ ] New UI parameters for fine-tuning
- [x] Refactoring


### Feature Requests
- Suggestions welcome through GitHub issues
- Priority given to stability and performance improvements


## Contributing

Contributions are welcome! Please feel free to submit pull requests, report bugs, or suggest new features.

## License

This project is licensed under MIT - see the LICENSE file for details.