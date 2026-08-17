# Engeto_BI: Makroekonomický přehled ČR a mezinárodní srovnání (2006–2018)

Interaktivní Power BI dashboard analyzující makroekonomický vývoj v České republice v letech 2006–2018, zaměřený na mzdy podle odvětví, vývoj cen potravin, reálnou kupní sílu obyvatelstva a mezinárodní srovnání HDP evropských států.

## O projektu

Projekt vznikl jako semestrální práce v rámci kurzu Datový analytik s Pythonem (Engeto). Cílem bylo propojit primární datovou sadu o domácí ekonomice (mzdy podle odvětví, ceny potravin) se sekundární mezinárodní datovou sadou (HDP, populace a Gini index evropských států) do jednoho konzistentního datového modelu a postavit nad ním přehledný, interaktivní a vizuálně sjednocený report.

## Struktura reportu

Report je rozdělen do 4 stránek propojených navigačními tlačítky:

### 1. Hlavní přehled ČR
* Multi-row karta s klíčovými metrikami (Průměrné HDP, Průměrná cena potravin, Průměrná mzda).
* Spojnicový graf dlouhodobého vývoje průměrných mezd v porovnání s cenami potravin.
* Filtrování podle roku a odvětví.

### 2. Analýza mezd podle odvětví
* Vodorovný pruhový graf průměrných mezd napříč sektory hospodářství.
* Spojnicový graf vývoje průměrné mzdy v čase.
* Odkaz na primární zdroj dat (ČSÚ).

### 3. Vývoj cen potravin a reálná kupní síla
* Spojnicový graf vývoje cen jednotlivých potravinových položek v letech 2006–2018.
* Tabulka s průměrnými cenami jednotlivých potravin.
* Filtrování podle roku a cenové kategorie (nad/pod průměrem), postavené na kalkulovaném sloupci.

### 4. Mezinárodní srovnání a pozice HDP
* Vodorovný pruhový graf celkového HDP evropských států.
* Filtrování podle roku a státu.

## Datový model

* **Primární tabulka:** Mzdy podle odvětví, ceny potravin, roky (Česká republika).
* **Sekundární tabulka:** HDP, populace a Gini index evropských států podle roku.
* **Calendar:** Samostatná kalendářová dimenze propojující obě tabulky přes sloupec Year (relace 1:M, star schema), namísto přímé vazby mezi primární a sekundární tabulkou.

## Použité technologie a funkce Power BI

* **Rozsah:** 4 stránky.
* **Typy vizuálů:** Vodorovné pruhové grafy, spojnicové grafy, tabulka, multi-row karta, slicery, navigační tlačítka.
* **Propojení tabulek:** Datový model se star schématem přes kalendářovou tabulku.
* **DAX:**
    * Measures – např. průměrná mzda, průměrná cena potravin, průměrné HDP.
    * Calculated column – kategorizace cen potravin (nad/pod průměrem).
* **Formátování:** Vlastní formát měny (Kč) u finančních metrik.
* **Grafická úprava:** Vlastní barevná paleta, sjednocené fonty a nadpisy napříč stránkami, zarovnané a promyšleně rozmístěné vizuály (jednotné okraje, bez prázdných ploch).
* **Interaktivita:** Slicery pro rok, odvětví, stát a cenovou kategorii; navigace mezi stránkami pomocí tlačítek; křížové filtrování mezi vizuály.

## Datové zdroje

* **Primární tabulka:** Vývoj průměrných mezd podle odvětví a cen potravin v ČR (ČSÚ).
* **Sekundární tabulka:** Makroekonomická data (HDP, populace, Gini index) evropských států.
