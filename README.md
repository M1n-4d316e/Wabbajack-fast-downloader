# [Wabbajack](https://www.wabbajack.org) Fast Downloader

**[Wabbajack](https://www.wabbajack.org) Fast Downloader** is a tool designed to streamline the process of downloading mods for modlists generated by Wabbajack. This tool extracts mod IDs and file IDs from the Wabbajack modlist JSON file and generates download links for each mod, then opens these links in batches for efficient and faster downloading.

> **Project Origin:** This project is inspired by the need for a faster mod downloading process for Wabbajack-generated modlists. It originated from [this GitHub issue](https://github.com/parsiad/nexus-autodl/issues/17).

## How It Works

The tool operates in two main steps:

1. **Modlist Extraction:** The JSON modlist file included in the Wabbajack modlist is parsed to extract mod IDs and file IDs. These IDs are used to generate download links for each mod on Nexus Mods.

2. **Batch Download:** The generated download links are opened in batches using the `webbrowser` module. This approach helps bypass download limits and speeds up the downloading process.

## Requirements

- [Python 3.x](https://www.python.org)
- [Tampermonkey](https://www.tampermonkey.net)
- [Tampermonkey plugin that removes Nexus Mods wait time](https://greasyfork.org/en/scripts/394039-nexus-no-wait)

## Usage

1. **Clone or Download Repository**:

   Clone or download this repository to your local machine:

   ```bash
   git clone https://github.com/M1n-4d316e/Wabbajack-fast-downloader.git

   ```

2. **Locate and Extract Modlist File**:

   The Modlist File is located within the Wabbajack modlist package. For example, the package is located next to '**Wabbajack.exe**' inside '**3.2.0.1\downloaded_mod_lists\wj-featured@@\_tpf-fo4.wabbajack**'. You can use tools like 7-Zip or PeaZip to open and extract the Modlist File.

3. **Place Modlist File**:

   Place the Wabbajack modlist JSON file in the project directory.

4. **Extract Modlist Data**:

   Run the modlist extraction script to generate download links:

   ```bash
   python extract_modlist.py
   ```

   This will create an '**output.txt**' file containing the generated download links.

5. **Batch Download**:

   - Open the 'batch_download.py' script in a text editor.
   - Locate the following line:
     ```python
     url = f"https://www.nexusmods.com/fallout4/mods/{mod_id}?tab=files&file_id={file_id}"
     ```
   - Edit the URL according to your game. For example, if your game is Skyrim:

     ```python
     url = f"https://www.nexusmods.com/skyrim/mods/{mod_id}?tab=files&file_id={file_id}"
     ```

   - Save the script.
   - Run the batch download script to start downloading mods in batches:=
     ```bash
     python batch_download.py
     ```
     The script will open download links in batches. Let the downloads complete, and press Enter in the terminal for the next batch.

## Acknowledgments

This project was inspired by the need for a faster mod downloading process for Wabbajack-generated modlists. The code snippets used in this project were provided by Chat-GPT, [@npe607](https://github.com/npe607) and [@schuler-ph](https://github.com/schuler-ph), with special thanks to [@Abggithub123](https://github.com/Abggithub123) for the idea.

I'm just putting it together and making the README.

## Disclaimer

This tool is intended for personal use and should be used responsibly. Make sure to respect the terms and conditions of the mod authors and Nexus Mods. Use this tool at your own risk.
