# X.500 Distinguished Names

X.500 Distinguished Names are part of the X.509 standard and are used to identify entities, such as those which are named by the _subject_ and _issuer_ fields of X.509 certificates. 



## Sub-Parts

X.500 Distinguished Names support the following sub-parts:

| Sub-part              | Property | Description                    | Example      |
| --------------------- | -------- | ------------------------------ | ------------ |
| **Common Name**       | CN       | Name of a person               | John Smith   |
| **Organization Unit** | OU       | Name of department or division | Procurement  |
| **Organization Name** | O        | Name of an organization        | ACME Limited |
| **Locality Name**     | L        | Name of a city or town         | Palo Alto    |
| **State Name**        | S        | Name of a state or province    | California   |
| **Country**           | C        | ISO 3166-2 country code        | US           |



**Example X.500 Distinguished Name**

```
CN=John Smith, OU=Procurement, O=ACME Limited, L=Palo Alto, S=California, C=US
```



## Sub-Part Ordering

X.500 Distinguished Name sub-parts **must** be ordered correctly. The order of the sub-parts is as follows:

CN, OU, O, L, S, C



## Sub-Part Omission

X.500 Distinguished Name sub-parts can be omitted, but the remaining sub-parts must remain in order:

```
OU=Procurement, O=ACME Limited, L=Palo Alto, C=US
```



## Corda X.500 Names

Not all X.500 Distinguished Name sub-parts are supported by Corda.

**Pre-UAT Environment Format**

```
O=ACME Limited, L=Palo Alto, C=US
```

**Post-UAT Environment Format**

```
OU=Procurement, O=ACME Limited, L=Palo Alto, C=US
```



### TestNet

Corda X.500 names issued for TestNet use GUID/UUID to uniquely identify organizations:

```
O=d34db33f-4afa-4854-92e7-40fe2248a959, L=Palo Alto, C=US
```

**NOTE** GUID/UUID identifiers **SHOULD NOT** be used for environments other than TestNet



### UAT

Corda X.500 names issued for UAT should represent realistic names to identify organizations and organizational units:

```
OU=Procurement, O=ACME Limited, L=Palo Alto, C=US
```

**NOTE** The `OU` sub-part should represent a division or department within the organization. The `O` sub-party should represent the legal entity in the same way that it would be registered as a company.