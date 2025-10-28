# [Steelseries Moments Database Merger](https://rascaloons.github.io/SteelSeries-Moments-Database-Merger/)

A simple, in-browser tool to merge two Steelseries Moments database.db files. This tool helps you recover old gameplay clips and metadata from a backup database and merge them with your current one.

## The Problem

SteelSeries Moments stores all clip metadata (titles, descriptions, trim points, etc.) in a single SQLite database file, separate from the video files themselves. If you reinstall Windows or forget to back up the "database.db" file, your Moments gallery will appear empty even if you move the .mp4 video files into the clips folder.

This tool solves that problem by allowing you to take a backup of your old database.db file and merge its contents into your new, current database.db file.

## Features

- 100% Client-Side: The entire merge process runs in your browser using JavaScript and sql.js. Your database files are never uploaded to any server.

- Duplicate Prevention: The tool automatically detects and skips clips that are already present in your database (based on their unique ID), so you don't get duplicate entries.

- Verbose Logging: See exactly which clips are imported and which are skipped (and why).

- Simple Interface: Just select your two database files, click merge, and you're done.

## How to Use

**DISCLAIMER: THIS WILL ONLY BE POSSIBLE IF YOU STILL HAVE YOUR OLD STEELSERIES INSTALLATION/DATABASE. IF YOU ONLY HAVE YOUR CLIPS, YOU'RE OUT OF LUCK.**\
\
*This is an unofficial tool and is not affiliated with SteelSeries in any way. It was created to solve a specific problem and has been tested for that purpose, but you use it at your own risk.*

**ALWAYS BACK UP YOUR DATABASE FILES BEFORE USING THIS TOOL.** ***I am not responsible for any lost data or damage to your clip library.***

### 1. Find Your Database Files:
You will need two files:

- Your OLD (backup) database file (e.g., from a backup folder). In the case that you still have your old Windows installation, the file can be found at `C:\ProgramData\SteelSeries\GG\apps\moments\db\database.db`

- Your NEW (current) database file.

- The NEW file is typically located at: `C:\ProgramData\SteelSeries\GG\apps\moments\db\database.db`

### 2. IMPORTANT: Make Backups!

Before you do anything, make a backup copy of both your OLD and NEW database files and store them somewhere safe.

### 3. Run the Tool:

Click the following link: [SteelSeries Moments Database Merger](https://rascaloons.github.io/SteelSeries-Moments-Database-Merger/)

### 4. Close Steelseries GG:

Completely shut down the Steelseries GG application. Right-click its icon in your system tray (by the clock) and click "Exit".

### 5. Select Your Files:

1. Base Database: Select your OLD (backup) database file.

2. Appended Database: Select your NEW (current) database file.

The table name should already be set to moments_clips.

### 6. Merge & Download:

Click the "Merge Databases" button.

Wait for the process to complete. You will see a log of imported and skipped clips.

A new file named database.db will be downloaded automatically.

### 7. Replace the File:

Go to the Steelseries Moments database folder (the path from Step 1).

Replace the NEW (current) database.db file with the one you just downloaded.

### 8. Restart and Verify:

Start the Steelseries GG app and open Moments. Your old clips should now appear in the gallery alongside your new ones!

## Technical Details

UI: Built with plain HTML and styled with Tailwind CSS.

Database Logic: Uses sql.js (a JavaScript library) to load the SQLite database files entirely in the browser's memory, run SQL queries to extract data, and insert that data into the other file.
