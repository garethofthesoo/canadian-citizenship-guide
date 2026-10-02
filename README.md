# Citizenship Coach

**Live app:** https://canada-dun.vercel.app

A free study app for the Canadian citizenship test, built for people who need a lot of repetition and whose first language is not English. Every fact in the official study guide *Discover Canada* is turned into a card you can read, hear, and get quizzed on, until you know it.

## What it does

- **437 fact cards, 963 questions**, covering all twelve sections of *Discover Canada*: the test and the oath, rights and responsibilities, who we are, history (two parts), modern Canada, how Canadians govern themselves, federal elections, the justice system, symbols, the economy, and the regions.
- **English and French**: switch the whole app with the EN / FR toggle. French text comes from the official French edition of the guide, not machine translation.
- **Arabic support**: every card has an Arabic translation hidden behind "Show translation". Tap any English word to see its Arabic meaning and hear it, Duolingo style. More languages can be added the same way.
- **Natural audio**: a natural female voice reads every card. *Play* reads the sentence and highlights each word as it is spoken. *Slow, word by word* reads one word at a time with a pause between words, for learners who are still building their English.
- **Learns from your mistakes**: a wrong answer brings that card back later in the same lesson and again the next day. Correct answers push a card further out (1, 3, 7, 14, 30 days). No hearts, no penalties; it is a learning app.
- **Review and Weak spots**: Review shows everything due today plus anything you got wrong. Weak spots replays the facts you miss most.
- **Mock tests**: once every unit is complete, five 100-question mock tests unlock, plus a real-exam simulator (20 questions, 30 minutes, pass mark 15) that matches the actual test format. Wrong answers feed back into your review.
- **My Gov**: the test asks about your own representatives. Pick your province and the capital fills in; enter your MP, premier, mayor and so on and the app quizzes you on them.
- **Works offline, saves per device**: install it to your phone's home screen. Progress is stored on the device, with copy-and-paste backup and restore in Settings.

## How to study

1. Open a unit and go through the lesson: read each new fact (press Play, or tap words you don't know), then answer the questions.
2. Finish all twelve units. The progress ring on each unit shows how many of its cards you have learned.
3. Use Review every day. It is short and it is the part that makes facts stick.
4. When the mock tests unlock, take them until you pass comfortably, then try the simulator.
5. Fill in My Gov and check the names shortly before your test; office holders change.

## Repository layout

This repository holds the deployed site. Vercel serves it as-is, no build step.

```
index.html      the whole app (content, dictionary and code in one file)
manifest.json   web-app manifest (home-screen install)
sw.js           service worker (offline cache)
icon-192.png / icon-512.png
audio/
  manifest.json       index of audio clips
  <card-id>.mp3       one clip per fact (437)
  words/<word>.mp3    one clip per word, used by the slow mode (3,144)
```

The source project (chapter text extracted from the official guide, the unit JSON files, the Arabic dictionary, the build script and the audio generators) is kept separately; `index.html` is built from it.

## Updating the site

Replace `index.html` (or any file) in this repository, commit, and push to `main`. Vercel redeploys automatically within about a minute. The audio folder only needs to change when the card text changes.

## Content and credits

- Facts, French text and sample questions are from *Discover Canada: The Rights and Responsibilities of Citizenship* / *Découvrir le Canada*, published by Immigration, Refugees and Citizenship Canada. © His Majesty the King in Right of Canada. Used for non-commercial study.
- The maple leaf uses the official geometry of the National Flag of Canada.
- Arabic translations and the word dictionary are study aids only and are not official.
- Audio was generated with the Kokoro open-source neural text-to-speech model.

This app is free and is not affiliated with IRCC or the Government of Canada. The official guide is the authority for the test: https://www.canada.ca/en/immigration-refugees-citizenship/corporate/publications-manuals/discover-canada.html
