# Jarred — AI Short-Video Marketing for SMBs

Jarred helps SMBs create short marketing videos faster.
Input product info + target audience → generate scripts, storyboards, captions, and multi-variant creatives for ad testing.

## What it does
- Script generation (hook, benefits, CTA)
- Storyboard & shot list (scene-by-scene)
- Captions/subtitles + multi-variant creatives (A/B testing)

## Planned Azure stack
- **Azure OpenAI**: script/storyboard/caption generation
- **Azure App Service**: web & API backend
- **Azure Storage**: assets (images/video/audio) + outputs
- **GPU compute**: video generation/rendering & inference acceleration (as needed)

## Architecture (draft)
flowchart LR
U[Business User] --> W[Web App]
W --> API[Backend API - App Service]
API --> AOAI[Azure OpenAI]
API --> ST[Azure Storage]
API --> Q[Jobs and Workers]
Q --> GPU[GPU Compute]
GPU --> ST
ST --> W
flowchart LR
U[Business User] --> W[Web App]
W --> API[Backend API (App Service)]
API --> AOAI[Azure OpenAI]
API --> ST[Azure Storage]
API --> Q[Jobs/Workers]
Q --> GPU[GPU Compute]
GPU --> ST
ST --> W
