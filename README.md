# Vehicle Manager Card

Card Lovelace pentru integrarea
[Vehicle Manager](https://github.com/alinalecu2013/ha-vehicle-manager):
model 3D rotativ al masinii, caracteristici si acte (RCA, ITP, rovinieta, revizie,
distributie), cu meniu **Themes** (culori, fonturi, aspect, imagine de fundal) si istoric de
**Costuri** (cheltuieli pe categorii si pe ani, export CSV), **Dosar** cu actele scanate si
cardul **Garaj** cu toate masinile. In romana sau engleza, dupa limba din Home Assistant.

![Vehicle Manager Card](https://raw.githubusercontent.com/alinalecu2013/vehicle-manager-card/main/images/card.png)

<p align="center">
  <img src="https://raw.githubusercontent.com/alinalecu2013/vehicle-manager-card/main/images/phone.png" alt="Cardul pe telefon (tema Sunset)" width="300">
  &nbsp;
  <img src="https://raw.githubusercontent.com/alinalecu2013/vehicle-manager-card/main/images/themes.png" alt="Meniul Themes" width="520">
</p>

<sub>Capturi cu date demonstrative.</sub>

> **Necesita integrarea Vehicle Manager.** Cardul afiseaza datele vehiculelor si
> salveaza tema prin integrare; singur nu are ce afisa.

## Instalare prin HACS

[![Deschide in HACS](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=alinalecu2013&repository=vehicle-manager-card&category=plugin)

1. Instaleaza mai intai integrarea
   [Vehicle Manager](https://github.com/alinalecu2013/ha-vehicle-manager).
2. **HACS &rsaquo; &vellip; &rsaquo; Depozite personalizate**: adauga
   `https://github.com/alinalecu2013/vehicle-manager-card` cu tipul **Dashboard**.
3. Cauta **Vehicle Manager Card** si apasa **Descarca**. HACS adauga singur resursa
   Lovelace.
4. Restarteaza Home Assistant (ca integrarea sa nu mai incarce copia ei a cardului),
   apoi reincarca pagina. Pe telefon: **Setari &rsaquo; Companion app &rsaquo; Depanare
   &rsaquo; Reset frontend cache**.

Instalarea cardului din HACS e optionala: integrarea include si ea cardul si il incarca
automat. Cand cardul e instalat din HACS, integrarea detecteaza asta si lasa HACS sa-l
gestioneze, deci primesti actualizarile cardului separat, in HACS.

## Utilizare

```yaml
type: custom:vehicle-manager-card
```

Pentru pagina principala de pe telefon exista **modul compact** (masina + actele cele
mai urgente):

<p align="center"><img src="https://raw.githubusercontent.com/alinalecu2013/vehicle-manager-card/main/images/compact.png" alt="Modul compact pe telefon" width="380"></p>

```yaml
type: custom:vehicle-manager-card
compact: true
navigation_path: /lovelace/masini   # optional
```

Cardul Garaj, cu toate vehiculele:

```yaml
type: custom:vehicle-manager-garage-card
```

Atingerea unei mașini deschide dashboardul **AUTO Check** (sau cel ales în editor) cu mașina
respectivă selectată.

Toate optiunile si functiile sunt descrise in
[documentatia integrarii](https://github.com/alinalecu2013/ha-vehicle-manager#cardul).

## Dezvoltare

Sursa cardului se afla in depozitul integrarii
(`custom_components/vehicle_manager/www/vehicle-manager-card.js`); acest depozit primeste
o copie la fiecare versiune. Modificarile se fac acolo.
