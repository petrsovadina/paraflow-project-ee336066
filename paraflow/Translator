
# Jazykový překladače pro FONS Copilot


**Chat Prompt Template**

	- Definuje proměnnou pro volbu. jazyka: "{`output_language`}"
	- Definuje proměnnou/uživatelskou zprávu: "{text}"
	- Obsahuje mapování proměnných: `{"output_language":"{{$vars.output_language}}","text":"{{question}}"}`

## Identifikované proměnné pro předání z FONS Enterprise


|   Název proměnné    |            Popis            |             Hodnota v toku              |  Typ   |
| ------------------- | --------------------------- | --------------------------------------- | ------ |
| **text**            | Text, který má být přeložen | Mapováno na `{{question}}`              | String |
| **output_language** | Cílový jazyk překladu       | Mapováno na `{{$vars.output_language}}` | String |


---


**AI vrstva (Flowise)**

- Přijme požadavek s parametry `text` a `output_language`
- Mapuje `text` na `question` v promptu
- Mapuje `output_language` na `$vars.output_language` v promptu
- Zpracuje tok pomocí modelu
- Vrátí přeložený text zpět do Backend FE

```python
import requests

API_URL = "https://flowise.digimedic.dev/api/v1/prediction/5da0cec6-98e4-4b94-9013-361fb46f5cb2"

def query(payload):
    response = requests.post(API_URL, json=payload)
    return response.json()

output = query({
    "question": "Hey, how are you?",
    "overrideConfig": {
        "systemMessagePrompt": "example",
        "humanMessagePrompt": "example",
        "promptValues": { "key": "val" },
        "messageHistory": "example",
    }
})
```


---


## Rozšíření pro budoucí verze


	**Inteligentní translátor s regionálním zaměřením**


	Víceúrovňový překladový systém se třemi hlavními režimy:

	- **Odborný ⟷ Laický** - převod mezi odbornou terminologií a pacientsky srozumitelným jazykem
	- **Mezijazykový** - překlad mezi češtinou, slovenštinou, polštinou, němčinou a angličtinou
	- **Dokumentační** - standardizace používané terminologie v rámci dokumentace
	- **Standardizace terminologie** - sjednocení používaných termínů v rámci dokumentace

	---


	## Zdroje pro vytvoření databáze medicínských termínů


		Nejvhodnější materiály a zdroje pro vytvoření databáze medicínských termínů.


		### Standardizované medicínské terminologie a ontologie


		### SNOMED CT

		- **Zdroj:** [SNOMED CT Český portál](https://snomedct.cz/)
		- **Typ obsahu:** Komplexní medicínská terminologie obsahující cca 300 000 konceptů a 1,2 milionu anglických termínů
		- **Licenční podmínky:** Česká republika je členem IHTSDO, což umožňuje využití SNOMED CT pro české organizace
		- **Poznámka:** SNOMED CT není plně lokalizován do češtiny, ale představuje nejkomplexnější zdroj medicínské terminologie s definovanými vztahy

		### MeSH (Medical Subject Headings)

		- **Zdroj:** [MeSH český překlad (MSHCZE)](https://www.medsoft.website/sbornik/2015/Medsoft_2015_maixnerova.pdf)
		- **Typ obsahu:** Standardizovaný hierarchický slovník biomedicínských termínů, používaný primárně pro indexaci článků
		- **Přístup:** Dostupný jako součást UMLS (Unified Medical Language System)
		- **Poznámka:** MSHCZE je český překlad MeSH, který je integrován do UMLS a poskytuje kvalitní český ekvivalent anglické terminologie

		### MKN-10 (Mezinárodní klasifikace nemocí)

		- **Zdroj:** [MKN-10 klasifikace](https://mkn10.uzis.cz/) a [PDF verze od ÚZIS](https://www.uzis.cz/res/f/008458/mkn-10-tabelarni-cast-20250101.pdf)
		- **Typ obsahu:** Oficiální klasifikace nemocí, používaná pro kódování diagnóz
		- **Aktuálnost:** Obsahuje aktualizace platné k 1.1.2025
		- **Výhoda:** Plně lokalizovaná do češtiny, oficiálně používaná ve zdravotnictví ČR
		- **Poznámka:** Poskytuje standardizované názvy diagnóz, ale neobsahuje detailní vysvětlení termínů

		### Slovníky a vysvětlující zdroje medicínských termínů


		### Velký lékařský slovník On-Line

		- **Zdroj:** [Lékařské slovníky](https://www.lekarske.slovniky.cz/)
		- **Typ obsahu:** Rozsáhlý výkladový slovník lékařských termínů
		- **Výhody:** Obsahuje odborné definice, dostupný online
		- **Poznámka:** Vhodný jako zdroj odborných vysvětlení

		### Slovníček odborných pojmů (Stefajir)

		- **Zdroj:** [Stefajir.cz](https://www.stefajir.cz/slovnicek-odbornych-pojmu)
		- **Typ obsahu:** Přes 4000 medicínských termínů s vysvětlením pro laiky
		- **Výhody:** Zjednodušené a "lidsky" vysvětlené odborné termíny
		- **Poznámka:** Ideální zdroj pro mapování odborné terminologie na laickou

		### Medlicker - Slovníček odborných lékařských termínů

		- **Zdroj:** [Medlicker.com](https://cs.medlicker.com/c/slovnicek)
		- **Typ obsahu:** Slovník často používaných lékařských termínů včetně synonym
		- **Výhody:** Obsahuje způsoby použití jednotlivých hesel, moderní web
		- **Poznámka:** Dobrý zdroj pro kontextové použití termínů

		### SÚKL - Databáze léků a výkladový slovník

		- **Zdroj:** [SÚKL výkladový slovník](https://sukl.gov.cz/verejnost/leciva/vykladovy-slovnik/)
		- **Typ obsahu:** Terminologie související s léčivy
		- **Výhody:** Oficiální zdroj, standardizovaná terminologie
		- **Poznámka:** Vhodný pro rozšíření databáze o farmakologické termíny

		### Vícejazyčné zdroje pro středoevropský region


		### Multilingual Medical Corpus (MMedC)

		- **Zdroj:** Zmíněn v [článku o multilingválních medicínských LLM](https://www.electropages.com/blog/2024/11/building-multi-language-llms-medical-sector)
		- **Typ obsahu:** Korpus obsahující 25,5 miliard medicínských tokenů v šesti jazycích
		- **Poznámka:** Vhodné ověřit dostupnost pro slovenštinu, polštinu a češtinu

		### Výzkumný projekt pro západoslovanské jazyky

		- **Zdroj:** [Understanding Health Records in West Slavic Languages](https://ebooks.iospress.nl/doi/10.3233/SHTI230433)
		- **Typ obsahu:** Akademický výzkum zaměřený na zpracování zdravotnických záznamů v češtině, slovenštině a polštině
		- **Poznámka:** Může poskytovat metodologii a dílčí korpusy pro tyto jazyky
