# 🎛️ OpenGroove – Groovebox Open Source Modulaire

OpenGroove est une machine groovebox/sampler/séquenceur open source inspirée du Digitakt 2. Pensée pour être **modulaire**, **évolutive**, **hackable**, et totalement **documentée**, elle s’adresse aux musiciens, bidouilleurs, makers et développeurs audio.

---

## 🚀 Objectifs

- 16 pistes audio, 16 pistes MIDI
- Séquenceur pas à pas (64 pas, polyrhythmique, microtiming)
- Effets (Delay, Reverb, Chorus, LFO, filtre…)
- Lecture et enregistrement de samples
- Interface simple et rapide
- Matériel open hardware, extensions par modules

---

## 🧩 Structure du projet

```
OpenGroove/
├── firmware/              # Code embarqué C/C++ (RTOS, audio, séquenceur)
├── web-editor/            # Éditeur ou utilitaires Web (config, kits, etc.)
├── hardware/              # Schémas électroniques, PCB, BOM
│   ├── baseboard/         # Carte principale (CPU, Audio, Storage)
│   ├── modules/           # Extensions (MIDI, CV, Pads, Wi-Fi...)
├── docs/                  # Documentation utilisateur et technique
├── tools/                 # Scripts MIDI, transfert de projet, dump sysex
├── samples/               # Kits de sons de démo
└── README.md
```

---

## 🧠 Technologies utilisées

- STM32 / Teensy / CM4 pour le microcontrôleur
- FreeRTOS ou Zephyr RTOS pour l’embarqué
- PCM5102 / WM8731 DAC pour la lecture audio
- SPI Flash ou microSD pour le stockage
- React + WebMIDI API pour l’éditeur de patterns
- Python pour les utilitaires MIDI

---

## 🔌 Modularité matérielle

OpenGroove est conçu comme un **cerveau central** (mainboard) auquel on peut **brancher des modules physiques** :

- MIDI (IN / OUT / THRU)
- CV/Gate (eurorack friendly)
- Extension Wi-Fi
- Plus de pads / encodeurs
- Écrans secondaires

Chaque module communique via **connecteurs standardisés** (SPI / I2C / UART) avec autodétection logicielle.

---

## 📦 Assembler la V1

Voir le dossier `hardware/baseboard` pour les composants requis, le câblage et les instructions de montage.

- ÉTAPE 1 : Flash du firmware sur le microcontrôleur
- ÉTAPE 2 : Connexion du DAC + sortie audio
- ÉTAPE 3 : Test des TRIGs et encodeurs
- ÉTAPE 4 : Test MIDI In/Out
- ÉTAPE 5 : Stockage SD / flash

---

## 🤖 Prompt LLM conseillé

> Tu es un assistant embarqué expert, spécialiste en audio numérique et design modulaire. Ton objectif est de guider un développeur expérimenté en Web mais débutant en hardware, dans la création d’un groovebox open source inspiré du Digitakt. Ton rôle est de fournir des explications claires, des schémas logiques, des recommandations de composants, et des choix d’architecture logiciel embarqué (RTOS, threading, ISR, etc.). Pense en couches logiques indépendantes : audio, UI, stockage, MIDI. Garde en tête l’extensibilité (hardware modulaire, firmware flashable).

---

## 📜 Licence
MIT + CERN-OHL pour le hardware

---

> Ce projet est une exploration de ce que peut être une groovebox communautaire, modulaire et ouverte. Rejoins le projet pour inventer la musique de demain 🛠🎶
