---
title: "&lt;add&gt; de &lt;scopedCertificates&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;add&gt; de &lt;scopedCertificates&gt; (elemento)
Agrega un certificado X.509 a la colección de certificados con ámbito.  
  
## Sintaxis  
  
```  
  
<add findValue="String"  
          storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
          targetUri="string"  
         x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"   
/>   
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|targetUri|Cadena.  Especifica el URI del servicio asociado al certificado.|  
|findValue|Cadena.  Valor que se va a buscar.|  
|x509FindType|Enumeración.  Uno de los campos de certificado en que buscar.|  
|storeLocation|Enumeración.  Una de las dos ubicaciones de almacén en que buscar.|  
|storeName|Enumeración.  Uno de los almacenes del sistema en que buscar.|  
  
## AtributofindValue  
  
|Valor|Descripción|  
|-----------|-----------------|  
|String|El valor depende del campo \(se especifica por el atributo X509FindType\) en que se busca.  Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.|  
  
## Atributo x509FindType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## Atributo storeLocation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|CurrentUser o LocalMachine.|  
  
## Atributo storeName  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<scopedCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Representa una colección de certificados X.509 proporcionada por servicios concretos \(con ámbito\) para la autenticación.|  
  
## Comentarios  
 Este elemento permite al cliente configurar un certificado del servicio que se va a utilizar basándose en la dirección URL del servicio con el que se comunica.  Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios \(el servicio final, así como los servicios del token de seguridad intermediarios\).  Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.  
  
 Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.  
  
 Para obtener más información, consulte la sección "Certificados con ámbito"de [Cómo crear un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
## Ejemplo  
 En el ejemplo siguiente se agrega un certificado X.509 a la colección.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <serviceCertificate>  
     <scopedCertificates>  
      <add targetUri="http://www.contoso.com"   
       findValue="www.Contoso.com"   
       storeLocation="LocalMachine"  
       storeName="Root"   
       x509FindType="FindByIssuerName" />  
     </scopedCertificates>  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>   
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>   
 [Cómo crear un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)