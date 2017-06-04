---
title: "Elemento &lt;authentication&gt; de &lt;clientCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Elemento &lt;authentication&gt; de &lt;clientCertificate&gt;
Especifica los comportamientos de autenticación para los certificados de cliente utilizados por un servicio.  
  
## Sintaxis  
  
```  
  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|customCertificateValidatorType|Cadena opcional.  Tipo y ensamblado utilizados para validar un tipo personalizado.  Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.|  
|certificateValidationMode|Enumeración opcional.  Especifica uno de los modos usados para validar las credenciales.  Este atributo es del tipo [System.Servicemodel.Security.X509CertificateValidationMode](assetId:///System.Servicemodel.Security.X509CertificateValidationMode?qualifyHint=False&amp;autoUpgrade=True).  Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.  De manera predeterminada, es `ChainTrust`.|  
|includeWindowsGroups|Opcional booleano.  Especifica si los grupos de Windows están incluidos en el contexto de seguridad.  Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.  Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.|  
|mapClientCertificateToWindowsAcccount|booleano.  Especifica si el cliente puede estar asignado a una identidad de Windows utilizando el certificado.  Active Directory debe estar habilitado para ello.|  
|revocationMode|Enumeración opcional.  Uno de los modos utilizados para comprobar listas de certificados revocadas \(RCL\).  De manera predeterminada, es `Online`.  Se omite este valor al usar la seguridad de transporte HTTP.|  
|trustedStoreLocation|Enumeración opcional.  Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.  Se utiliza este valor cuando un certificado del servicio se negocia al cliente.  La validación se realiza contra el **Personas de confianza** almacén en la ubicación del almacén especificada.  De manera predeterminada, es `CurrentUser`.|  
  
## Atributo customCertificateValidatorType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|String|Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.|  
  
## Atributo certificateValidationMode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los valores siguientes: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Para obtener más información, consulte [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Atributo revocationMode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los valores siguientes: NoCheck, Online, Offline.  Para obtener más información, consulte [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Atributo trustedStoreLocation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: `LocalMachine` o `CurrentUser`.  De manera predeterminada, es `CurrentUser`.  Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente bajo `LocalMachine`.  Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en `CurrentUser`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|Define un certificado X.509 que se usa para autenticar un cliente en un servicio.|  
  
## Comentarios  
 El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.  Le permite personalizar cómo se autentican los clientes.  Puede establecer el atributo `certificateValidationMode` en `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`.  De forma predeterminada, el nivel está establecido en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una *entidad emisora raíz* en la parte superior de la cadena.  Este es el modo más seguro.  También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos \(confianza del mismo nivel\) se aceptan, así como los certificados que están en una cadena de confianza.  Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.  Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.  
  
 También puede establecer el valor en `Custom`.  Cuando se establezca en el valor `Custom`, también debe establecer el atributo `customCertificateValidatorType` en un ensamblado y tipo utilizados para validar el certificado.  Para crear su propio validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta.  Para obtener más información, consulte [Cómo crear un servicio que emplee un validador de certificado personalizado](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## Ejemplo  
 El código siguiente especifica un certificado X.509 y un tipo de validación personalizado en el elemento `<authentication>`.  
  
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
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>   
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>   
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Cómo crear un servicio que emplee un validador de certificado personalizado](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)