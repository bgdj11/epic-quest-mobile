# EpicQuest - Your Life, Gamified

## About The Project

EpicQuest is an innovative Android application that revolutionizes personal productivity by transforming mundane daily tasks into thrilling RPG adventures. Every task becomes a quest, every completed goal brings you closer to leveling up, and every challenge conquered earns you legendary rewards. Built with Java and powered by Firebase, EpicQuest combines the addictive mechanics of role-playing games with real-world productivity, making personal growth an epic journey worth embarking on.

Whether you're conquering work deadlines, maintaining healthy habits, or crushing personal goals, EpicQuest turns you into the hero of your own story. Team up with friends in powerful alliances, face formidable bosses together, and watch as your virtual character grows stronger with every real-world achievement.

## Key Features

### Gamification System
- **Experience Points (XP)**: Earn XP by completing tasks
- **Level System**: Progress through levels with increasing XP requirements
- **Player Profile**: Track your avatar, level, title, and achievements
- **Badges**: Showcase completed special missions
- **Virtual Currency**: Earn coins to purchase in-game items

### Task Management
- **Create Tasks**: Add tasks with title, description, category, difficulty, and deadline
- **Task Categories**: Organize tasks (Work, Personal, Study, Health, Shopping, Other)
- **Difficulty Levels**: Choose from Very Easy, Easy, Hard, or Extremely Hard (affects XP rewards)
- **Task Status**: Track active, completed, missed, or cancelled tasks
- **Daily Tasks**: View and manage tasks scheduled for today
- **Task History**: Review all completed tasks with completion logs

### Social Features
- **Friends System**: Add friends by scanning QR codes
- **Alliances**: Create or join alliances with friends
- **Public Profiles**: View other players' stats, badges, and active equipment
- **Leaderboards**: Compare your progress with friends

### Special Missions (Boss Battles)
- **Alliance Missions**: Team up with alliance members to defeat bosses
- **Boss Health System**: Reduce boss HP by completing daily tasks
- **Time-Limited**: Complete missions before the deadline
- **Alliance Rewards**: Earn special rewards for your entire alliance

### Statistics & Progress
- **Consecutive Active Days**: Track your daily consistency
- **Task Completion Charts**: Visualize tasks by category, difficulty, and status
- **XP Progress**: Monitor your XP gains over the last 7 days
- **Mission Statistics**: View started and completed special missions
- **Longest Streak**: See your best completion streak

### Shop System
- **Buy Items**: Purchase equipment and power-ups with coins
- **Active Items**: Equip items to your profile
- **Item Management**: View and manage your inventory

## Technical Stack

- **Language**: Java
- **Platform**: Android (SDK 33)
- **Backend**: Firebase
  - Firebase Authentication (Email/Password)
  - Cloud Firestore (Database)
  - Firebase Storage (Future implementation)
- **UI Components**: Material Design Components
- **Charts**: MPAndroidChart library
- **QR Code**: ZXing library
- **Build Tool**: Gradle

## Architecture

- **Repository Pattern**: Clean separation between data and UI layers
- **Firebase Integration**: Real-time database updates
- **Fragment-Based Navigation**: Modern Android navigation patterns
- **Custom Managers**: LevelManager, NotificationManager for game logic

## Authentication

- **Email/Password Registration**: Secure user account creation
- **Login System**: Persistent sessions with Firebase Auth
- **Password Management**: Change password functionality
- **Auto-Login**: Stay logged in until manual logout

##  Getting Started

### Prerequisites
- Android Studio (Latest version recommended)
- Android SDK 33+
- Firebase account
- Google Services JSON file

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/epic-quest.git
```

2. Open the project in Android Studio

3. Add your `google-services.json` file to the `app/` directory

4. Sync Gradle and build the project

5. Run on an emulator or physical device

## 📝 Firebase Setup

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable Email/Password authentication
3. Create a Firestore database
4. Download `google-services.json` and place it in the `app/` directory

### Firestore Structure
```
users/
  {uid}/
    - username
    - email
    - level
    - xp
    - coins
    - avatar
    - title
    - specialMissionsWon
    tasks/
      {taskId}/
    completionLogs/
      {logId}/
    friends/
      {friendId}/
    alliances/
      {allianceId}/

alliances/
  {allianceId}/
    - name
    - members[]
    specialMissions/
      {missionId}/

items/
  {itemId}/
    - name
    - price
    - category
```

## Core Functionalities

### Task Lifecycle
1. User creates a task with details and deadline
2. Task appears in daily list if scheduled for today
3. User marks task as complete → earns XP based on difficulty
4. System logs completion and updates statistics
5. Missed tasks are tracked if not completed by deadline

### XP & Leveling System
- Each difficulty level awards different XP amounts
- Level requirements increase exponentially
- Progress bar shows XP until next level
- Leveling up unlocks new titles and features

### Alliance Boss Battles
1. Alliance leader starts a special mission
2. Boss has HP based on alliance size
3. Members reduce boss HP by completing daily tasks
4. Mission must be completed before deadline
5. Success awards all members with special badges

## 📦 Dependencies

```gradle
dependencies {
    // Firebase
    implementation platform('com.google.firebase:firebase-bom:32.7.0')
    implementation 'com.google.firebase:firebase-auth'
    implementation 'com.google.firebase:firebase-firestore'
    
    // Material Design
    implementation 'com.google.android.material:material:1.11.0'
    
    // Charts
    implementation 'com.github.PhilJay:MPAndroidChart:v3.1.0'
    
    // QR Code
    implementation 'com.google.zxing:core:3.5.2'
    
    // AndroidX
    implementation 'androidx.appcompat:appcompat:1.6.1'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
    implementation 'androidx.navigation:navigation-fragment:2.7.6'
}
```

## Why EpicQuest?

Traditional task management apps can feel monotonous and uninspiring. EpicQuest changes the game by making productivity fun, engaging, and social. By leveraging proven gamification mechanics, we've created an experience that motivates users to not just track their tasks, but to genuinely look forward to completing them. The social aspect adds accountability and camaraderie, turning personal growth into a shared adventure.

## Team

This project was developed as part of Mobile Applications course (2025).


**Note**: This is a university project created for educational purposes. Feel free to use it as a reference for learning Android development with Firebase integration.
