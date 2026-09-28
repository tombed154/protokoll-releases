# Protokoll

Protokoll je aplikácia pre Windows, ktorá z nahrávky stretnutia vytvorí prepis,
štruktúrovaný súhrn a návrhy úloh. Všetko spracovanie beží na vašom počítači;
zvuk, prepis ani súhrn ho neopúšťajú.

Tento repozitár obsahuje iba vydania aplikácie, nie jej zdrojový kód.

## Ukážka aplikácie

https://github.com/user-attachments/assets/88abd75e-fc59-48fa-87be-23b3eb520091

Ukážka používa vymyslené stretnutie.

## Inštalácia

1. Otvorte [najnovšie vydanie](../../releases/latest) a stiahnite súbor
   `Protokoll_<verzia>_x64-setup.exe`.
2. Spustite ho. Inštalátor nie je digitálne podpísaný, preto Windows SmartScreen
   zobrazí varovanie o neznámom vydavateľovi. Kliknite na **Ďalšie informácie** a
   **Spustiť aj tak**.
3. Inštalácia prebehne pre vášho používateľa a nepotrebuje administrátorské práva.

Súbory `.sig` a `latest.json` pri vydaní používa aplikácia na overenie
aktualizácie; sťahovať ich nemusíte.

## Čo treba po prvom spustení

| Požiadavka                            | Poznámka                                                                        |
| ------------------------------------- | ------------------------------------------------------------------------------- |
| Windows 10/11, 64-bit                 | Iná platforma nie je podporovaná.                                               |
| Približne 11 GB miesta na disku       | Aplikácia, prepisovací model, AI model pre súhrny a pracovné súbory nahrávania. |
| Grafika s ovládačom Vulkan 1.2 / CUDA | Voliteľné. Bez nej beží prepis na procesore, len pomalšie.                      |
| OpenProject a API token               | Voliteľné. Bez nich funguje všetko okrem odoslania do OpenProjectu.             |

Po prvom spustení stiahnite v aplikácii dva modely:

- **Nastavenia → Prepis:** odporúčaný prepisovací model (asi 834 MB).
- **Nastavenia → AI spracovanie:** model **Gemma 4 E4B** pre súhrny a úlohy
  (asi 4,6 GB).

Oba sa sťahujú z pevne určenej verzie a použijú sa až po overení kontrolného
súčtu. Potom aplikácia funguje aj bez internetu.

## Aktualizácie

Protokoll sa raz denne pozrie sem, či nevyšla novšia verzia. Ak áno, v ľavom
paneli sa objaví **Nová verzia …**. V **Nastavenia → Diagnostika** kliknite na
**Aktualizovať a reštartovať**. Aplikácia stiahne novú verziu, overí jej podpis,
zavrie sa a otvorí v novej verzii. Stretnutia, modely a nastavenia ostanú.

Počas nahrávania alebo spracovania sa aktualizácia nespustí. Automatickú kontrolu
vypnete v **Nastavenia → Aplikácia**; kontrola neposiela nič o vás ani o vašich
stretnutiach.

## Vaše dáta

Stretnutia sú lokálne súbory v dátovom adresári aplikácie a odinštalovanie ich
nemaže. Sieť aplikácia používa iba na stiahnutie modelov, kontrolu novej verzie a
odoslanie do vášho OpenProjectu, ktoré vždy potvrdzujete vy.

## Nahlásenie problému

1. V **Nastavenia → Diagnostika** si opíšte verziu aplikácie.
2. Tým istým miestom otvorte priečinok s logmi a priložte najnovší súbor. Log
   neobsahuje prepis, súhrn, úlohy, token ani cesty k vašim súborom.
3. Opíšte, čo ste robili, čo ste čakali a čo sa stalo.

Hlásenie pošlite tomu, od koho máte odkaz na túto stránku. Obsah skutočných
stretnutí do hlásenia nevkladajte.

## Licencie

Protokoll obsahuje súčasti tretích strán, napríklad FFmpeg (LGPL-2.1) s kodekom
Opus (BSD), whisper.cpp a llama.cpp (MIT) a knižnice NVIDIA CUDA. Ich licencie a
pôvod sú v súbore `THIRD_PARTY_NOTICES.md` v priečinku inštalácie.

Zdrojový kód pribaleného FFmpeg je priložený ku každému vydaniu ako
`ffmpeg-<verzia>.tar.xz` a `opus-<verzia>.tar.gz`.
