# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Unity-chan's Ball a Roll demo project - a workshop project from Unite 2016 Tokyo demonstrating Unity Services integration (Analytics, IAP, Cloud Build, Ads). Built with Unity 5.3.4.

## Project Structure

- **Assets/Example/** - Main game code
  - `Scripts/CompleteProject/` - Production-ready implementations (namespace: `CompleteProject`)
  - `Scripts/Workshop/` - Workshop exercise versions (incomplete)
  - `Scenes/` - Game scenes including `CompleteScene.unity` (main scene)
- **Assets/Etc/** - Supporting assets
  - `UnityChan/` - Unity-chan character assets and scripts
  - `Effects/` - Image effects (CinematicEffects, ImageEffects)
  - `Heatmaps/` - Unity Analytics heatmap visualization
  - `Kino/` - Keijiro's effects (Bloom, Obscurance)

## Key Scripts

- `PlayerController.cs` - Ball physics with gyro/keyboard input, item collection, scoring
- `Purchaser.cs` - Unity IAP integration (consumable, non-consumable, subscription products)
- `ScoreManager.cs` - Coin/score persistence via PlayerPrefs
- `GameModeController.cs` - Game state management

## Running Tests

Unit tests use NUnit and run in the Unity Editor:
- Open Unity Test Runner: Window > General > Test Runner
- Tests located in `Assets/Example/Scripts/UnitTest/Editor/`

## Platform-Specific Code

The project uses preprocessor directives for platform-specific behavior:
- `UNITY_IOS`, `UNITY_ANDROID` - Mobile gyroscope input
- `UNITY_EDITOR` - Editor-only behavior
- IAP receipt validation is platform-specific (Android, iOS, OSX)

## Unity Version Compatibility

- **Original version**: Unity 5.3.4 (Mono runtime, .NET 2.0 API)
- **Linux Editor**: Requires Unity 2019.x+ for official Linux Editor support
- **CoreCLR runtime**: Requires Unity 6+ (experimental)
- **Upgrading**: Expect deprecated API fixes for CinematicEffects/ImageEffects (replaced by Post Processing Stack in newer Unity)
