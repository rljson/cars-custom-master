<!--
@license
Copyright (c) rljson

Use of this source code is governed by terms that can be
found in the LICENSE file in the root of this package.
-->

# @rljson/cars-custom-master

[English](README.md) | Deutsch

[![CI](https://github.com/rljson/cars-custom-master/actions/workflows/quick_check.yaml/badge.svg)](https://github.com/rljson/cars-custom-master/actions/workflows/quick_check.yaml)

Master der Seite custom der cars-Beispiel-App, wo freigegebene Kataloge für Kunden weiterbearbeitet werden.

## Motivation

- Die Seite custom der cars-Beispiel-App betreibt einen eigenen Master,
  wo freigegebene Kataloge für Kunden weiterbearbeitet werden
- Später hält er alle Daten seiner Seite auf `@rljson/server`; vorerst
  antwortet er mit dem Hello World: `GET /`, `GET /api/hello` und
  `GET /health`
- Er läuft als Container in den Stufen `dev`, `test` und `prod`, auch
  hinter einem Proxy, der ihn unter einem Pfad ausliefert und dieses
  Präfix entfernt

## Installation

Das Package ist privat und nicht auf npm veröffentlicht. Hänge von einer
getaggten Version seines Git-Repos ab:

```bash
pnpm add git+ssh://git@github.com/rljson/cars-custom-master.git#semver:^0.0.1
```

## Verwendung

Den Server starten:

```ts
import { start } from '@rljson/cars-custom-master';

await start({ PORT: '3000' });
```

`GET /` antwortet dann mit `Hello from cars-custom-master`.

### Container

Das Image in der Registry `crcars` bauen, getaggt mit der Version:

```bash
az acr build --registry crcars --image cars-custom-master:<version> .
```

## Grenzen

- Hält noch keine Daten, nur den Gruß

## Dokumentation

- Die Guides in [doc/guides](doc/guides)

## Stand

Vor 1.0 — die API kann sich zwischen Minor-Versionen ändern.

## Mitwirken

Siehe [doc/guides/develop-guide.md](doc/guides/develop-guide.md).

## Lizenz

MIT — siehe [LICENSE](LICENSE).
