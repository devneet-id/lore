# Rune — Map

The ten origin runes. Aether flows through all of them.

```mermaid
graph TD
    RUNE([Rune])
    RUNE --> Aether
    RUNE --> Chanter
    RUNE --> Whisper
    RUNE --> Weaver
    RUNE --> Forger
    RUNE --> Cipher
    RUNE --> Keeper
    RUNE --> Crafter
    RUNE --> Specter
    RUNE --> Minister
```

## Built-in runites and modes

```mermaid
graph TD
    CAST([your runite · cast]) --> RUNITE[@runite/]
    RUNITE --> awakening
    RUNITE --> main[rune · main hall]
    RUNITE --> grimoire
    RUNITE --> reliquary
    RUNITE --> sentinel
    sentinel -->|--evolution| EVO["@evolution/ · runes of your own"]
    sentinel -->|--federation| FED["@federation/ · your reliquary"]
    sentinel -->|--liberation| LIB["@liberation/ · your PHP runtime"]
    reliquary -.->|relics| FED
```
