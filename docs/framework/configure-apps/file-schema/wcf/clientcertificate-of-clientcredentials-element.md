---
title: "&lt;clientCertificate&gt; de &lt;clientCredentials&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;clientCertificate&gt; de &lt;clientCredentials&gt; (elemento)
Define un certificado X.509 usado para autenticar un cliente a un servicio.  
  
## Sintaxis  
  
```  
  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.  El tipo contenido en el atributo debe satisfacer los requisitos del valor del atributo `X509FindType`.  El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del certificado X.509 que usa el cliente para autenticarse al servicio.  Los valores válidos son los siguientes:<br /><br /> -   LocalMachine: el almacén de certificados asignado al equipo local.<br />-   CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.  Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a buscar.  Los valores válidos son los siguientes:<br /><br /> -   AddressBook: almacén de certificados para otros usuarios.<br />-   AuthRoot: almacén del certificado para las entidades de certificación \(CA\) de otros fabricantes.<br />-   CertificateAuthority: almacén del certificado para las entidades de certificación \(CA\) intermedias.<br />-   Disallowed: almacén de certificados para los certificados revocados.<br />-   My: almacén de certificados para los certificados personales.<br />-   Root: almacén del certificado para las entidades de certificación \(CA\) raíz de confianza.<br />-   TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.<br />-   TrustedPublisher: almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.  Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Define el tipo de búsqueda de X.509 que se va a ejecutar.  El tipo contenido en el atributo `findValue` debe satisfacer los requisitos de este atributo.  Los valores válidos son los siguientes:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.  Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
  
## Comentarios  
 Este elemento de configuración especifica que el certificado utilizado para autenticar el cliente con este elemento.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Cómo: Especificar los valores de credenciales de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Cómo: Especificar los valores de credenciales de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)