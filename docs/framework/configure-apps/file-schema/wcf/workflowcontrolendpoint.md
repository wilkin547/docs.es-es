---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854786"
---
# \<workflowControlEndpoint>
Este elemento de configuración define un punto de conexión estándar para controlar la ejecución de instancias de flujo de trabajo (crear, ejecutar, suspender, terminar, etc).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Cadena que especifica el nombre de la configuración del punto de conexión estándar. El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
