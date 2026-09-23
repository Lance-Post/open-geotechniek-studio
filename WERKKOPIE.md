# Werkkopie 22-09-2026

Deze repository is een privé-werkkopie van
[OpenAEC-Foundation/open-geotechniek-studio](https://github.com/OpenAEC-Foundation/open-geotechniek-studio),
vastgelegd op 22-09-2026 (commit `8182b48`, tag `basis-2026-09-22`). Er wordt gewerkt in branch `versie-2026-09-22`.

## Ophalen

De app gebruikt de Rust-rekenkern uit `crates-warehouse` via een relatief pad. Haal beide repositories op
**naast elkaar** in dezelfde map:

```
git clone https://github.com/Lance-Post/open-geotechniek-studio.git
git clone https://github.com/Lance-Post/crates-warehouse.git
```

## Bouwen

Nodig: Rust (MSVC-toolchain + Visual Studio Build Tools, C++) en Node.js 22.

```
cd open-geotechniek-studio/apps/desktop
npm ci
npm run tauri dev
```

## Wijzigingen van OpenAEC ophalen

Remote `upstream` wijst naar OpenAEC-Foundation (alleen lezen, pushen is geblokkeerd):

```
git fetch upstream
git merge upstream/main
```

GitHub Actions staat uit in deze kopie, zodat de publicatie- en releaseworkflows van OpenAEC hier niet draaien.

## Online versie

De browserversie van deze werkkopie staat op:

**https://lance-post.github.io/open-geotechniek-studio/**

Elke push naar `versie-2026-09-22` die `apps/desktop/**` raakt, publiceert automatisch een nieuwe versie
(workflow `.github/workflows/pages.yml`, circa 2 minuten). Handmatig starten kan via het tabblad Actions.

In de browser ontbreken de onderdelen die het Rust-deel nodig hebben: PDF-rapporten, IFC-export en het openen
van projectbestanden (.ifcgis). Gebruik daarvoor de desktopversie. De experimentele berekeningen zijn in deze
interne versie wél zichtbaar; op de publieke site van OpenAEC staan die uit.
