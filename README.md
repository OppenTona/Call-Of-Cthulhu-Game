# 🎲 Call of Cthulhu Game - Discord Bot Scripts

<div align="center">

![Call of Cthulhu](https://img.shields.io/badge/Call%20of%20Cthulhu-RPG-darkred?style=for-the-badge)
![Avrae](https://img.shields.io/badge/Avrae-Discord%20Bot-blue?style=for-the-badge)
![Draconic](https://img.shields.io/badge/Language-Draconic-orange?style=for-the-badge)
![Discord](https://img.shields.io/badge/Discord-Integration-5865F2?style=for-the-badge&logo=discord&logoColor=white)

*A comprehensive collection of Draconic scripts for playing Call of Cthulhu on Discord via Avrae*

</div>

---

## 📖 Overview

**Call of Cthulhu Game** is a comprehensive collection of Draconic scripts (Python-based language) designed to support Call of Cthulhu tabletop RPG sessions directly on Discord through the Avrae bot.

Since there isn't any existing bot that fully supports Call of Cthulhu gameplay on Discord, this project was developed to fill that gap, providing players with a seamless and convenient gaming experience for the cosmic horror RPG community.

## ✨ Features

### 🎯 Character Management
- **Attribute System**: Manage STR, DEX, POW, CON, APP, EDU, SIZ, INT
- **Sanity (SAN)**: Track and modify mental stability points
- **Magic Points (MP)**: Manage spell-casting resources
- **Luck**: Luck point system with modification support
- **Movement Rate**: Character speed management

### 🎲 Skill System
- **Complete Skill Database**: Full support for Call of Cthulhu skill list
- **Skill Checks**: d100 skill roll system with success/failure determination
- **Skill Abbreviations**: Quick commands for common skills (SPOT, DOD, STE, LIS, etc.)
- **Custom Skills**: Add and manage custom or specialized skills
- **Automatic Calculations**: Dodge automatically calculated from DEX

### 🎯 Dice Rolling System
- **Character Creation**: Random stat generation following Call of Cthulhu rules
- **Skill Rolls**: Automated skill checks with result interpretation
- **Attribute Rolls**: Direct attribute testing capabilities

## 📁 Project Structure

```
Call-Of-Cthulhu-Game/
├── Code của Call of Cthulhu/
│   ├── coc.txt          # Main character management script
│   ├── skill.txt        # Skill system and checks
│   ├── randcoc.txt      # Random character generation
│   ├── san.txt          # Sanity management
│   ├── mp.txt           # Magic Points management
│   ├── luck.txt         # Luck system
│   └── moverate.txt     # Movement rate management
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Discord server with **Avrae** bot installed
- Permissions to use custom commands on your server
- Basic understanding of Call of Cthulhu RPG rules

### Installation

1. **Import individual scripts into Avrae:**
```
!alias coc embed {{paste content from coc.txt}}
!alias skill embed {{paste content from skill.txt}}
!alias randcoc embed {{paste content from randcoc.txt}}
!alias san embed {{paste content from san.txt}}
!alias mp embed {{paste content from mp.txt}}
!alias luck embed {{paste content from luck.txt}}
!alias moverate embed {{paste content from moverate.txt}}
```

2. **Alternative**: Use gist/workshop for batch importing

### Basic Usage

#### Character Creation
```
!randcoc
```
Generates random character stats following Call of Cthulhu rules (3d6×5 for most stats, (2d6+6)×5 for others)

#### Setting Attributes
```
!coc STR 65        # Set Strength to 65
!coc DEX 70        # Set Dexterity to 70
!coc SAN 55        # Set Sanity to 55
!coc JOB Detective # Set occupation
```

#### Skill Checks
```
!skill Spot Hidden          # Roll against Spot Hidden skill
!skill 65 Custom Skill      # Roll against a 65% custom skill
!skill SPOT                 # Use abbreviation for Spot Hidden
!skill DOD                  # Use abbreviation for Dodge
```

#### Resource Management
```
!san -5         # Lose 5 Sanity points
!san +2         # Gain 2 Sanity points
!mp -3          # Spend 3 Magic Points
!mp +1          # Recover 1 Magic Point
!luck           # Check current luck
!moverate       # Check movement rate
```

## 📊 Supported Skills & Abbreviations

<details>
<summary>📋 Complete Skill List</summary>

| Skill | Abbreviation | Default Value |
|-------|--------------|---------------|
| Spot Hidden | SPOT | 25 |
| Dodge | DOD | DEX/2 (auto-calculated) |
| Stealth | STE | 20 |
| Listen | LIS | 20 |
| Accounting | ACC | 5 |
| Anthropology | ANT | 1 |
| Appraise | APP | 5 |
| Archaeology | ARC | 1 |
| Art/Craft | ART | 5 |
| Charm | CHA | 15 |
| Climb | CLI | 20 |
| Credit Rating | CRT | 9 |
| Cthulhu Mythos | CTH | 0 |
| Disguise | DIS | 5 |
| Drive Auto | DRI | 20 |
| Electrical Repair | ELE | 10 |
| Fast Talk | FAS | 5 |
| Fighting | FIG | 25 |
| Fighting Brawl | FIB | 25 |
| Firearms | FIR | 25 |
| Firearms Handgun | FIH | 20 |
| Rifle/Shotgun | RIF | 25 |
| First Aid | FIR | 30 |
| History | HIS | 5 |
| Intimidate | INT | 15 |
| Jump | JUM | 20 |
| Language Other | LAO | 1 |
| Language Own | LAW | EDU (auto-calculated) |
| Law | LAW | 5 |
| Library Use | LIB | 20 |
| Listen | LIS | 20 |
| Locksmith | LOC | 1 |
| Mechanical Repair | MEC | 10 |
| Medicine | MED | 1 |
| Natural World | NAT | 10 |
| Navigate | NAV | 10 |
| Occult | OCC | 5 |
| Operate Heavy Machinery | OPE | 1 |
| Persuade | PER | 10 |
| Pilot | PIL | 1 |
| Psychology | PSY | 10 |
| Psychoanalysis | PSA | 1 |
| Ride | RID | 5 |
| Science | SCI | 1 |
| Sleight of Hand | SLE | 10 |
| Survival | SUR | 10 |
| Swim | SWI | 20 |
| Throw | THR | 20 |
| Track | TRA | 10 |

</details>

## 🛠️ Customization

### Adding Custom Skills
```
!coc "Mythos Lore" 15        # Add custom skill with value
!coc "Computer Use" 25       # Modern skill addition
```

### Removing Skills
```
!coc DELETE "Skill Name"     # Remove unwanted skill
```

### Setting Occupation
```
!coc JOB "Private Investigator"    # Set character occupation
!coc JOB "Professor"               # Academic background
```

### Modifying Existing Skills
```
!coc "Spot Hidden" 65        # Update existing skill value
!coc "Fighting" 45           # Modify combat skill
```

## 🎮 Advanced Usage

### Skill Check Results
The skill system automatically determines:
- **Critical Success**: 01-05 or ≤ skill/5
- **Extreme Success**: ≤ skill/5
- **Hard Success**: ≤ skill/2
- **Regular Success**: ≤ skill value
- **Failure**: > skill value
- **Fumble**: 96-100 (depending on skill level)

### Character Data Storage
All character data is stored in Avrae's CVAR system:
- `coc`: Main character attributes (STR, DEX, etc.)
- `cocskill`: All character skills and their values

## 🤝 Contributing

We welcome contributions from the community! Whether you want to:

- 🐛 Report bugs
- 💡 Suggest new features
- 🔧 Improve existing code
- 📚 Enhance documentation
- 🎯 Add new skills or mechanics

Please feel free to create **Issues** or **Pull Requests**!

### How to Contribute:
1. Fork this repository
2. Create a new branch for your feature
3. Make your changes
4. Test thoroughly with Avrae
5. Commit your changes with clear messages
6. Push to your branch
7. Create a Pull Request

### Development Guidelines:
- Follow Draconic syntax conventions
- Test all scripts in a Discord environment
- Update documentation for new features
- Maintain compatibility with Avrae bot

## 🔧 Technical Details

- **Language**: Draconic (Python-based scripting language for Avrae)
- **Platform**: Discord with Avrae bot integration
- **Game System**: Call of Cthulhu 7th Edition rules compatible
- **Data Storage**: Character data stored in Avrae CVARs (Character Variables)
- **Roll System**: d100 percentile system with automatic success calculation

### Script Architecture:
- **Modular Design**: Each script handles specific functionality
- **Data Persistence**: Character data persists across sessions
- **Error Handling**: Robust input validation and error messages
- **Extensibility**: Easy to add new skills and features

## 📞 Support & Community

- **GitHub Issues**: [Report bugs or request features](https://github.com/OppenTona/Call-Of-Cthulhu-Game/issues)
- **Discord**: Join Call of Cthulhu gaming communities
- **Developer**: [@OppenTona](https://github.com/OppenTona)
- **Avrae Documentation**: [Official Avrae Docs](https://avrae.readthedocs.io/)

### Troubleshooting:
- Ensure Avrae has proper permissions in your Discord server
- Verify script syntax when importing custom aliases
- Check character data with `!cvar list` if experiencing issues
- Reset character data with `!cvar delete coc` if needed

## 📄 License

This project is released under an open-source license. See the `LICENSE` file for more details.

## 🎭 About Call of Cthulhu

Call of Cthulhu is a horror tabletop role-playing game based on the works of H.P. Lovecraft, where players take on the roles of investigators exploring dangerous supernatural mysteries in a world where cosmic horrors lurk beyond human understanding.

### Game Themes:
- **Cosmic Horror**: Face unknowable entities from beyond
- **Investigation**: Uncover dark secrets and hidden truths
- **Sanity Loss**: Mental stability as a precious resource
- **1920s Setting**: Classic era of mystery and horror
- **Mortality**: Characters are fragile humans in a vast, uncaring universe

## 🌟 Features Roadmap

- [ ] **Combat System**: Initiative tracking and combat mechanics
- [ ] **Weapon Database**: Firearm and weapon damage systems  
- [ ] **Occupation Templates**: Pre-built skill packages for common jobs
- [ ] **Insanity System**: Temporary and permanent insanity effects
- [ ] **Spell System**: Mythos spells and casting mechanics
- [ ] **Monster Database**: Quick access to creature stats
- [ ] **Campaign Tools**: Session tracking and note-taking features

---

<div align="center">

**"The oldest and strongest emotion of mankind is fear, and the oldest and strongest kind of fear is fear of the unknown." - H.P. Lovecraft**

⭐ **If this project helps your gaming sessions, please give us a star!**

[![GitHub stars](https://img.shields.io/github/stars/OppenTona/Call-Of-Cthulhu-Game?style=social)](https://github.com/OppenTona/Call-Of-Cthulhu-Game/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/OppenTona/Call-Of-Cthulhu-Game?style=social)](https://github.com/OppenTona/Call-Of-Cthulhu-Game/network/members)

</div>
