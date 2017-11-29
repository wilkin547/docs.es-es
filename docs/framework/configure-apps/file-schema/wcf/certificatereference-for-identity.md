---
title: '&lt;certificateReference&gt; para &lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 883ae318e32493013f009f3580ef102e4d39b3e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificatereferencegt-for-ltidentitygt"></a>&lt;certificateReference&gt; para &lt;identity&gt;
Especifica los valores para la validación del certificado X.509. Un cliente [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] seguro que se conecta a un extremo con esta identidad comprueba que las notificaciones presentadas por el servidor contienen la notificación de identidad utilizada para construir esta identidad.  
  
 \<identidad >  
\<certificateReference >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|findValue|Especifica el valor que se va a buscar en el almacén de certificados de X.509 . El tipo contenido en este atributo debe satisfacer los requisitos del valor `X509FindType` especificado. El valor predeterminado es una cadena vacía.|  
|isChainIncluded|Valor de tipo booleano que especifica si la validación se hace mediante una cadena de certificados.|  
|storeLocation|Especifica la ubicación del almacén de certificados que el cliente puede usar para validar el certificado del servidor.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -LocalMachine: El almacén de certificados asignado al equipo local.<br />-CurrentUser: El almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Especifica el nombre del almacén del certificado X.509 que se va a abrir.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -AddressBook: Almacén de certificados para otros usuarios.<br />-AuthRoot: Almacén de certificados para entidades de certificación (CA) de terceros.<br />-CertificateAuthority: Almacén de certificados para las CA intermedias.<br />-Disallowed: Almacén de certificados para certificados revocados.<br />-My: Almacén de certificados para los certificados personales.<br />-Root: Almacén de certificados para CA raíz de confianza.<br />-TrustedPeople: Almacén de certificados para las personas de confianza directa y recursos.<br />-TrustedPublisher: Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Especifica el tipo de búsqueda de X.509 que se va a ejecutar. El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identidad >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica los valores que permiten la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>
