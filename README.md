# icao_9303_summary

reference to 9303 p10: https://www.icao.int/publications/documents/9303_p10_cons_en.pdf

1.1)Which data fields have data on chip

4.7.1 DATA GROUP 1 — Machine Readable Zone Information (MANDATORY) - Contains the machine readable zone (MRZ) data, which reflects the information printed on the MRZ of the passport.

4.7.2 DATA GROUP 2 — Encoded Identification Features — Face (MANDATORY) - Contains one or more facial image(s) of the passport holder, encoded in a biometric template format.

4.7.3 DATA GROUP 3 — Additional Identification Feature — Finger(s) (OPTIONAL) - Optionally can contain one or more fingerprint image(s) of the holder.

4.7.4 DATA GROUP 4 — Additional Identification Feature — Iris(es) (OPTIONAL) - Optionally can contain one or more iris image(s) of the holder.

4.7.5 DATA GROUP 5 — Displayed Portrait (OPTIONAL) - Optionally can contain one or more displayed portrait(s)/photo(s) of the passport holder. These would be JPEG images of the photo page of the passport.

4.7.6 DATA GROUP 6 — Reserved for Future Use - This data group is currently reserved for future use.

4.7.7 DATA GROUP 7 — Displayed Signature or Usual Mark (OPTIONAL) - Optionally can contain one or more displayed signature(s) or usual mark(s) of the passport holder. These would typically be JPEG images of the signature from the signature page of the passport.

4.7.8 DATA GROUP 8 — Data Feature(s) (OPTIONAL) - This Data Group has yet to be defined. The document states that until it is defined, DG8 is available for temporary proprietary usage by issuing countries/organizations.
-The document notes that DG8 could use a structure similar to that used for biometric templates, machine-assisted security feature verification and encoded details. But since it is not yet formally defined, countries can use it flexibly for proprietary purposes on a temporary basis.

4.7.9 DATA GROUP 9 — Structure Feature(s) (OPTIONAL)- Reserved for future use.

4.7.10 DATA GROUP 10 — Substance Feature(s) (OPTIONAL) - Reserved for future use.

4.7.11 DATA GROUP 11 — Additional Personal Detail(s) (OPTIONAL) - Contains additional personal details of the holder.

4.7.12 DATA GROUP 12 — Additional Document Detail(s) (OPTIONAL) - Contains additional document details.

4.7.13 DATA GROUP 13 — Optional Details(s) (OPTIONAL)
4.7.14 DATA GROUP 14 — Security Options (CONDITIONAL)
4.7.15 DATA GROUP 15 — Active Authentication Public Key Info (CONDITIONAL)
4.7.16 DATA GROUP 16 — Person(s) to Notify (OPTIONAL)
Data Groups 13-16 (DG13-DG16):

These data groups provide space for issuing countries/organizations to add optional/proprietary data
The specifics of any data stored in these groups is left up to the discretion of the individual issuer and is outside the scope of the ICAO standard
Issuers can define their own data elements, templates, formats, etc. to include additional information as they see fit within these groups
More than one recording of data added by a receiving state/organization can be included in these groups
The ability for a receiving state to add data after issuance is not supported, these groups are only intended for issuer use

The Document Security Object (EF.SOD):

Is located in the LDS1 eMRTD application
Contains hash values of the data groups to validate integrity of data created/stored by the issuer
Each data group is represented in the EF.SOD
The EF.SOD is digitally signed by the issuing state/organization
It contains the hash algorithms and hash values of each data group
For LDS v1.7 it does not include LDS/Unicode version info, but v1.8 does
It allows validation of integrity of data created by the issuer and stored in the LDS1 application


### Summary
Electronic passports (ePassports) contain an embedded contactless integrated circuit (chip) that stores passport holder data in a standardized logical format defined by ICAO.

The data is organized into "Data Groups" that can contain things like photos, fingerprints, personal details, travel records, etc.

The standard defines 16 possible Data Groups, but not all may be used by every passport issuing country.

Biometrics like photos and fingerprints are stored in encoded template formats like JPEG for photos and ISO fingerprint standards.

Travel records of entry/exit stamps can be digitally stored.

Issuing countries can optionally add proprietary extra data in Data Groups 13-16.

Data integrity is ensured through cryptographic hashes of each Data Group stored in the Document Security Object (EF.SOD).

Multiple applications can be supported like travel records, visas, additional biometrics.

1.2) What is nature of data stored on chip?

The data stored on the contactless chip in an electronic passport/travel document (ePassport/eMRTD) is defined by the Logical Data Structure (LDS) specification. The key points about the nature of this data are:

It is primarily biographic and biometric identity data about the passport holder. This includes things like name, date of birth, nationality, photos, fingerprints etc.

It also includes some document data like passport number, issuing country, expiration date etc.

Optional data like additional personal details, displayed images, travel records can also be included.

The data has a standardized logical structure divided into Data Groups for global interoperability.

Biometrics and images are encoded in standardized biometric template formats.

The data is digitally signed by the issuing authority to ensure integrity.

It is static/non-modifiable after issuance to prevent tampering.

The intent is to allow machine-assisted identity verification of the holder.

It also facilitates automated border/migration processes using the stored identity/travel data.

The nature of data is identity-related biographic and biometric information about the holder, following set logical structures and encoding formats defined in international standards. Its purpose is to enable global electronic verification of travel documents.

Files, records and templates follow defined structures to enable global interoperability.

As a mobile dev, I'd focus on the key biometric and travel record Data Groups, their encoding formats, and authentication methods using the Document Security Object.


1.3) What is nature of data stored on each data filed?


The data stored in each specific data field/data group on the ePassport chip has the following nature:

Data Group 1 (DG1): Contains the machine readable zone (MRZ) data in the same format as printed on the passport.

Data Group 2 (DG2): Contains facial image(s) of the holder encoded as biometric template(s) following ISO photo standards.

Data Group 3 (DG3): Optionally contains fingerprint image(s) of the holder encoded as biometric template(s) following ISO fingerprint standards.

Data Group 4 (DG4): Optionally contains iris image(s) of the holder encoded as biometric template(s) following ISO iris standards.

Data Groups 5-7 (DG5-DG7): Optionally contain displayed image(s) like photo, signature encoded in JPEG/image format.

Data Group 8 (DG8): Reserved for future use/proprietary data defined by issuer.

Data Groups 9-12 (DG9-DG12): Contain additional identity details like personal details, document details, etc.

Data Groups 13-16 (DG13-DG16): Reserved for optional/proprietary data defined by issuing country.

EF.SOD: Contains cryptographic hashes of each data group to validate data integrity.

So in summary, the nature of data is identity-related biographic information, biometric images/templates, displayed images, and travel records - all organized into standardized data structures and encoding formats.
