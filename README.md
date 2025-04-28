# DCTL Collection for DaVinci Resolve

A collection of DCTL (DaVinci Color Transform Language) scripts for color manipulation and image processing in DaVinci Resolve.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Controls & Features](#controls--features)
- [Color Space Models](#color-space-models)
- [Changelog](#changelog)
- [Contributing](#contributing)
- [License](#license)

## Overview

DCTL: MC Saturations
Enhance saturation for different types of media, seeking maximum or desired color separation, with natural tones and cinematic or glossy results. For detailed information and examples, check out the [article on Medium](https://medium.com/@magnociqueira/extrair-o-máximo-de-saturação-das-cores-e-obter-resultados-incríveis-com-uma-dctl-no-davinci-81920742599e).


### Key Features

- Multiple color space transformations (HSL, HSV, Lab, LCH, etc.)
- Zone-based saturation controls
- Advanced chroma manipulation
- Support for various color gamuts
- Customizable pivot points and color ranges

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

## Additional Requirements

### Color Range Considerations

**English:**  
DaVinci Resolve processes images in floating-point space, allowing values above 1.0 or below 0.0. While this extends the dynamic range, certain processes - such as conversion to HSV - may generate unwanted artifacts when working with negative or excessively high values. It is recommended to use a [Clamp](https://github.com/xtremestuff/resolve-dctl/blob/master/Clamp.dctl) before the DCTL Saturations node to restrict RGB channel values to stay within the 0 to 1 range, avoiding color conversion issues.

**Portuguese:**  
DaVinci Resolve processar imagens em espaço de ponto flutuante, permitindo valores acima de 1.0 ou abaixo de 0.0. Embora isso amplie a faixa dinâmica, certos processos - como a conversão para HSV - podem gerar artefatos indesejados quando se trabalha com valores negativos ou excessivamente altos. A sugestão é usar um [Clamp](https://github.com/xtremestuff/resolve-dctl/blob/master/Clamp.dctl) ante do node de DCTL Saturations, para restringir os valores dos canais RGB para que fiquem dentro do intervalo 0 a 1, evitando problemas na conversão de cores.

### Setup Example
```
Input Image → Clamp (0-1) → DCTL Saturations → Output
```

> **Note**: This is particularly important when working with HDR footage or when previous nodes in your grade may push values outside the standard range.

## Installation

1. Download the DCTL files from this repository
2. Copy the files to your DaVinci Resolve DCTL folder:
   - **macOS**: `/Library/Application Support/Blackmagic Design/DaVinci Resolve/LUTs/`
   - **Windows**: `C:\ProgramData\Blackmagic Design\DaVinci Resolve\Support\LUTs\`
   - **Linux**: `/home/resolve/LUTs/`
3. Restart DaVinci Resolve
4. Access the DCTL from the OpenFX panel

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

## Credits & Acknowledgments

### DCTL Community & Developers
- [hotgluebanjo](https://github.com/hotgluebanjo) - Advanced DCTL implementations
- [Calvin Silly](https://github.com/calvinsilly) - Color science contributions
- [Thatcher Freeman](https://github.com/thatcherfreeman/utility-dctls) - Utility DCTLs
- [Juan Pablo Zambrano](https://github.com/JuanPabloZambrano) - Color space transformations
- [Moaz Elgabry](https://github.com/MoazElgabry) - Color management tools
- [Demystify Color](https://github.com/Demystify-Color) - Educational resources
- [Kaur Hendrikson](https://github.com/KaurHendrikson) - Color grading tools

### Special Thanks
- I can't help but thank a lot of people, starting with @vicer.color Paulo Henrique, with whom I had great conversations about color, emulations and tests. I also thank @davinciresolvetutoriais Marcelo Sant’Anna, who gave me my first directions on color, in addition to the engaged community, where I met incredible people who collaborate, share knowledge and help each other.


## License

This project is licensed under MIT - see the LICENSE file for details.