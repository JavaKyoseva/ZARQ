# 📲 ZARQ  
**Zero-Authentication Request Querier**

A lightweight Android application designed for research and demonstration purposes related to message‑trigger simulations, request crafting, and protocol behavior analysis.  
This project **does not send real SMS**, **does not bypass any system**, and **must not be used for harmful actions**.  
It is provided *purely for educational and security‑testing demonstrations*.

---

## 📌 Features
- Generates simulated message‑trigger payloads  
- Demonstrates how client-side components handle custom requests  
- Shows security students how build pipelines and modular Android components interact  
- Fully offline and isolated test environment  
- Clean, minimal and extensible structure

---

## ⚠️ Educational Notice
This repository exists **ONLY** for:
- Learning how Android build processes work  
- Demonstrating client-side request modeling  
- Showing how modules can be structured inside an APK project  

It is **NOT** intended for real-world messaging, spoofing, or unauthorized operations.  
Using this project outside legal boundaries is **strictly prohibited**.

---

## 🛠️ Build Instructions
Because the repository contains the decoded project files (smali/java/resources), users must **rebuild** the APK manually.

### 1️⃣ Clone the repository
```bash
git clone https://github.com/JavaKyoseva/ZARQ.git
cd ZARQ
```

### 2️⃣ Build using Gradle (normal Android project)
If your project is a standard Android Studio project:
```bash
./gradlew assembleDebug
```

The resulting APK appears at:
```
/app/build/outputs/apk/debug/app-debug.apk
```

### 3️⃣ For decoded APK projects (smali-based rebuild)
If the repo contains *decoded* APK content (e.g. via apktool), rebuild like this:

```bash
apktool b ZARQ -o ZARQ_Rebuilt.apk
```

Then sign the APK:
```bash
keytool -genkey -v -keystore zarq.keystore -alias zarq -keyalg RSA -keysize 2048 -validity 10000
jarsigner -keystore zarq.keystore ZARQ_Rebuilt.apk zarq
```

(optional) Zipalign:
```bash
zipalign -v 4 ZARQ_Rebuilt.apk ZARQ_Aligned.apk
```

## 📜 License
This project is released **only for educational and research purposes**.  
Any misuse is strictly the responsibility of the user.

---
