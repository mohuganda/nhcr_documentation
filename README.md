# National Health Client Registry 

Thank you for taking an interest in the National Health Client Registry (NHCR)! This is a ministry of health project.

> Regardless if you're just curious, an implementer, or a developer, please read the documentation for an overview at https://intrahealth.github.io/client-registry/.

> The API documentation is at https://intrahealth.github.io/opencr-api

This repository is the source code for the NHCR Service documentation, and the full NHCR stack requires ElasticSearch and HAPI FHIR Server.

## What is NHCR?

NHCR is an open source and standards-based client registry. A client registry facilitates the exchange of patient information between disparate systems. A client registry holds patient identifers and may include patient demographic information. It is a necessary tool for public health to help manage patients, monitor outcomes, and conduct case-based surveillance.

A client registry sits within a health information exchange (HIE). An HIE is used to safely and effectively exchange information. A critical component of an HIE are registries, such as those to manage a shared, canonical facility list, practitioners, and patients. 

## What does NHCR do?

NHCR offers the ability to:

* Assign and look-up unique identifiers,
* Allow connections from diverse point of service (POS) systems, such as lab systems and electronic medical record (EMR) systems, that can submit messages in FHIR,
* Configure decision rules around patient matching.

> This implementation does not allow point-of-service systems to get patient demographic information stored in the Client Registry. This is also not a Shared Health Record, nor does it contain patient clinical data.

## Use Cases

The Client Registry is one component in a more complex HIS architecture needed to accomplish important use cases, such as:

* **Deduplicating patients**: Sometimes patients have multiple diagnostic results stored within a POS. The Client Registry will link patients based on configurable decision rules so multiple test results for the same patient can be found. 

* **Tracking patients lost to clinical care**: EMRs are often not interoperable with one another, resulting in difficulty tracking patients as they move between facilities to seek care. A Client Registry will help data managers to track patients, decreasing instances of duplicate and incomplete records, patients LTFU, and sub-optimal care. 

> The Client Registry is not deduplicating or even touching patient clinical and demographic records within point-of-service systems. Instead, it provides a way to enable use cases like deduplication - which must be an external process. 

## Tests

A major round of investment in NHCR involved support of the Data Aggregation Service for Health (DASH) architecture. DASH is a reference system under development to support monitoring and reporting using patient data. The initial test automation approach focused on NHCR as it fits into the DASH architecture. For reference, see the [Test Plan for NHCR in the DASH Architecture](https://docs.google.com/document/d/1nyTKGSYGMvKz-FjEFt6gD9fxNwIuN0iEN83A8XQnK2o). 

GitHub Actions is used to run tests and feature files are in the /features folder. E2E tests require that the full application stack be stood up. Docker is used to stand up the application stack for E2E tests inside GitHub Actions. All tests and reports are open and under the Actions tab on this page. The maintainers would appreciate further contributions to testing.

## About

NHCR was developed by IntraHealth International with support from PEPFAR through the USAID MEASURE Evaluation Project. Technical direction was provided by CDC. 

