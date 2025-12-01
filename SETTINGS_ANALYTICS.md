# 🎮 PixelPaw - Settings & Analytics Guide

## 📊 **Analytics Dashboard**

Access detailed statistics about your pet's life and your interactions!

### **How to Access:**
Click the 📊 button in the header

### **Analytics Sections:**

#### 📈 **Total Interactions**
Track every action you've taken:
- **Total Pets**: Times you clicked/petted your pet
- **Times Fed**: Total feeding sessions ($5 each)
- **Play Sessions**: Times you played with your pet
- **Healings**: Medical care given
- **Baths Given**: Hygiene care sessions ($8 each)
- **Training Sessions**: Times you trained your pet
- **Vet Visits**: Professional health care ($25 each)
- **Chores Completed**: Work done to earn money
- **Toys Bought**: Toys purchased ($15 each)
- **Tricks Performed**: Tricks done for money (Level 3+)

#### ⏱️ **Time Statistics**
Monitor your pet's lifecycle:
- **Days Old**: Age in days
- **Current Level**: Experience level (1-20+)
- **Growth Stage**: Baby → Child → Teen → Adult → Elder
- **Time Played**: Total hours and minutes played
- **Pet Created**: Date when pet was first created

#### 🏆 **Achievements**
Visual list of all unlocked achievements:
- ✅ **Unlocked**: Shows in golden gradient
- ❌ **Locked**: Shows in gray
- Tracks 7 major achievements

#### 📊 **Current Stats Distribution**
Live bar chart showing:
- Health percentage (red bar)
- Hunger percentage (orange bar)
- Happiness percentage (green bar)
- Energy percentage (blue bar)

#### 🎯 **Pet Performance**
Average statistics and metrics:
- **Avg. Happiness**: Current happiness level
- **Avg. Health**: Current health level
- **Interactions/Day**: Daily interaction rate
- **Total XP Gained**: Lifetime experience points
- **Pet Type**: Current selected pet species (Dog, Cat, Bird, etc.)

#### 💝 **Care Quality Rating**
Dynamic rating system based on average stats:
- ⭐⭐⭐⭐⭐ (90-100%): Exceptional Care! Your pet is thriving!
- ⭐⭐⭐⭐ (75-89%): Great Care! Keep it up!
- ⭐⭐⭐ (60-74%): Good Care! Room for improvement.
- ⭐⭐ (40-59%): Needs More Attention!
- ⭐ (0-39%): Critical! Your pet needs care!

---

## 📑 **Three-Tab Stats System**

### **Tab 1: Pet Stats** 🐾
Quick overview of your pet:
- **Age**: Days old
- **Level**: Current level
- **Experience**: XP progress (e.g., "45 / 100")
- **Mood**: Current mood with emoji

### **Tab 2: Money & Savings** 💰
Financial management:
- **Wallet**: Current available money
- **Spent on care**: Total spent with progress bar (tracked up to $200)
- **Total Earned**: Lifetime earnings from chores and tricks
- **Savings Goal**: Target savings amount
- **Saved**: Current savings with progress bar

### **Tab 3: Activity & Badges** 🏅
Recent history and accomplishments:

**Recent Activity Log:**
- Shows last 10 activities
- Timestamp for each action
- Scrollable list
- Compact display (150px max height)

**Badge Grid:**
Unlock special badges by completing challenges:
- 🌅 **Early Bird**: Play in the morning hours
- 🦉 **Night Owl**: Play late at night
- 🧹 **Caretaker**: Complete 20 chores
- 💰 **Millionaire**: Accumulate significant wealth
- 💾 **Saver**: Reach savings goal
- 💸 **Spender**: Spend significant amount
- 🎪 **Trainer**: Train frequently
- 🏥 **Veterinarian**: Visit the vet 10 times
- 🧼 **Cleaner**: Give many baths
- 🧸 **Player**: Buy 15 toys for your pet

---

## ⚙️ **Settings Panel**

Customize your game experience!

### **How to Access:**
Click the ⚙️ button in the header

### **Settings Categories:**

#### 🐾 **Choose Your Pet**

Select from 6 different pet types, each with unique 3D emoji and sounds:

1. **🐶 Dog**
   - Sound: "Arf arf" bark
   - Appearance: Dog face emoji
   - Personality: Loyal and energetic

2. **🐱 Cat**
   - Sound: Complex meow with vibrato
   - Appearance: Cat face emoji
   - Personality: Independent and elegant

3. **🐦 Bird**
   - Sound: Three chirps
   - Appearance: Bird emoji
   - Personality: Cheerful and active

4. **🐰 Rabbit**
   - Sound: Soft squeak
   - Appearance: Rabbit face emoji
   - Personality: Gentle and shy

5. **🦊 Fox**
   - Sound: Quick yip
   - Appearance: Fox face emoji
   - Personality: Clever and playful

6. **🐻 Bear**
   - Sound: Deep growl
   - Appearance: Bear face emoji
   - Personality: Calm and cuddly

**Effect:** Changes pet emoji, sounds, behaviors, and thought bubbles instantly!

#### 🎮 **Game Settings**

**Stat Decay Speed:**
- **Slow (0.5x)**: Stats decrease at half speed - easier gameplay, perfect for beginners
- **Normal (1x)**: Default balanced decay rate - recommended
- **Fast (1.5x)**: Stats decrease faster - challenging gameplay for experts

**Sound Effects:**
- Toggle sound effects on/off (master switch)
- Includes pet-specific sounds (bark, meow, chirp, etc.)
- Includes UI sounds (level up, money, error, etc.)

**Sound Mode:**
- **Game Sounds (Synthesized)** - Default mode
  - Uses Web Audio API for real-time synthesis
  - No files needed - works immediately
  - Lightweight and always available
- **Realistic Sounds (MP3)** - Optional mode
  - Uses MP3 audio files for authentic animal sounds
  - Requires MP3 files in sounds/ folder
  - More realistic and immersive
  - Smart fallback: Uses synthesized sounds if MP3 files missing
- **How to Add MP3 Files:**
  - Open `sounds/download-helper.html` for easy download links
  - See `SOUND_INSTALLATION_GUIDE.md` for complete guide

**Particle Effects:**
- Enable/disable heart and sparkle particles
- Improves performance on slower devices
- Recommended: Keep ON for best visual experience

**Auto-save:**
- Enable: Game saves automatically after every action (recommended)
- Disable: Manual saves only (not recommended - risk losing progress)

#### 🎨 **Theme & Appearance**

**Container Theme** (Main Window):
Choose your main interface style:
1. **Dark Mode** (Default) - Modern dark gradient
2. **Light Mode** - Clean white interface
3. **Midnight Blue** - Deep cosmic blue
4. **Dark Forest** - Teal-green forest theme
5. **Dark Sunset** - Purple sunset vibes
6. **Deep Ocean** - Dark aquatic theme

**Background Theme** (Outer Gradient):
Choose the background behind your game:
1. **Purple Gradient** (Default) - Classic purple to violet
2. **Ocean Blue** - Light blue to teal
3. **Sunset Pink** - Pink to coral
4. **Forest Green** - Dark blue-green
5. **Cosmic Purple** - Multi-tone purple space theme
6. **Fire Red** - Red to orange energy
7. **Aurora** - Bright blue icy theme
8. **Night Sky** - Dark purple-blue night

**Total Combinations**: 6 containers × 8 backgrounds = **48 unique looks!**

#### ⚠️ **Danger Zone**

**Reset All Progress:**
- Permanently deletes all save data
- Resets pet to level 1
- Clears all achievements and badges
- Resets all statistics and money
- Clears activity log
- **CANNOT BE UNDONE** - Use with extreme caution!
- Shows confirmation before resetting

---

## 💾 **Save System**

### **What Gets Saved:**
Complete game state:
- Pet name and type
- All stats (health, hunger, happiness, energy)
- Age and level
- Experience and XP to next level
- Growth stage and size
- Mood and sleep state
- All interaction counts (pet, feed, play, heal, bath, train, vet, chore, toy, trick)
- Money (wallet, total earned, total spent)
- Savings goal and saved amount
- All achievements (7 total)
- All badges (10 total)
- Activity log (last 10 actions)
- All settings preferences
- Creation date and total time played

### **When It Saves:**
- Automatically after every action (if auto-save enabled)
- When changing settings
- When switching pet types
- When changing themes
- On achievement unlock
- On badge unlock
- On level up

### **Where It's Saved:**
- Browser's localStorage
- Persists between sessions
- Specific to this browser
- No server required
- No account needed

---

## 🎯 **Tips for Using Analytics**

1. **Track Your Care Quality**
   - Check the care rating regularly
   - Aim for 5 stars!
   - Balance all 4 stats

2. **Monitor Interaction Balance**
   - See which actions you use most
   - Try balancing different activities
   - Optimize for XP gain

3. **Set Personal Goals**
   - Challenge yourself to reach 100 pets
   - Try to maintain high stats
   - Unlock all achievements and badges

4. **Watch Growth Progress**
   - Track how quickly your pet levels up
   - See how interactions affect XP gain
   - Monitor growth stage transitions

5. **Time Management**
   - Check time played statistics
   - See your daily interaction rate
   - Track when you're most active

6. **Financial Tracking**
   - Monitor earning vs spending
   - Track progress toward savings goal
   - See spending patterns

---

## 🔧 **Tips for Using Settings**

1. **Experiment with Pet Types**
   - Try all 6 pet types
   - Listen to different sounds
   - Find your favorite emoji!

2. **Adjust Difficulty**
   - New players: Use "Slow" decay speed
   - Experienced: Try "Fast" for challenge
   - Match difficulty to playtime availability

3. **Performance Issues?**
   - Disable particle effects for better performance
   - Disable sound effects if needed
   - Change to simpler theme (Light Mode)

4. **Customize Your Experience**
   - Pick a theme that matches your mood
   - Change pet type to match preferences
   - Try all 48 theme combinations

5. **Sound Preferences**
   - Some pets have quieter sounds (rabbit)
   - Some have complex sounds (cat, bird)
   - Toggle sounds off if you prefer silent play

6. **Before Resetting**
   - Take a screenshot of your analytics!
   - Make sure you really want to start over
   - Achievements and badges can't be recovered
   - Money and stats will be lost

---

## 📱 **Responsive Design**

Both panels are fully responsive:
- Three-column layout on desktop
- Mobile-friendly compact layouts
- Touch-friendly buttons
- Scrollable content where needed
- Adaptive grids

---

## 🎨 **Visual Features**

### **Settings Modal:**
- Smooth fade-in animation
- Hovering effects on pet selection
- Selected pet highlighted with glow
- Color-coded danger zone (red theme)
- Organized sections

### **Analytics Modal:**
- Animated progress bars
- Color-coded statistics
- Card-based layout for organization
- Star rating system
- Real-time data updates

### **Both Modals:**
- Click outside to close
- Close button (×) with hover effect
- Backdrop blur effect
- Smooth transitions
- Scrollable content

---

## 🚀 **Quick Access**

**Current access:**
- ⚙️ Button → Settings
- 📊 Button → Analytics
- ❓ Button → Help & Tutorial
- ESC or click outside → Close modal
- Tab buttons → Switch between stats tabs

---

## 💡 **Pro Features**

### **Activity Logging:**
- Tracks last 10 activities
- Shows timestamps
- Compact, scrollable list
- Automatic updates

### **Badge System:**
- 10 total badges to unlock
- Real-time tracking
- Visual locked/unlocked states
- Unlock notifications

### **Money Tracking:**
- Wallet balance
- Spending progress bar
- Earnings history
- Savings goal system
- Complete financial overview

---

## 🎯 **Optimization Tips**

1. **For Best Performance:**
   - Keep auto-save ON
   - Enable particles (they're optimized)
   - Any theme works smoothly

2. **For Best Experience:**
   - Enable sound effects to hear pet sounds
   - Try different pet types for variety
   - Check analytics regularly
   - Customize themes to your preference

3. **For Analytics Accuracy:**
   - Let analytics track your progress
   - Don't reset unless necessary
   - Build up a good history

---

Enjoy your enhanced PixelPaw experience with comprehensive settings and detailed analytics! 🐾✨
