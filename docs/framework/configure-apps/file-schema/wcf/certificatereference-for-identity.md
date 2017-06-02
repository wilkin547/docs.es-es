---
title: "&lt;certificateReference&gt; para &lt;identity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;certificateReference&gt; para &lt;identity&gt;
Especifica los valores para la validación del certificado X.509.  Un cliente [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] seguro que se conecta a un extremo con esta identidad comprueba que las notificaciones presentadas por el servidor contienen la notificación de identidad utilizada para construir esta identidad.  
  
## Sintaxis  
  
```  
  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|findValue|Especifica el valor que se va a buscar en el almacén de certificados de X.509 .  El tipo contenido en este atributo debe satisfacer los requisitos del valor `X509FindType` especificado.  El valor predeterminado es una cadena vacía.|  
|isChainIncluded|Valor de tipo booleano que especifica si la validación se hace mediante una cadena de certificados.|  
|storeLocation|Especifica la ubicación del almacén de certificados que el cliente puede usar para validar el certificado del servidor.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   LocalMachine: el almacén de certificados asignado a la máquina local.<br />-   CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Especifica el nombre del almacén del certificado X.509 que se va a abrir.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   AddressBook: almacén de certificados para otros usuarios.<br />-   AuthRoot: almacén de certificados para las entidades de certificación \(CA\) de terceros.<br />-   CertificateAuthority: almacén de certificados para las CA intermedias.<br />-   Disallowed: almacén de certificados para los certificados revocados.<br />-   My: almacén de certificados para los certificados personales.<br />-   Root: almacén de certificados para las CA de raíz de confianza.<br />-   TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.<br />-   TrustedPublisher: almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Especifica el tipo de búsqueda de X.509 que se va a ejecutar.  El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica los valores que permiten la autenticación de un extremo por otros extremos que intercambian mensajes con él.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>   
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>