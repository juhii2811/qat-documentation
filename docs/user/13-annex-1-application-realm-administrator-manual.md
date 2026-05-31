---
id: annex-1-application-realm-administrator-manual
title: "Annex 1: Application & Realm Administrator Manual"
sidebar_label: "Annex 1: Application & Realm Administrator Manual"
sidebar_position: 13
---

# Annex 1: Application & Realm Administrator Manual

## Introduction
This annex provides guidance on administrative functionalities restricted to **Application Administrators** and **Realm Administrators**.
- **Application Masters**: Global settings affecting all realms (App Admin only).
- **Realm Level Masters**: Data specific to a realm, affecting its programs and supply plans (App and Realm Admins).
- **Program Level Masters**: Settings managed by Program Admins for specific programs.

## Administrative Dashboards
Administrators see unique tiles on their dashboards to manage global and realm-level data.

| Tile | Admin Level | Function |
| :--- | :--- | :--- |
| **Program User** | App & Realm | Manage user roles and permissions. |
| **Total Realms** | App | Create and configure application realms. |
| **Language** | App | Manage supported UI languages. |
| **Country** | Realm | Map global countries to specific realms. |
| **Technical Area** | Realm | Define program focus areas (e.g., HIV, Malaria). |
| **Organization** | Realm | Manage partner and government entities. |
| **Total Program** | Realm | Overview and bulk update of program info. |
| **Setup Program** | Realm | Primary wizard for onboarding new programs. |

---

## Managing Master Data
QAT uses a three-tier hierarchy for data management.

## C1. Application Masters

### a. Database Translation
The database translation screen, which is accessible for application admins is used to translate "Dynamic labels" that are stored in QAT. The dynamic labels are included in drop-down lists throughout QAT as well as be labels that reference other labels (e.g. QAT Problem List problems that reference shipment IDs).

For every dynamic label, there must be at least an English translation as identified by the red asterisk next to 'English' in the below figure. The translations for the other software languages are highly recommended but not required to save a translation.

To edit a translation, double-click that cell and input the desired text. Then click the "Submit" button. The submitted translation(s) will not be changed on the front end in QAT until the next software release.

#### Global Entities (CRUD)
The following entities follow a standard **List > Add (+) > Update** workflow:
- **Country**: Manage global country list. Note: Use 3-letter (e.g., AGO) and 2-letter (e.g., AO) ISO codes.
- **Currency**: Manage conversion rates. Use "Sync Online" to automatically update rates against the USD.
- **Language**: Enable/Disable UI languages (English, French, Spanish, Portuguese).
- **Dimension & Unit**: Define measurable values (Weight, Volume) and units (mL, gm, Box).
- **Usage Period**: Define time intervals (Month, Week) used in forecasting calculations.

#### User Management & Roles
- **Users**: Add new users via email, assigning them a primary Role, Realm, and Language.
- **Roles**: Administrators can modify business rules associated with roles. 
  > [!NOTE]
  > For a full permission breakdown, see [Annex 3: User Role Matrix](15-annex-3-user-role-matrix.md).

---

### 2. Realm Masters (Business Logic)
Realm settings govern the specific products, funders, and procurement logic for a group of programs.

#### Product Catalog
The product hierarchy is central to QAT operations:
1. **Forecasting Unit (FU)**: The base unit (e.g., 1 Tablet).
2. **Planning Unit (PU)**: The dispensing pack (e.g., Bottle of 30 tabs). 
   - *Mapping:* Many PUs can map to one FU.
   - *Volumetrics:* Administrators must map volume/weight data to PUs for shipping calculations.
3. **Procurement Unit**: Item-level description including manufacturer-specific data (GTIN, SKU) and lead times.
4. **Planning Unit Category**: Broad groupings (e.g., "ARV Pharmaceuticals").
5. **Tracer Category**: Specific clusters (e.g., "Adult First Line").

#### Equivalency Units (EU)
EUs allow disparate products to be aggregated for reporting (e.g., converting bottles and tubes into "Standard Treatment Months").
- **Logic:** Realm-level mappings apply to all programs unless overridden by a program-specific mapping.

#### Logistics & Partners
- **Procurement Agents**: Manage lead times, color codes, and catalog integration.
- **Funding Sources**: Define the entities paying for shipments.
- **Organizations**: Manage the specific bodies (MOH, NGO) running programs.
- **Forecast Methods**: Define the available methodologies (ARIMA, TES, etc.) for the realm.

---

## Setting Up a New Program
Administrators initiate programs via the **Setup Program** wizard.

### Workflow:
1. **Choose Realm & Country**: Assign the program to its clinical/geographic context.
2. **Define Technical Area**: Select one or more areas (e.g., HIV + TB).
3. **Select Organization & Regions**: Determine the managing body and geographic scope (National or sub-national).
4. **Configure Program Data**:
   - **For Supply Planning**: Set Lead Times, Stock levels, and Planning Units.
   - **For Forecasting**: Set Forecast Start/End dates and review periods.
5. **Submit**: The program is now available for Program Admins to manage.

---

## Utility Tools
### Resetting the QPL
Administrators can bulk-reset the **QAT Problem List (QPL)** to reopen "Addressed" issues for a new review cycle.
- **Usage:** Typically done at the start of a new submission period for approved versions.
