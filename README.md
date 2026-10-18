# Protokoll

Protokoll je aplikácia pre Windows, ktorá z nahrávky stretnutia vytvorí prepis,
štruktúrovaný súhrn a návrhy úloh. Pri nahrávke hovoru rozlíši hovoriacich a mená
účastníkov vie prečítať z okna hovoru. Všetko spracovanie beží na vašom počítači;
zvuk, prepis ani súhrn ho neopúšťajú.

Tento repozitár obsahuje iba vydania aplikácie, nie jej zdrojový kód.

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

Po prvom spustení stiahnite v aplikácii tri modely:

- **Nastavenia → Prepis:** odporúčaný prepisovací model (asi 715 MB) a model
  rozlíšenia hovoriacich (asi 107 MB).
- **Nastavenia → AI spracovanie:** model **Gemma 4 E4B** pre súhrny a úlohy
  (asi 4,6 GB).

Všetky sa sťahujú z pevne určenej verzie a použijú sa až po overení kontrolného
súčtu. Potom aplikácia funguje aj bez internetu.

## Hovoriaci a mená z hovoru

Pri nahrávke hovoru Protokoll rozlíši hlasy: vaše repliky sú „Ja“, ostatné
„Účastník 1, 2, …“. Počas nahrávania nájde okno hovoru podľa mikrofónu a zvuku
a prečíta z neho mená účastníkov cez rozhranie prístupnosti Windows – bez
rozšírenia prehliadača, okno netreba presúvať. V Jitsi Meet sa mená priradia
hlasom samy; v Google Meet a Microsoft Teams na webe sa ponúknu a meno hlasu
vyberiete jedným klikom v plávajúcom paneli. Čítanie okna vypnete v paneli
nahrávania.

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
odoslanie do vášho OpenProjectu, ktoré vždy potvrdzujete vy. Z okna hovoru sa
čítajú iba mená a stav mikrofónu účastníkov; chat ani titulky nie a nič z toho
sa nikam neposiela.

## Nahlásenie problému

Problém nahláste v [Issues](../../issues/new/choose) cez formulár **Nahlásiť problém**:

1. V **Nastavenia → Diagnostika** si opíšte verziu aplikácie.
2. Tým istým miestom otvorte priečinok s logmi a priložte najnovší súbor. Log
   neobsahuje prepis, súhrn, úlohy, token ani cesty k vašim súborom.
3. Opíšte, čo ste robili, čo ste čakali a čo sa stalo.

Hlásenia sú verejné. Nevkladajte do nich obsah skutočných stretnutí ani
screenshoty s ich textom.

## Licencie

Protokoll obsahuje súčasti tretích strán, napríklad FFmpeg (LGPL-2.1) s kodekom
Opus (BSD), NVIDIA NeMo-Speech.cpp (Apache-2.0), whisper.cpp a llama.cpp (MIT) a
knižnice NVIDIA CUDA. Ich licencie a pôvod sú v súbore `THIRD_PARTY_NOTICES.md` v
priečinku inštalácie. Modely sa sťahujú pri prvom spustení pod vlastnými
licenciami: slovenský Parakeet od KInIT (CC-BY-4.0), Nemotron 3 Diarization od
NVIDIA (OpenMDW 1.1) a Gemma 4 od Google.

Zdrojový kód pribaleného FFmpeg je priložený ku každému vydaniu ako
`ffmpeg-<verzia>.tar.xz` a `opus-<verzia>.tar.gz`.
