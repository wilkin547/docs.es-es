---
description: 'Más información acerca de: <custom>'
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 327a5d7ff1bab88a1633d7a10095e708e6b1a533
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725914"
---
# \<custom>

Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`address`|Un URI que especifica la dirección de extremo del nodo del mismo nivel que hospeda el servicio de resolución del mismo nivel personalizado.|  
|`resolverType`|Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento. Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<headers>](headers-element.md)|Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.|  
  
## <a name="remarks"></a>Observaciones  

 Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de extremo del igual que hospeda el servicio y cualquier configuración obligatoria concreta. Para obtener más información sobre cómo crear un solucionador personalizado, vea [Agregar un solucionador personalizado a una aplicación de PeerChannel](/previous-versions/ms730105(v=vs.90)).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [Resoluciones del mismo nivel](../../../wcf/feature-details/peer-resolvers.md)
- [Adición de una resolución personalizada a una aplicación PeerChannel](/previous-versions/ms730105(v=vs.90))
