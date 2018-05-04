---
title: '&lt;ServicePrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: e5c1f5a6986d57d20180560b12f5c7c5540a590d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltserviceprincipalnamegt"></a>&lt;ServicePrincipalName&gt;
Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).  
  
 Para obtener más información acerca de cómo establecer el SPN, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<identidad >  
\<servicePrincipalName >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|value|El nombre por el que un cliente identifica de manera unívoca una instancia de un servicio. Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN. Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identidad >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica la identidad del servicio que va a autenticar el cliente.|  
  
## <a name="remarks"></a>Comentarios  
 Un cliente seguro de Windows Communication Foundation (WCF) que se conecta a un extremo con esta identidad utiliza SPN al realizar la autenticación de SSPI con el punto de conexión.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<identidad >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
