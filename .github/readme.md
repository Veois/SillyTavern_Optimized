<a name="readme-top"></a>

![][cover]

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/forks)
[![GitHub Issues](https://img.shields.io/github/issues/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/SillyTavern/SillyTavern.svg)](https://github.com/SillyTavern/SillyTavern/pulls)

</div>

---

SillyTavern provides a single unified interface for many LLM APIs (KoboldAI/CPP, Horde, NovelAI, Ooba, Tabby, OpenAI, OpenRouter, Claude, Mistral and more), a mobile-friendly layout, Visual Novel Mode, Automatic1111 & ComfyUI API image generation integration, TTS, WorldInfo (lorebooks), customizable UI, auto-translate, more prompt options than you'd ever want or need, and endless growth potential via third-party extensions.

We have a [Documentation website](https://docs.sillytavern.app/) to answer most of your questions and help you get started.

# Applied Optimizations

This version of SillyTavern (v1.19.0) includes optimizations to speed up loading when working with a large number of characters.

## 🚀 Main Improvements

### 1. Character Indexing System
**Problem:** With a large number of characters (1000+), interface loading took 3-5 minutes.

**Solution:** The system creates a pre-built `characters-index.json` index with all character metadata. Instead of reading and parsing each PNG file on every request, the server reads a single JSON file.

**Result:** Interface loading is reduced to 4-5 seconds even with 3500+ characters.

### 2. Bulk Tag Import
Ability to import tags from character metadata for multiple selected cards simultaneously.

### 3. Imagen Regex
Extraction of prompts from the special `<imagen>...</imagen>` tag in model responses for image generation.

---

## ⚙️ How to Enable Optimization

### Enabling Lazy Loading

1. Open the `default/config.yaml` file
2. Find the `performance:` section
3. Change the parameter:
   ```yaml
   performance:
     lazyLoadCharacters: false  # Change to true
   ```
4. Save the file and restart SillyTavern

### On Server Startup

If `lazyLoadCharacters: true`, the following happens automatically on startup:
- An index is created for all users
- A message appears in the console: `Character indexes built for all users.`

### Automatic Index Updates

The index is automatically updated when:
- Creating a character
- Renaming
- Editing
- Deleting
- Importing
- Duplicating
- Changing attributes

---

## License and credits

**This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.**

* [TavernAI](https://github.com/TavernAI/TavernAI-v1) 1.2.8 by Humi: MIT License
* Portions of CncAnon's TavernAITurbo mod used with permission
* Visual Novel Mode inspired by the work of PepperTaco (<https://github.com/peppertaco/Tavern/>)
* Noto Sans font by Google (OFL license)
* Lexer/Parser by Chevrotain (Apache-2.0 license) <https://github.com/chevrotain/chevrotain>
* Icon theme by Font Awesome <https://fontawesome.com> (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License)
* Default content by @OtisAlejandro (Seraphina character and lorebook) and @kallmeflocc (10K Discord Users Celebratory Background)
* Docker guide by [@mrguymiah](https://github.com/mrguymiah) and [@Bronya-Rand](https://github.com/Bronya-Rand)
* kokoro-js library by [@hexgrad](https://github.com/hexgrad) (Apache-2.0 License)

<!-- LINK GROUP -->
[cover]: https://github.com/user-attachments/assets/01a6ae9a-16aa-45f2-8bff-32b5dc587e44
[discord-link]: https://discord.gg/sillytavern
[discord-shield-badge]: https://img.shields.io/discord/1100685673633153084?color=5865F2&label=discord&labelColor=black&logo=discord&logoColor=white&style=for-the-badge
