---
title: "&lt;certificate&gt; del elemento &lt;clientCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;certificate&gt; del elemento &lt;clientCertificate&gt;
Especifica un certificado X.509 usado para firmar y cifrar mensajes.  
  
## Sintaxis  
  
```  
  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.  El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado.  El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor.  Los valores válidos son los siguientes:<br /><br /> -   LocalMachine: el almacén de certificados asignado al equipo local.<br />-   CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a abrir.  Los valores válidos son los siguientes:<br /><br /> -   AddressBook: almacén de certificados para otros usuarios.<br />-   AuthRoot: almacén de certificados para las entidades de certificación \(CA\) de terceros.<br />-   CertificationAuthority: almacén de certificados para las entidades de certificación \(CA\) intermedias.<br />-   Disallowed: almacén de certificados para los certificados revocados.<br />-   My: almacén de certificados para los certificados personales.<br />-   Root: almacén de certificados para las entidades de certificación \(CA\) raíz de confianza.<br />-   TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.<br />-   TrustedPublisher: almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.|  
|`X509FindType`|Define el tipo de búsqueda de X.509 que se va a ejecutar.  Los valores válidos son los siguientes:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## Comentarios  
 El elemento `<certificate>` se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.  Esto se produce al utilizar el patrón de comunicación dúplex.  En el patrón de solicitud\/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.  Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.  Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.  Para obtener más información sobre los servicios dúplex, consulte [Creación de un contrato dúplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## Ejemplo  
 El código siguiente especifica cómo buscar un certificado X.509 adecuado y un tipo de validación personalizado en el elemento `<authentication>`.  
  
```  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Cómo crear un servicio que emplee un validador de certificado personalizado](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)