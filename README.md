# ig-registry

Registry of published implementation guides. 

This registry is published for human convenience at https://registry.fhir.org/guides

Other registries:

* http://registry.fhir.org: a registry of conformance resources, including ones contained in IGs registered here

# Editing the registry 

If you want to register a new implementation guide, or a new edition of an existing guide, edit fhir-ig-list.json and then make your changes into a pull request. Note that you must make sure that the JSON file is valid, or your changes will be rejected by the build process. JSON validity is checked by python script in the CI/CD, hosted on [Azure Pipelines](https://dev.azure.com/fhir-pipelines/ig-registry). 

Alternatively, you can email your changes to fhir-director@hl7.org

# Documentation of Registry

Each implementation guide gets an entry in the registry. Implementation guides do not need to be 
published by HL7  - any one can register a published implementation guide - just make a pull request.

Entries for each implementation guide:

* name (required) : human name for the implenentation guide
* npm-name (optional) : the npm-name for all versions of this IG, if they are all the same (e.g. "hl7.fhir.us.core")
* category (required) : arbitrary category for sorting/filtering - check existing ones
* description (required) : a human readable description of the IG contents
* authority (required) : Who is responsible for publishing the IG. All IGs published by HL7 or affiliates are "HL7"
* country (required) :ISO 2 letter code, or "UV" for international
* history : URL to see a list of all published versions of the IG
* ci-build : URL to see the CI build of the IG (just the base URL - do not include the index.html etc)
* editions : optional array containing at least 1 published edition information:
  * name (required) : Human name for published edition
  * ig-version (required) : the stated version of the IG itself
  * fhir-version (required) : array for the the version of the FHIR spec that the IG is based on e.g. ["4.0.0"]
  * package (required) : the npm-name and version for the IG e.g. hl7.fhir.us.core#3.0.1
  * url (required) : where the edition is found (just the base URL - do not include the index.html etc)

Typically, only milestone releases are published, and for a given ballot sequence, only the last of the sequence - the most recent - will be listed.
