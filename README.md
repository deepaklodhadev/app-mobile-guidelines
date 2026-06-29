# ================================
# EXPO APP FULL FLOW SUMMARY
# ================================

# 1. Install Node.js
# https://nodejs.org/

# Verify installation
node -v
npm -v

# ================================
# CREATE EXPO APP
# ================================

npx create-expo-app MyApp

cd MyApp

# Start development server
npx expo start

# Install Expo Go app in mobile
# Scan QR code
# App opens in mobile

# ================================
# DURING DEVELOPMENT
# ================================

# After code changes:
# Save file -> app auto refreshes in mobile

npx expo start

# ================================
# BUILD APK
# ================================

# Install EAS
npm install -g eas-cli

# Login
eas login

# Configure project
eas build:configure

# Fix project ID if needed
eas project:init

# ================================
# CREATE eas.json
# ================================

# Create eas.json file in root folder

{
  "cli": {
    "version": ">= 10.2.0"
  },
  "build": {
    "preview": {
      "android": {
        "buildType": "apk"
      }
    }
  }
}

# ================================
# BUILD APK
# ================================

eas build --platform android --profile preview

# Expo gives APK download link

# Download APK
# Install in mobile

# ================================
# AFTER APK INSTALLATION
# ================================

# SMALL CHANGES (UI / Logic)
# No APK reinstall needed

eas update

# Open app again in mobile
# Changes automatically update

# ================================
# BIG CHANGES (Native Packages)
# ================================

# If added:
# - camera
# - sqlite
# - new native library
# - permissions
# Then rebuild APK

eas build --platform android --profile preview

# Install new APK again

# ================================
# CLEAR CACHE IF NEEDED
# ================================

npx expo start -c

# ================================
# DONE
# ================================
