---
title: '&lt;certificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatereferencegt"></a>&lt;certificateReference&gt;
Especifica valores que se usan para encontrar y validar un certificado X.509 en un almacén de certificados.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<serviceCertificate >  
\<certificateReference >  
  
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
|x509FindType|Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valor que especifica el tipo de búsqueda que va a ejecutarse. El valor predeterminado es "FindBySubjectDistinguishedName". Opcional.|  
|findValue|El valor que se va a buscar en el almacén de certificados X.509. Opcional.|  
|isChainIncluded|Especifica si se debe realizar validación mediante el uso de la cadena de certificados. El valor predeterminado es "true"; se realiza la validación mediante el uso de la cadena de certificados. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura el certificado que se utiliza para cifrar y descifrar los tokens.|  
  
## <a name="remarks"></a>Comentarios  
 El `<certificateReference>` elemento especifica los valores que se usan para encontrar y validar un certificado X.509 en un almacén de certificados. Cuando se especifica como el elemento secundario de la `<serviceCertficate>` elemento, especifica la configuración de ubicación y la comprobación del certificado X.509 que se utiliza para cifrar y descifrar los tokens. El `<certificateReference>` elemento representado por la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.
