> **Implementace AI asistence pro generování epikríz v systému Enterprise**
> Cílem projektu je implementovat funkcionalitu umělé inteligence do stávajícího formuláře epikrízy v systému Enterprise, která umožní automatické generování obsahu epikrízy na základě existujících záznamů o pacientovi.

---


**Tato funkcionalita má za cíl:**

- ✅ Významně zefektivnit práci lékařů
- ✅ Minimalizovat administrativní zátěž
- ✅ Zajistit konzistentní kvalitu epikríz v souladu s požadovanými standardy

---


## 📚 KONTEXT A SOUČASNÝ STAV

> _Epikríza představuje souhrnný záznam průběhu hospitalizace pacienta a je klíčovou součástí zdravotnické dokumentace._
> **Současný stav:**
> 📝 Epikríza se v systému Enterprise vyplňuje **manuálně**
> 🔍 Lékař musí procházet všechny relevantní záznamy o pacientovi
> ⏱️ Proces je časově náročný a náchylný k opomenutím
> 📋 Lékaři často řeší kopírováním textů z různých částí dokumentace

### Legislativní požadavky:

- 📜 Vyhláška [č. 98/2012 Sb. definuje povinné náležitosti epikrízy](https://www.zakonyprolidi.cz/cs/2024-444/zneni-20250101#p20_p20-1-1) - **§ 21**
- ⏰ Epikríza musí být vypracována po 7 dnech hospitalizace

---


## 💻 FUNKČNÍ POŽADAVKY


### Implementace do aktzuálně používaného UIX


|     Požadavek      |                        Popis                        |
| ------------------ | --------------------------------------------------- |
| **Tlačítka**       | Přidat "Generovat" a "Generovat jinak" do formuláře |
| **Umístění**       | V blízkosti textového pole pro epikrízu             |
| **Vizuální prvky** | Ikona AI/čipu, indikace procesu generování          |


### Datové zdroje a kontext


> 💡 


### Povinné náležitosti epikrízy podle vyhlášky č. 98/2012 Sb.


	**Identifikační údaje**
	Identifikace pacienta (jméno, příjmení, datum narození)
	Identifikace poskytovatele zdravotních služeb
	Oddělení, kde byla péče poskytována


	Anamnestické údaje


	Stručný souhrn anamnézy


	Diagnostická část


	Hlavní a vedlejší diagnózy
	Kód diagnózy podle MKN-10


	Průběh hospitalizace


	Shrnutí průběhu hospitalizace
	Významné změny zdravotního stavu
	Komplikace


	Provedená vyšetření a léčba


	Přehled důležitých vyšetření a jejich výsledků
	Konzilia
	Aplikovaná farmakoterapie
	Provedené výkony a zákroky


	Epikritické zhodnocení


	Celkové zhodnocení průběhu hospitalizace
	Výsledný stav při propuštění


	Doporučení


	Další léčebný plán
	Režimová opatření
	Termín kontroly
	Doporučená medikace po propuštění


	Administrativní údaje


	Datum a čas vytvoření
	Identifikace a podpis lékaře zodpovědného za zpracování epikrízy


	Časové požadavky na vytvoření epikrízy


	Při propuštění pacienta - epikríza musí být součástí propouštěcí zprávy
	Při překladu pacienta - epikríza musí být vypracována před překladem
	Při dlouhodobé hospitalizaci - průběžná epikríza musí být vypracována nejpozději po 7 dnech hospitalizace


**Zdroje dat:**

- 👤 Základní identifikační údaje pacienta
- 🩺 Diagnózy (hlavní a vedlejší)
- 📊 Dekurzy a záznamy o průběhu hospitalizace
- 🔬 Provedená vyšetření a jejich výsledky
- 📈 Laboratorní výsledky
- 💊 Medikace
- 🔧 Provedené zákroky a operace
- 📁 Další klinické události relevantní pro epikrízu

### AI funkcionalita


![image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=e29bed4797f12ac7e3efa4dbc086ec423497ac9fa46426236f370bf6da6e336d&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject](https://prod-files-secure.s3.us-west-2.amazonaws.com/f3cfa1c6-d7da-4fb2-a1aa-ee30e79030bd/3c9a7d47-53a7-4a7a-a6aa-235922553afc/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=e29bed4797f12ac7e3efa4dbc086ec423497ac9fa46426236f370bf6da6e336d&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


**Prompt pro AI:**


```text
"Shrň obsah těchto zpráv na jeden odstavec s klinickým zaměřením"

```


**Struktura výstupu:**

- 📌 Generovaný text musí respektovat požadovanou strukturu epikrízy
- 📌 Soulad se standardy

### Ošetření chybových stavů


|          Stav          |             Řešení             |
| ---------------------- | ------------------------------ |
| **Chybějící data**     | Detekce a upozornění uživatele |
| **Selhání generování** | Srozumitelné chybové hlášení   |
| **Kontrola výstupu**   | Základní validace struktury    |


---


## 🔧 TECHNICKÉ POŽADAVKY


### Integrace se systémem Enterprise

- ⚙️ Využití existujících "get" funkcí systému Enterprise
- 🔄 Mapování mezi datovými strukturami a vstupem pro AI
- 🧩 Kompatibilita s různými konfiguracemi systému

### Flow


```mermaid
graph LR
    A[Enterprise data] --> B[AI Endpoint]
    B --> C[AI Model]
    C --> D[Generovaný text]
    D --> E[Textové pole epikrízy]
```


![image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=1d173969f1d06581acf256b09e7834898324f315b6af3344b6ef5fad93e2de2c&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject](https://prod-files-secure.s3.us-west-2.amazonaws.com/f3cfa1c6-d7da-4fb2-a1aa-ee30e79030bd/3adda1bb-07e3-40f2-9950-0f54c34cdc83/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=1d173969f1d06581acf256b09e7834898324f315b6af3344b6ef5fad93e2de2c&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


**Architektura:**


![image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=5194650492832f5720cd2dcbe8d830f6a64c47de15c8eee6bd09c10dddcd796b&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject](https://prod-files-secure.s3.us-west-2.amazonaws.com/f3cfa1c6-d7da-4fb2-a1aa-ee30e79030bd/9deb7ab4-457e-4540-894d-6c4f709b7196/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=5194650492832f5720cd2dcbe8d830f6a64c47de15c8eee6bd09c10dddcd796b&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


**User flow:**


![image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=59f3e1295963166fd9c80a69e85d7880ae56aaaa8aaef403480ff089403198c5&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject](https://prod-files-secure.s3.us-west-2.amazonaws.com/f3cfa1c6-d7da-4fb2-a1aa-ee30e79030bd/7924dcbf-2213-4c71-ac86-35315660c505/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466SVTBGE4N%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235808Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIH4Dze7D4tMbflWzfAgrwQ47vWmOlYNaZOy6gAOsnUm7AiEA9mPZ2TMQcq9StN%2BCKOzXn3bnHv3bpykiDxbLGTDkoB4qiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDBnuaPlJBHA6lt9RfSrcAxVbVUsFQY4cZzk1MdjK8jwhf83dtoB7FLl799eLVi00rnK1UkBBBABX5%2FDIYdFCMVp%2BDs1sN8aJeNe36dTGxausSGcpMO0qdygE4cOSqA3u3GXf7M5R0SlC1HFnkrvl1drtuEl3ZAQceDRCNEhHYBWSoU60IXnQr2Bf4TrUlZYyctGR%2FJQSv8vIj7ngEfeXtQNnnzcAHzS2kQR2Hpl6pYkr%2BBqdlcMce%2B7xN%2F1q2OBD2I%2FMeQCixgPawGKCXWdxaPBAovx0v6xxqOErDTg%2BafSiPmTO2SmmmZZFNl4SSN4O0c6JqRHiD8WyIcCmxVZPjiX2wAQsOAANE1cun%2F3Q8nLWb7XnlX2lfUJReA5yie3W6OOaVHxE7w34gbOr%2BjuvgnbTOvZiBUFUPGd9%2BK%2BciM2qsREK%2FFl4b7EWRFDSmJ3AilVPuftny%2BDtTkUWvJaHlHAynyfNfELuen%2BuRND%2FjfJTNnfxkBO%2BjK%2Fn9spiO2DNmpoOmLA8BbTriW2dEcvzpHtZKcKsGGRdpw1sOXfRo%2Brc4Ha5f9w%2BZNkmSysv2elNfXlgysZU3EHKbew9zbZafI0R1pZk8pcNqf2nfGrzkPuGuMR6YUzb2Tw4nd7UQ12%2B0RA7%2F36Un5%2FQyigGMIP98sgGOqUBvRr8bdVlU2cM69HuZTSsg%2F3Gs22SnOG7VnYMfFy1kpukISY5D3JAMXlcJPKXYu1JZF2mmFacQRLi%2Bhy19odPGiggDqQWO%2FFwtkm9Pd4s9CbTBEZM37sE923qA4VqSVvOu3FxxE%2FOpyygei0bpT3Dvy%2FTmybv50qzUI16GqTqRRzFL6MPhdozE7i8vOw4Yaj0I8q8YxbIVOfeCDVBrlW%2BQ9vbb01x&X-Amz-Signature=59f3e1295963166fd9c80a69e85d7880ae56aaaa8aaef403480ff089403198c5&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


---

