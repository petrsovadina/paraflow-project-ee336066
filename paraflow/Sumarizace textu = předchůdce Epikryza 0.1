
# **"Sumarizace" předchůdce plnohodnotné Epikryzy**


> 💡 


## Datové zdroje


Pro tuto verzi budeme pracovat s následujícími datovými zdroji:

- **Lékařské zprávy** - textové záznamy z aktuální epizody péče (anamnéza, průběh hospitalizace)
- **Laboratorní výsledky** - klíčové laboratorní hodnoty pacienta s důrazem na patologické nálezy
- **Medikace** - seznam aktuálně předepsaných léků a jejich dávkování

---


```mermaid
flowchart TD
    %% Uživatelský vstup a akce
    User["Uživatel FONS Enterprise"] -->|"1. Výběr pacienta + časové období"| UI["Modální okno FONS Copilot"]
    UI -->|"2. Požadavek na Epikryzu 0.1"| API["REST API Controller"]
    
    %% Získávání dat z FONS Enterprise
    API -->|"3. Požadavek na data pacienta"| DataServicesLayer["Data Services Layer"]
    
    %% Datové zdroje
    subgraph "FONS Enterprise Datové zdroje"
        MedicalReports[("Lékařské zprávy
        Anamnéza
        Zprávy z vyšetření
        Průběh hospitalizace")]
        LabResults[("Laboratorní výsledky
        Biochemie
        Hematologie
        Mikrobiologie")]
        Medications[("Medikace
        Aktuální předpisy
        Historie medikace")]
    end
    
    %% Získání dat z jednotlivých zdrojů
    DataServicesLayer -->|"4a. Načtení zpráv"| MedicalReports
    DataServicesLayer -->|"4b. Načtení výsledků"| LabResults
    DataServicesLayer -->|"4c. Načtení medikace"| Medications
    
    %% Zpracování dat
    MedicalReports -->|"5a. Textové zprávy"| DataProcessor["Data Processor"]
    LabResults -->|"5b. Strukturované výsledky"| DataProcessor
    Medications -->|"5c. Seznam léků"| DataProcessor
    
    %% Sestavení datového balíčku pro AI
    DataProcessor -->|"6. Strukturovaná data pacienta"| AIPreparation["AI Request Preparation"]
    
    %% Příprava dat pro AI tok
    AIPreparation -->|"7. Strukturovaný vstup pro AI"| AIFlow["AI Flow (Flowise)"]
    
    %% AI zpracování
    subgraph "AI tok v Flowise"
        InputProcessing["Vstupní data
        Strukturování a validace"]
        ContextCreation["Vytvoření kontextu
        Sestavení komplexního kontextu"]
        PromptGeneration["Generování promptu
        Systémová + uživatelská zpráva"]
        LLMProcessing["LLM zpracování
        GPT-4o-mini"]
        OutputFormatting["Formátování výstupu
        Strukturace a validace"]
    end
    
    %% Propojení AI toku
    AIFlow --> InputProcessing
    InputProcessing --> ContextCreation
    ContextCreation --> PromptGeneration
    PromptGeneration --> LLMProcessing
    LLMProcessing --> OutputFormatting
    
    %% Zpracování odpovědi
    OutputFormatting -->|"8. Strukturovaná epikryza"| ResultHandler["Result Handler"]
    
    %% Odpověď uživateli
    ResultHandler -->|"9. Formátovaný výsledek"| UIResult["UI - Zobrazení výsledku"]
    UIResult -->|"10. Strukturovaná epikryza"| UserReview["Uživatelská kontrola a export"]
    
    %% Možné další akce
    UserReview -->|"11a. Export do dokumentace"| DocumentStorage["Uložení do FONS"]
    UserReview -->|"11b. Tisk"| Print["Tisk dokumentu"]
    UserReview -->|"11c. Kopírování"| Clipboard["Kopírování do schránky"]
    
    %% Datové entity pro každý zdroj
    subgraph "Datové entity - Lékařské zprávy"
        ReportEntity["Lékařská zpráva {
            id: string,
            patientId: string,
            date: datetime,
            author: string,
            type: string,
            content: string,
            department: string
        }"]
    end
    
    subgraph "Datové entity - Laboratorní výsledky"
        LabEntity["Laboratorní výsledek {
            id: string,
            patientId: string,
            date: datetime,
            testName: string,
            value: string/number,
            unit: string,
            referenceRange: string,
            isAbnormal: boolean,
            lab: string
        }"]
    end
    
    subgraph "Datové entity - Medikace"
        MedEntity["Medikace {
            id: string,
            patientId: string,
            drugName: string,
            atcCode: string,
            dosage: string,
            frequency: string,
            route: string,
            startDate: datetime,
            endDate: datetime,
            prescribedBy: string,
            notes: string
        }"]
    end
    
    %% Propojení datových entit s datovými zdroji
    MedicalReports --- ReportEntity
    LabResults --- LabEntity
    Medications --- MedEntity
    
    %% Struktura výstupu
    subgraph "Struktura výstupu Epikryzy 0.1"
        OutputStructure["Strukturovaná epikryza {
            patientOverview: {
                diagnoses: Array<Diagnosis>,
                clinicalContext: string
            },
            clinicalFindings: Array<Finding>,
            laboratoryResults: Array<LabResult>,
            medications: Array<Medication>,
            recommendations: Array<string>,
            metadata: {
                sources: Object,
                generationTime: datetime
            }
        }"]
    end
    
    %% Propojení výstupu s UI
    OutputFormatting --- OutputStructure
    
    %% Styl
    classDef input fill:#4285F4,stroke:#333,stroke-width:1px,color:white;
    classDef process fill:#34A853,stroke:#333,stroke-width:1px,color:white;
    classDef datasource fill:#FBBC05,stroke:#333,stroke-width:1px,color:black;
    classDef aiprocess fill:#EA4335,stroke:#333,stroke-width:1px,color:white;
    classDef output fill:#8E44AD,stroke:#333,stroke-width:1px,color:white;
    classDef entity fill:#eeeeee,stroke:#333,stroke-width:1px,color:black;
    
    class User,UI input;
    class API,DataServicesLayer,DataProcessor,AIPreparation,ResultHandler process;
    class MedicalReports,LabResults,Medications datasource;
    class AIFlow,InputProcessing,ContextCreation,PromptGeneration,LLMProcessing,OutputFormatting aiprocess;
    class UIResult,UserReview,DocumentStorage,Print,Clipboard output;
    class ReportEntity,LabEntity,MedEntity,OutputStructure entity;
```


---


![Capture-2025-03-28-030254.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663B6CNBBG%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235923Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIDJ%2Ff%2B3G%2FbW%2FBuxxvTDTKu%2BafUDHeIBH7j1LvvEW3fnIAiEAqGmJ6S85bNFCX8pyKOOJin6qXfj8Y%2B3v14Juj0IKAGcqiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDFeBdbA%2FPWF%2Fb3nEgircAzPbmuiEXknNb2YFY2MLomqJ5QYZOH4kNPq%2FHGwK4poBpRCMPkygoDQGliNGnPkCAqwrmqZ%2BMYB1xJvRuFpLWZOEt3rcTF75VuNhk8Vxpl6losbRZBgF8ethtKIuNHrEkDw6O5Hb49LPRgZEaxac0IQD95S7QqfLJ%2B%2BUlIDYobjtRec2YVGB2IdQgpyaCjYu5rZ7dPzCvZ5uuid7%2FZl41CBt8HKA9bG3njf%2BGbQt%2BJQkiZKA%2FEDvvoHGO5lydysMrEgKQF7A0Zl1ExXArlYPF%2B7gcSaH1vdIJIUmNO6oTnFH%2F5xqWDXopmlelZcbCBxsy67Cgo7YLFwxedCIAKlanOo8XLf8KcV2BQcCQ4K15UXglmp9D818J%2BQQZS7GVq5RdewC9uVrdY%2BQazdpMxZdeo3FcNO%2Bt2udt0kJjKSvuIt4i1KNT3qBTkwXmUn6rbPB851Cev4X1Tvt0pUeU9YwgpuDzhx3HDw0rTUVQdmLylYZU7wM4wyL1A5JF0zlH8bvlHr%2FOgXO%2FjcS8Ec2Vfkr1aQaeFyp5VRMYeS3VbBj7TasqD51WHk%2Fq%2FoexcaD8o%2BXhkLBQgJXsJP6%2BeLK%2BmziaRd8jW1gtQ3DZsZnJK%2FnPT4BgNoHBNmw3g1GhrWOMO388sgGOqUBgGQt8vJCouJ%2Bvt3Dsr4GGEE0zsdxxwrVdDhcizb34Lk4FJdU4Ta7VghcQWDPqI%2BUgikd9vobAR12ndUKz4XkeVfmYXkdtvmLD79W8shw%2BoGV9GhlRMiBu5IGwOsBRACv%2BeOavKIILW0lYFiDF4zqUpaq6U8b6uwe6EqwNWGmmM0g7F0tQHGTYxdv9IwPbvGssiNRGGmU96dh4abZfFUEZ1WN1GGd&X-Amz-Signature=a3fd1116bdbf74d95a76e3ebc71b548d58ea57da944880940c6737b2b0337bfe&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject](https://prod-files-secure.s3.us-west-2.amazonaws.com/f3cfa1c6-d7da-4fb2-a1aa-ee30e79030bd/10cbf2c5-3857-4fa9-bfb5-e42e2cc50184/Capture-2025-03-28-030254.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4663B6CNBBG%2F20251118%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20251118T235923Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEAMaCXVzLXdlc3QtMiJHMEUCIDJ%2Ff%2B3G%2FbW%2FBuxxvTDTKu%2BafUDHeIBH7j1LvvEW3fnIAiEAqGmJ6S85bNFCX8pyKOOJin6qXfj8Y%2B3v14Juj0IKAGcqiAQIzP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw2Mzc0MjMxODM4MDUiDFeBdbA%2FPWF%2Fb3nEgircAzPbmuiEXknNb2YFY2MLomqJ5QYZOH4kNPq%2FHGwK4poBpRCMPkygoDQGliNGnPkCAqwrmqZ%2BMYB1xJvRuFpLWZOEt3rcTF75VuNhk8Vxpl6losbRZBgF8ethtKIuNHrEkDw6O5Hb49LPRgZEaxac0IQD95S7QqfLJ%2B%2BUlIDYobjtRec2YVGB2IdQgpyaCjYu5rZ7dPzCvZ5uuid7%2FZl41CBt8HKA9bG3njf%2BGbQt%2BJQkiZKA%2FEDvvoHGO5lydysMrEgKQF7A0Zl1ExXArlYPF%2B7gcSaH1vdIJIUmNO6oTnFH%2F5xqWDXopmlelZcbCBxsy67Cgo7YLFwxedCIAKlanOo8XLf8KcV2BQcCQ4K15UXglmp9D818J%2BQQZS7GVq5RdewC9uVrdY%2BQazdpMxZdeo3FcNO%2Bt2udt0kJjKSvuIt4i1KNT3qBTkwXmUn6rbPB851Cev4X1Tvt0pUeU9YwgpuDzhx3HDw0rTUVQdmLylYZU7wM4wyL1A5JF0zlH8bvlHr%2FOgXO%2FjcS8Ec2Vfkr1aQaeFyp5VRMYeS3VbBj7TasqD51WHk%2Fq%2FoexcaD8o%2BXhkLBQgJXsJP6%2BeLK%2BmziaRd8jW1gtQ3DZsZnJK%2FnPT4BgNoHBNmw3g1GhrWOMO388sgGOqUBgGQt8vJCouJ%2Bvt3Dsr4GGEE0zsdxxwrVdDhcizb34Lk4FJdU4Ta7VghcQWDPqI%2BUgikd9vobAR12ndUKz4XkeVfmYXkdtvmLD79W8shw%2BoGV9GhlRMiBu5IGwOsBRACv%2BeOavKIILW0lYFiDF4zqUpaq6U8b6uwe6EqwNWGmmM0g7F0tQHGTYxdv9IwPbvGssiNRGGmU96dh4abZfFUEZ1WN1GGd&X-Amz-Signature=a3fd1116bdbf74d95a76e3ebc71b548d58ea57da944880940c6737b2b0337bfe&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


---


# Standardizace a specifikace Epikrizy 0.1


## Analyza standardizace epikrízy


	### Legislativní a standardizační rámec v ČR

	- **Vyhláška č. 98/2012 Sb. o zdravotnické dokumentaci**
		- Definuje, že epikríza je "souhrnný údaj o způsobu řešení akutního stavu"
		- Stanovuje náležitosti propouštěcí zprávy, která často obsahuje epikrízu

	**Požadavky na propouštěcí zprávu dle vyhlášky:**


	_Na základě standardu NCEZ a obecné praxe by propouštěcí zpráva/epikríza měla obsahovat:_

	- _Identifikace pacienta a administrativa_
	- _Diagnózy (hlavní a vedlejší)_
	- _Anamnéza_
	- _Průběh hospitalizace_
	- _Provedená vyšetření a jejich výsledky_
	- _Prováděná léčba a její výsledky_
	- _Stav při propuštění_
	- _Doporučení pro další péči_
	- _Medikace při propuštění_

	### Mezinárodní standardy

	- **HL7 CDA (Clinical Document Architecture)**
		- Definuje strukturu klinických dokumentů včetně propouštěcích zpráv
		- Zajišťuje interoperabilitu mezi zdravotnickými systémy
	- **FHIR (Fast Healthcare Interoperability Resources)**
		- Novější standard pro výměnu zdravotnických informací
		- Definuje způsob strukturování a předávání zdravotnických dat
	- **WHO doporučení**
		- Celosvětové standardy pro strukturu zdravotnické dokumentace

## Specifikace proměnných a konfigurace pro Epikryza 0.1


_S ohledem na identifikované standardy a požadavky specifikuji následující proměnné a konfigurační parametry pro funkci Epikryza 0.1._


### Vstupní proměnné


### Základní identifikační proměnné


|    Název proměnné     |                 Popis                 |   Typ    | Povinná | Výchozí hodnota |
| --------------------- | ------------------------------------- | -------- | ------- | --------------- |
| `patientId`           | Identifikátor pacienta v systému FONS | String   | Ano     | -               |
| `userId`              | ID uživatele, který požaduje epikrízu | String   | Ano     | -               |
| `timeRange`           | Časové období pro epikrízu            | Object   | Ano     | -               |
| `timeRange.startDate` | Počáteční datum období                | DateTime | Ano     | -               |
| `timeRange.endDate`   | Koncové datum období                  | DateTime | Ano     | Aktuální datum  |


### Proměnné pro konfiguraci datových zdrojů


|     Název proměnné      |                 Popis                  |   Typ   | Povinná |                Výchozí hodnota                 |
| ----------------------- | -------------------------------------- | ------- | ------- | ---------------------------------------------- |
| `includeMedicalReports` | Zahrnout lékařské zprávy               | Boolean | Ne      | True                                           |
| `includeLabResults`     | Zahrnout laboratorní výsledky          | Boolean | Ne      | True                                           |
| `includeMedications`    | Zahrnout medikace                      | Boolean | Ne      | True                                           |
| `medicalReportTypes`    | Typy lékařských zpráv k zahrnutí       | Array   | Ne      | ["admission", "progress", "discharge"]         |
| `labResultTypes`        | Typy laboratorních výsledků k zahrnutí | Array   | Ne      | ["biochemistry", "hematology", "microbiology"] |
| `medicationTypes`       | Typy medikací k zahrnutí               | Array   | Ne      | ["current", "discharge"]                       |


### Proměnné pro konfiguraci výstupu


|   Název proměnné    |                 Popis                 |   Typ   | Povinná | Výchozí hodnota |
| ------------------- | ------------------------------------- | ------- | ------- | --------------- |
| `detailLevel`       | Úroveň detailu výstupu (1-5)          | Number  | Ne      |               3 |
| `outputFormat`      | Formát výstupu                        | String  | Ne      | structured      |
| `highlightAbnormal` | Zvýraznit abnormální hodnoty          | Boolean | Ne      | True            |
| `includeTrends`     | Zahrnout trendy v datech              | Boolean | Ne      | True            |
| `language`          | Jazyk výstupu                         | String  | Ne      | cs              |
| `specialtyContext`  | Odborný kontext pro zaměření epikrízy | String  | Ne      | general         |


### Struktura výstupu

<details><summary>_V souladu s vyhláškou 98/2012 Sb. a mezinárodními standardy HL7 CDA/FHIR bude výstup strukturován následovně:_</summary>
```json
{
  "summary": {
    "metadata": {
      "patientId": "String",
      "timeRange": {
        "startDate": "DateTime",
        "endDate": "DateTime"
      },
      "generatedAt": "DateTime",
      "generatedBy": "String",
      "version": "String"
    },
    "patientOverview": {
      "basicInfo": {
        "name": "String",
        "birthDate": "Date",
        "gender": "String",
        "insurance": "String"
      },
      "diagnoses": [
        {
          "code": "String",
          "name": "String",
          "status": "String",
          "dateIdentified": "Date",
          "type": "String"
        }
      ],
      "clinicalContext": "String"
    },
    "medicalHistory": {
      "admissionReason": "String",
      "relevantPastHistory": "String",
      "allergies": [
        {
          "allergen": "String",
          "reaction": "String",
          "severity": "String"
        }
      ],
      "hospitalCourse": "String"
    },
    "clinicalFindings": [
      {
        "date": "DateTime",
        "finding": "String",
        "source": "String",
        "significance": "String"
      }
    ],
    "laboratoryResults": [
      {
        "category": "String",
        "name": "String",
        "value": "String",
        "unit": "String",
        "referenceRange": "String",
        "date": "DateTime",
        "status": "String",
        "trend": "String"
      }
    ],
    "medications": [
      {
        "name": "String",
        "atcCode": "String",
        "dosage": "String",
        "frequency": "String",
        "route": "String",
        "startDate": "DateTime",
        "endDate": "DateTime",
        "indication": "String",
        "notes": "String"
      }
    ],
    "procedures": [
      {
        "name": "String",
        "date": "DateTime",
        "result": "String",
        "performer": "String"
      }
    ],
    "recommendations": {
      "followUp": {
        "appointmentDate": "DateTime",
        "specialty": "String",
        "instructions": "String"
      },
      "medications": [
        {
          "name": "String",
          "dosage": "String",
          "frequency": "String",
          "duration": "String",
          "special": "String"
        }
      ],
      "lifestyleChanges": "String",
      "warningSignsToWatch": "String",
      "additionalInstructions": "String"
    }
  },
  "sources": {
    "medicalReports": {
      "count": "Number",
      "list": [
        {
          "id": "String",
          "type": "String",
          "date": "DateTime"
        }
      ]
    },
    "labResults": {
      "count": "Number",
      "categories": ["String"]
    },
    "medications": {
      "count": "Number"
    }
  }
}

```

</details>
### Konfigurační proměnné AI toku


### Systémová zpráva pro LLM


```text
Jsi zkušený lékař, specialista na vytváření komplexních souhrnu zdravotnické dokumentace (epikríz). Tvým úkolem je vytvořit strukturovanou epikrízu na základě poskytnutých informací z různých zdrojů zdravotnické dokumentace. Epikríza musí být v souladu s vyhláškou č. 98/2012 Sb. o zdravotnické dokumentaci a mezinárodními standardy HL7 CDA/FHIR.

Zaměř se na:
1. Přesnost a klinickou relevanci všech informací
2. Strukturování do jasně oddělených sekcí
3. Zdůraznění hlavních diagnóz a abnormálních nálezů
4. Logické propojení informací z různých zdrojů
5. Vyjádření trendů ve zdravotním stavu pacienta
6. Formulaci jasných doporučení pro následnou péči

Generuj pouze faktické informace podložené poskytnutými daty. Pokud nějaká důležitá informace chybí, zmíň to.

```


### Uživatelská zpráva pro LLM (šablona)


```text
Vytvoř strukturovanou epikrízu pro pacienta na základě následujících zdrojových dat:

LÉKAŘSKÉ ZPRÁVY:
{{medical_reports}}

LABORATORNÍ VÝSLEDKY:
{{lab_results}}

MEDIKACE:
{{medications}}

Úroveň detailu: {{detail_level}} (1-5, kde 5 je nejvyšší detail)
Specializace: {{specialty_context}}
Časové období: {{time_range_start}} až {{time_range_end}}

Výstup strukturuj podle následujícího formátu JSON:
{jsonSchema}

Zajisti, aby všechny relevantní informace z poskytnutých zdrojů byly zahrnuty a správně kategorizovány. Zvláštní pozornost věnuj abnormálním hodnotám a trendům ve zdravotním stavu pacienta.

```


### Datové mapování z FONS Enterprise


### Lékařské zprávy


```typescript
interface MedicalReport {
  id: string;
  patientId: string;
  date: Date;
  author: string;
  authorId: string;
  department: string;
  reportType: string;  // "admission", "progress", "discharge", "consultation"
  title: string;
  content: string;
  diagnoses: Array<{
    code: string;
    name: string;
    type: string;  // "primary", "secondary", "complication"
  }>;
  attachments?: Array<{
    id: string;
    type: string;
    name: string;
  }>;
}

```


### Laboratorní výsledky


```typescript
interface LabResult {
  id: string;
  patientId: string;
  sampleDate: Date;
  resultDate: Date;
  category: string;  // "biochemistry", "hematology", "microbiology"
  testName: string;
  value: string | number;
  unit: string;
  referenceRangeLow?: number;
  referenceRangeHigh?: number;
  isAbnormal: boolean;
  abnormalityDirection?: string;  // "high", "low", "normal"
  labName: string;
  notes?: string;
}

```


### Medikace


```typescript
interface Medication {
  id: string;
  patientId: string;
  drugName: string;
  atcCode?: string;
  dosage: string;
  frequency: string;
  route: string;
  startDate: Date;
  endDate?: Date;
  isActive: boolean;
  prescribedBy: string;
  prescribedById: string;
  indication?: string;
  notes?: string;
  isMandatory: boolean;
}

```


### Rozšiřitelnost pro budoucí verze


_Možnosti budoucího rozšíření na plnohodnotnou Epikryzu 1.0 jsou následující:_

- **Modulární datové providery** - možnost přidávat další poskytovatele dat a datové zdroje (např. zobrazovací metody, konzultace)
- **Konfigurovatelné šablony** - systém šablon pro různé specializace

---

