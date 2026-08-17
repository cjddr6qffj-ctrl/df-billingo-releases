# DF Billingo — letöltések

Ez a tároló **kizárólag telepítőket és frissítési metaadatot** tartalmaz.
Forráskód nincs benne, és nem is kerülhet bele.

## Letöltés

A legfrissebb stabil verzió mindig itt:

**→ [Legfrissebb kiadás](../../releases/latest)**

| Amit telepítesz | Fájl |
|---|---|
| Windows kliens (munkaállomásokra) | `DFBillingo-Setup-<verzió>.exe` |
| Windows szerver (a központi gépre, egyszer) | `DFBillingoServer-Setup-<verzió>.exe` |
| Minden egyben, telepítési lappal | `DFBillingo-Windows-Current.zip` |

## Telepítési sorrend

Ha a Windows gép egyszerre központi szerver **és** munkaállomás:

1. `DFBillingoServer-Setup-<verzió>.exe` — **rendszergazdaként**. Windows-
   szolgáltatást telepít, és tűzfalszabályt vesz fel a 8756-os TCP-portra.
2. `DFBillingo-Setup-<verzió>.exe` — **normál felhasználóként**. A saját
   mappádba települ, nem kér rendszergazdát.

Csak munkaállomás esetén elég a 2. lépés.

## „Ismeretlen kiadó" figyelmeztetés

A telepítők **nincsenek kódaláírva** — ehhez tanúsítvány kell, ami még nincs
beszerezve. A Windows SmartScreen ezért figyelmeztet:

> További információ → Futtatás mindenképp

Ez nem hiba, hanem a hiányzó tanúsítvány következménye. Az ellenőrzőösszeg
(`SHA256SUMS.txt`) alapján meggyőződhetsz róla, hogy a letöltött fájl
sértetlen:

```powershell
Get-FileHash .\DFBillingo-Setup-<verzió>.exe -Algorithm SHA256
```

## Frissítési manifeszt

A `manifest/stable.json` írja le, mi a jelenlegi stabil verzió, és hol van a
csomagja. Ed25519-cel aláírt; az ellenőrző nyilvános kulcs a
`manifest/update-public-key.txt` fájlban van, és be van építve az
alkalmazásba is.

## Adatvédelem

Ebben a tárolóban nincs és nem is lehet: forráskód, API-kulcs, adatbázis,
számla, ügyféladat, napló.
