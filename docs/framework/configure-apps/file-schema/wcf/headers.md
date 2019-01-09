---
title: '&lt;Encabezados&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 84b9a9437d4b0dfae72a6e625b21f2b830eb28d8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147868"
---
# <a name="ltheadersgt"></a>&lt;Encabezados&gt;
Uno o más encabezados SOAP pueden direccionar un punto de conexión además de su URI básico. Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios. Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados. Las entradas en la colección de encabezado de extremo son los elementos XML definidos por el usuario. Cada elemento tiene que ser XML correcto.  
  
 \<system.ServiceModel>  
\<cliente >  
\<punto de conexión >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|Región||  
|Miembro||  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<punto de conexión >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Configura tipos diferentes de puntos de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el punto de conexión. Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el punto de conexión un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [Puntos de conexión: Las direcciones, enlaces y contratos](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
