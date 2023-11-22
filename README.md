# icao_9303_summary
reference to 9303 p10:https://www.icao.int/publications/documents/9303_p10_cons_en.pdf

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
