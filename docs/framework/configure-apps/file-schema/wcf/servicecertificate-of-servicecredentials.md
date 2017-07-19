---
title: "Elemento &lt;serviceCertificate&gt; de &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Elemento &lt;serviceCertificate&gt; de &lt;serviceCredentials&gt;
Especifique un certificado X.509 que se vaya a utilizar para autenticar el servicio a los clientes utilizando el modo de seguridad de mensajes.  
  
## Sintaxis  
  
```  
  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.  El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado.  El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor.  Los valores válidos son los siguientes:<br /><br /> -   LocalMachine: el almacén de certificados asignado al equipo local.<br />-   CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a abrir.  Los valores válidos son los siguientes:<br /><br /> -   AddressBook: almacén de certificados para otros usuarios.<br />-   AuthRoot: almacén de certificados para las entidades de certificación \(CA\) de terceros.<br />-   CertificatAuthority: almacén de certificados para las entidades de certificación \(CA\) intermedias.<br />-   Disallowed: almacén de certificados para los certificados revocados.<br />-   My: almacén de certificados para los certificados personales.<br />-   Root: almacén de certificados para las entidades de certificación \(CA\) raíz de confianza.<br />-   TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.<br />-   TrustedPublisher: almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.|  
|`X509FindType`|Define el tipo de búsqueda de X.509 que se va a ejecutar.  Los valores válidos son los siguientes:<br /><br /> -   FindByThumbprint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## Comentarios  
 Utilice este elemento para especificar un certificado X.509 que se utilizará para autenticar el servicio a los clientes utilizando el modo de seguridad de mensajes.  Si está utilizando un certificado que se renovará periódicamente, su huella digital cambiará.  En ese caso, utilice el nombre del asunto como el `X509FindType` porque el certificado se puede volver a emitir con el mismo nombre de asunto.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] uso del elemento, vea [Cómo: Especificar los valores de credenciales de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>   
 [Cómo: Especificar los valores de credenciales de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)