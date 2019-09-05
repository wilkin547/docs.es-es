---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252142"
---
# <a name="certificatereference"></a>\<certificateReference>
Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateReference**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|storeName|Nombre del almacén de certificados X. 509. El valor predeterminado es "My". Opcional.|  
|storeLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica la ubicación del almacén de certificados X. 509. El valor predeterminado es "LocalMachine". Opcional.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> Valor que especifica el tipo de búsqueda que se va a ejecutar. El valor predeterminado es "FindBySubjectDistinguishedName". Opcional.|  
|findValue|El valor que se va a buscar en el almacén de certificados X.509. Opcional.|  
|isChainIncluded|Especifica si se debe realizar la validación mediante la cadena de certificados. El valor predeterminado es "true"; la validación se realiza mediante la cadena de certificados. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|Configura el certificado que se usa para cifrar y descifrar los tokens.|  
  
## <a name="remarks"></a>Comentarios  
 El `<certificateReference>` elemento especifica valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados. Cuando se especifica como el elemento secundario del `<serviceCertificate>` elemento, especifica la configuración de ubicación y comprobación del certificado X. 509 que se usa para cifrar y descifrar los tokens. El elemento se representa mediante la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase. `<certificateReference>`
