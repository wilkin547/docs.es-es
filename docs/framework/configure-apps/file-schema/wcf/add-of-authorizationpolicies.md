---
title: <add> de <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 532f7f1a74cb3af24d7a1bc26046be901f3cf025
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205243"
---
# <a name="add-of-authorizationpolicies"></a>\<Agregar > de \<authorizationPolicies >
Especifica una directiva de autorización para la transformación de notificaciones.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<comportamiento >  
\<serviceAuthorization>  
\<authorizationPolicies>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`policyType`|Atributo de cadena requerido.<br /><br /> El modelo de control de acceso de Windows Communication Foundation (WCF) admite el aprovisionamiento de un conjunto de directivas de autorización como tipos. Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones. Se puede permitir o denegar el acceso en base a eso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<authorizationPolicies>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|Especifica una colección de tipos de directiva de autorización.|  
  
## <a name="remarks"></a>Comentarios  
 Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena. El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas. Se puede permitir o denegar el acceso en base a eso. Para obtener más información sobre el funcionamiento de una directiva de autorización, consulte <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [Autorización de acceso a operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [Filtrar para crear un administrador de autorización personalizado para un servicio](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [Directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md)
