---
title: "Generating Code for JEAF Security"
toc: false
menubar: developer_guide_menu
---

## Generating Code for JEAF Security

As described in [How to model Security Roles](/uml-modeling-guide/how-tos/how-to-model-security-roles) JEAF Generator supports to define roles and authorizations based on the UML model.

![Code for JEAF Security](/images/code_for_jeaf_security.png)

<br>

The diagram above shows the output that is generated by JEAF Generator based on Roles (stereotype `«JEAF Actor»`) and services (stereotype `«JEAFService»`). JEAF Generator will take that as input and will write a resource file named `AuthorizationData.xml` to `res-gen`. This resource file will contain a so called authorization type for every operation of every JEAF Service. For every actor so called roles will be generated. These roles will reference authorization types based on the information that are defined in the UML model. If an actor has a dependency to a whole service then this means that users with this role are allowed to call all the methods of the service. If an actor references a single operation of a service then he only has access to this operation.

<br>

The role and authorizations that are defined in the generated file can be used by [JEAF Security](https://anaptecs.atlassian.net/wiki/spaces/JEAF/pages/546210729 "https://anaptecs.atlassian.net/wiki/spaces/JEAF/pages/546210729") to ensure security at runtime.

<br>

For further information please also refer to:

- [How to model Roles / Actors](/uml-modeling-guide/how-tos/how-to-model-security-roles)

- [JEAF Security](https://anaptecs.atlassian.net/wiki/spaces/JEAF/pages/546210729 "https://anaptecs.atlassian.net/wiki/spaces/JEAF/pages/546210729")

<br>

**Source Code Example**
<details>
  <summary><code>AuthorizationData.xml</code></summary>
  <script src="https://emgithub.com/embed-v2.js?target=https%3A%2F%2Fgithub.com%2Fanaptecs%2Fjeaf-generator-samples%2Fblob%2Fmain%2Faccounting-services-impl-runtime%2Fsrc-gen%2Fmain%2Fresources%2FAuthorizationData.xml&style=base16%2Fatelier-forest-light&type=code&showBorder=on&showFileMeta=on&showFullPath=on&showCopy=on"></script>
</details>

