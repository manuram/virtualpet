# PixelPaw - Virtual Pet App 🐾

An interactive virtual pet application built with HTML, CSS, and JavaScript. Take care of your digital pet by feeding, playing, training, and more! Features a beautiful 3D emoji-based design with realistic pet representations.

## Features

### Pet Care Actions
- **Feed** ($5) - Keep your pet well-fed and happy
- **Play** - Increase happiness through fun activities
- **Rest** - Toggle sleep mode to restore energy and health
- **Heal** - Restore your pet's health quickly
- **Clean** ($8) - Give your pet a bath to keep it clean and happy
- **Train** - Best way to gain experience and level up
- **Vet** ($25) - Full health restoration at the veterinarian
- **Chore** (+$10-24) - Do chores to earn money
- **Toy** ($15) - Buy toys for a huge happiness boost
- **Trick** (+$20-39, Level 3+) - Perform tricks to earn money

### Pet Stats
- **Health** ❤️ - Overall wellbeing of your pet
- **Hunger** 🍖 - How well-fed your pet is
- **Happiness** 😊 - Your pet's mood and contentment
- **Energy** 💤 - Your pet's activity level

### Pet Types
Choose from 6 different pet types, each with unique sounds:
- 🐶 Dog - "Arf arf" bark sound
- 🐱 Cat - Complex meow with vibrato
- 🐦 Bird - Three cheerful chirps
- 🐰 Rabbit - Soft gentle squeak
- 🦊 Fox - Quick sharp yip
- 🐻 Bear - Deep rumbling growl

### Progression System
- **Level System** - Your pet gains experience and levels up (Level 1-20+)
- **Growth Stages** - Pet grows through 5 life stages (Baby → Child → Teen → Adult → Elder)
- **Border Colors** - Glowing border changes color with growth stages (Green → Blue → Purple → Orange → Gold)
- **Age Tracking** - Watch your pet grow over time
- **Mood System** - Pet's mood changes based on stats (Happy, Okay, Sad, Critical)
- **Visual Feedback** - Animated reactions and emoji transformations

### Money & Savings System
- **Wallet** - Track your current money
- **Earn Money** - Complete chores and perform tricks
- **Spend Money** - Buy food, services, and toys
- **Savings Goal** - Set and track savings targets
- **Financial History** - View total earned and spent

### Achievements & Badges
Unlock special badges by completing challenges:
- 🌅 Early Bird - Play in the morning
- 🦉 Night Owl - Play at night
- 🧹 Caretaker - Complete 20 chores
- 💰 Millionaire - Accumulate wealth
- 🏥 Veterinarian - Visit the vet 10 times
- 🧸 Player - Buy 15 toys
- 🎪 Trick Master - Perform 25 tricks

### Sound Effects System
- **Dual Sound Modes** - Choose your preferred audio experience
  - **Game Sounds (Default)** - Synthesized sounds using Web Audio API (no files needed)
  - **Realistic Sounds** - MP3 audio files for authentic animal sounds (optional)
- **Pet-Specific Sounds** - Each pet type has unique sounds
  - Dog: Two quick barks / Realistic dog bark
  - Cat: Complex meow with pitch modulation / Authentic cat meow
  - Bird: Three high-pitched chirps / Real bird chirping
  - Rabbit: Very soft, gentle squeak / Actual rabbit sound
  - Fox: Sharp, quick yip / Genuine fox vocalization
  - Bear: Deep, rumbling growl / Real bear growl
- **UI Sounds** - Level up, money earned, achievement unlocked, error notifications
- **Smart Fallback** - Automatically uses synthesized sounds if MP3 files are missing
- **Easy Setup** - Download MP3 files from free sound libraries (see sounds/README.md)
- **Toggleable** - Enable/disable in Settings ⚙️

### Persistence
- **Auto-Save** - Game automatically saves your progress
- **Local Storage** - Progress is saved in your browser

## How to Play

1. **Name Your Pet** - Enter a name in the input field and click "Set Name"
2. **Choose Your Pet** - Click Settings ⚙️ to select from 6 different pet types
3. **Click Your Pet** - Single click to pet, double-click for hugs
4. **Use Action Buttons** - Feed, Play, Rest, Train, and more to care for your pet
5. **Monitor Stats** - Keep an eye on the 4 status bars (Health, Hunger, Happiness, Energy)
6. **Earn & Spend Money** - Do chores and tricks to earn money, spend it on care items
7. **Level Up** - Gain experience through activities to level up and unlock growth stages
8. **Track Progress** - Check Analytics 📊 to see detailed statistics and achievements
9. **Watch Growth** - Your pet's border color changes as it grows through life stages

## Tips

- Keep all 4 stats above 60% for optimal care rating
- Feed your pet when hunger drops below 30%
- Put your pet to rest when energy is low for regeneration
- Train your pet to gain the most experience (20 XP per session)
- Do chores to earn money for expensive items like vet visits
- Perform tricks (Level 3+) for the best XP gain (25 XP) and income
- Watch the mood badge on your pet to monitor its current state
- Read thought bubbles for helpful hints about what your pet needs
- Balance earning and spending to maintain a healthy wallet
- Unlock all badges by completing various challenges
- Customize themes to create your perfect pet environment (48 combinations!)
- Try both sound modes - Game Sounds (synthesized) vs Realistic Sounds (MP3 files)
- Open sounds/download-helper.html to easily download free MP3 sound files
- Visit regularly - stats decay over time when you're away

## Technical Details

- **Pure JavaScript** - No frameworks or dependencies, vanilla ES6+
- **Responsive Design** - Works on desktop and mobile devices
- **Optimized CSS Animations** - Hardware-accelerated smooth animations with GPU rendering
- **Text Rendering Optimization** - Geometric precision rendering for crystal-clear text during animations
- **Performance Tuned** - CSS isolation, transform3d, and backface visibility for zero-blur text
- **Local Storage** - Automatic save/load system for persistent gameplay
- **3D Emoji Design** - Realistic pet representations using modern emoji rendering (90px optimized size)
- **Dynamic Theming** - Multiple color schemes and backgrounds (48 combinations)
- **Tab System** - Organized interface with Pet Stats, Money & Savings, and Activity & Badges tabs
- **Modal System** - Settings, Analytics, and Help modals for detailed information
- **Activity Logging** - Comprehensive tracking of all pet interactions
- **Web Audio API** - Real-time sound synthesis for pet-specific sounds and UI feedback

## Getting Started

Simply open `index.html` in your web browser. No installation or build process required!

## Browser Compatibility

Works in all modern browsers that support:
- ES6 JavaScript
- CSS Grid and Flexbox
- Local Storage API

Enjoy taking care of your PixelPaw! 🎮🐾

