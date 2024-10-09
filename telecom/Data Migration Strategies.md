# Data Migration Strategies

## Table of Contents
- [Data Migration Strategies](#data-migration-strategies)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
    - [Which Data need to be Migrated?](#which-data-need-to-be-migrated)
    - [Where do Data need to be Migrated into the Ericsson Product?](#where-do-data-need-to-be-migrated-into-the-ericsson-product)
    - [Migration Strategies](#migration-strategies)
  - [Possible Problems during Migration](#possible-problems-during-migration)
  - [Data Verification after Migration](#data-verification-after-migration)

## Introduction

Many organizations have old and complex business data. Nobody wants to leave valuable data about customers, active subscriptions, catalog data, and templates in the old system and start with the empty new system, so there is a need to migrate this data. Unfortunately, data migration is not an easy task to do, a considerable percent of deployment effort is consumed by data migration activities. Therefore, data migration is a major topic for new customers. This section gives a generic overview about which data needs to be migrated, where to migrate this data, what are the migration strategies, the possible prob
lems during migration, and the data verification after the migration is completed.

### Which Data need to be Migrated?

Customers have several valuable data and they can be classified into the following categories:

- Hardgoods and catalog information that presents offers, services, prices, resources, etc.
- Generic data that presents lookup or raw data.
- Active subscriptions that represent the current install base for all customers.
- Existing customers data source that presents information about current
 customers.
- No historical data migration from the legacy system. It is recommended to leave the older system databases operational in a read-only inquiry mode
 state for users to access customer historical transactions for a temporary time rather than migrating historical transactions that will be potentially
 archived soon.

### Where do Data need to be Migrated into the Ericsson Product?

- Customer's legacy data that represents Catalog and generic data need to be migrated into Ericsson ECM.
- Active subscriptions that represent the legacy install base need to be migrated into Ericsson SR.
- If existing customers data need to be migrated, then it should be into Ericsson CPR.

### Migration Strategies

There are specific goals associated with implementing an effective data migration strategy. Primarily, data must be migrated from the source platform to the target platform completely and accurately, and according to business and regulatory policies on information controls and security. This means no dropped or incomplete records, and no data fields that fail validation or other quality controls in the target environment. Another goal of data migration is that the process needs to be done quickly.

Different migration strategies can be adopted by the project team and each of these strategies has its pros and cons. This section gives a generic view about each of these strategies in migration, the benefits and drawbacks for applying each of these strategies. Some customers can choose one of the strategies for ECM migration while using other strategy for SRmigration.

It is recommended to make migration as a separate project and have a realistic estimation. Engaging business people along with product technical people is required for such activity to guarantee the sanity and the quality of the migrated data. In addition to that, performance is one of, if not the biggest, trade-off when moving data from legacy to Ericsson product, so preparing for lengthy load is expected during this phase.

The following are the common migration strategies used by many customers:

1. Migration using DB SQL commands
    This type of migration relies mainly on creating SQL statements to read from the legacy data source and convert the data into Ericsson product. This involves SQLs for both ECM and SR. The responsible team for migration should have strong knowledge about how product tables are communicating with each other and have the knowledge about legacy data to create the correct mapping.

    - Pro: fast execution and the best option for performance. 
    - Con: not easy to implement. It requires deep knowledge in product tables schema and full understanding of legacy data.

2. Migration using REST API interfaces
    This type of migration uses ECM/SR REST API to populate the data from legacy. It requires a mapper function to generate the REST APIs. Mapper usually relies on the nature of the legacy data and the structure of the Ericsson product. The best option is to rely on the swagger file provided out-of-the-box to generate the mapping functionality. In ECM, the Management API can be used to populate the data. In SR, the SR REST API can be used for the same reason.

   - Pro: easy to implement. 
   - Con: slow and require a long execution time. However, the project team can create a customized script to support the bulk calls for POST REST API to make it fast, but this requires extra effort for such implementation.

3. Migration using Import/Export features 
    Legacy data can be populated into a format that can be understood by ECM and SR. The project team can create a customized script to migrate data from legacy into files that can be imported by both ECM and SR.

   - Pro: it is a moderate solution, easier to implement compared to the SQL approach but harder than REST APIs; faster than REST API but slower than the SQL approach.
   - Con: it requires understanding how out-of-the-box import functionality is working. Also, require configuration changes to improve the performance.

## Possible Problems during Migration

There should be a data cleansing mechanism for detecting, correcting, or removing corrupted or inaccurate data to ensure that the outcome data is consistent with the target environment. For example, having two different records with the same info coming from the same system, partial previous transformation, and external system sync issues. This mechanism target to detect, correct, or remove corrupted data by reporting the issue in source data and not by having the migration process to cleansing the data.

## Data Verification after Migration

Once migration is completed, there are several steps that need to be executed to guarantee the migration has been done successfully:

- Open out-of-the-box GUI and randomly view catalog model from ECM and subscriber details from SR.
- Use postman to randomly get ECM components and subscriber details from SR.
- Randomly create shopping carts for existing customers and verify if the installed base is loaded successfully.
- At the end, a generic report needs to be generated from ECM and SR to ensure that no data loss occurs and to provide an accurate report to the management to demonstrate the completeness of the data migration. The report should provide counters for entities like subscribers, product offering, services, then compare it with the counters from the legacy system to ensure that they match.

Here’s a structured presentation for your data migration content:

---

**Slide 1: Title Slide**
- **Title:** Data Migration Strategies
- **Subtitle:** Migrating Legacy Data to Modern Systems
- **Presented by:** [Your Name]

---

**Slide 2: Introduction**
- **Topic:** Data Migration Overview
- **Key Points:**
  - Many organizations hold valuable legacy data.
  - Migrating data like customer info, subscriptions, and catalogs is crucial.
  - Data migration is often a major effort, requiring careful planning and execution.

---

**Slide 3: What Data Needs to be Migrated?**
- **Key Data Types:**
  - Hardgoods & Catalog Information: Offers, services, prices, etc.
  - Generic Data: Lookup or raw data.
  - Active Subscriptions: Current customer install base.
  - Existing Customer Data: Info on current customers.
  - **Note:** No historical data migration. Keep old systems in read-only for historical access.

---

**Slide 4: Where Should the Data Be Migrated?**
- **Ericsson Products as Targets:**
  - Catalog & Generic Data → Ericsson ECM
  - Active Subscriptions (Install Base) → Ericsson SR
  - Existing Customer Data → Ericsson CPR

---

**Slide 5: Migration Strategies Overview**
- **Key Objectives:**
  - Data must be accurate and complete.
  - Comply with business and regulatory policies.
  - Speed and efficiency are critical.
  
- **Strategy Considerations:**
  - Each strategy has pros and cons.
  - Engage both business and technical teams to ensure data quality.
  - Performance and speed are important trade-offs during migration.

---

**Slide 6: Strategy 1 – DB SQL Commands**
- **Description:**
  - SQL queries used to extract, transform, and load data into Ericsson products.
- **Pros:**
  - Fast execution, ideal for performance.
- **Cons:**
  - Complex to implement, requires deep product schema knowledge.

---

**Slide 7: Strategy 2 – REST API Interfaces**
- **Description:**
  - Use REST APIs from ECM/SR to populate data from legacy systems.
- **Pros:**
  - Easier to implement, especially with swagger files.
- **Cons:**
  - Slower execution. Bulk API calls can improve speed but require extra effort.

---

**Slide 8: Strategy 3 – Import/Export Features**
- **Description:**
  - Data is exported from legacy systems into formats compatible with ECM/SR.
- **Pros:**
  - Moderate solution: Easier than SQL but faster than REST.
- **Cons:**
  - Requires an understanding of import functionalities and performance tuning.

---

**Slide 9: Possible Problems during Migration**
- **Challenges:**
  - Data inconsistencies: Corrupted, duplicated, or unsynchronized records.
  - Data cleansing mechanisms are necessary to ensure clean data migration.

---

**Slide 10: Data Verification after Migration**
- **Verification Steps:**
  - Open GUI to view catalog models and subscriber details.
  - Use Postman to check ECM components and subscriber details.
  - Test system by creating shopping carts for existing customers.

---

**Slide 11: Final Reporting**
- **Reporting Process:**
  - Generate a report from ECM/SR to compare against legacy system counts.
  - Include metrics on subscribers, product offerings, services, etc.
  - Ensure no data loss and provide accurate reports to management.

---

**Slide 12: Conclusion**
- **Final Thoughts:**
  - A well-planned migration ensures data integrity and system functionality.
  - Engaging business and technical teams is essential for successful migration.
  - Consider the trade-offs between speed, ease, and accuracy in each migration strategy.

---

This structure will help you present the topic clearly and in a well-organized manner.