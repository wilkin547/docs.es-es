---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423025"
---
# <a name="certificatereference"></a>\<certificateReference>
Especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<serviceCertificate>  
\<certificateReference>  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|storeName|El nombre del almacén de certificados X.509. El valor predeterminado es "My". Opcional.|  
|storeLocation|Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica la ubicación del almacén de certificados X.509. El valor predeterminado es "LocalMachine". Opcional.|  
|x509FindType|Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valor que especifica el tipo de búsqueda que se ejecuta. El valor predeterminado es "FindBySubjectDistinguishedName". Opcional.|  
|findValue|El valor que se va a buscar en el almacén de certificados X.509. Opcional.|  
|isChainIncluded|Especifica si se debe realizar la validación mediante el uso de la cadena de certificados. El valor predeterminado es "true"; se realiza la validación mediante el uso de la cadena de certificados. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura el certificado que se usa para cifrar y descifrar los tokens.|  
  
## <a name="remarks"></a>Comentarios  
 El `<certificateReference>` elemento especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados. Cuando se especifica como el elemento secundario de la `<serviceCertificate>` elemento, especifica la configuración de ubicación y la comprobación del certificado X.509 que se usa para cifrar y descifrar los tokens. El `<certificateReference>` elemento representado por la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.
