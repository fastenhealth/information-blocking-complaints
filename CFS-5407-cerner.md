I am the President of Fasten Health, Inc. a Personal Health Record (PHR) application that allows patients to create a longitudinal health record using Patient Access APIs.

I’m submitting an Information Blocking Complaint against:

**Name:** Cerner  
**Website:** [https://www.oracle.com/health/](https://www.oracle.com/health/)
**Role:** Certified Health IT  
**CHPL Link:** [https://chpl.healthit.gov/#/listing/11015](https://chpl.healthit.gov/#/listing/11015)

We determined that some Health Systems using Cerner's Millennium EHR are broken in a similar way: requesting PDF Binary FHIR resources will consistently result in 404 or 500 error messages (while XML Binary documents return correctly)

After filing an issue on the Oracle Cerner support forums, we were told that "Cerner’s Clinical Reporting (XR) solution" must be purchased & correctly installed by health systems.

Please see the following support forum thread for our discussion: https://forums.oracle.com/ords/apexds/post/binary-document-404-error-0893

This is contrary to their documentation for the [Binary resource](https://docs.oracle.com/en/industries/health/millennium-platform-apis/mfrap/binary.html) which implies that the Clinical Reporting (XR) product is only required if requesting with an Accept header other than `application/fhir+json`

