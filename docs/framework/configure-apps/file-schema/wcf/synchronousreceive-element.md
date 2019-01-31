---
title: <synchronousReceive> (elemento)
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: f4a8868304ebae9a7ed5e6afbfb14fb2116afc49
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278484"
---
# <a name="synchronousreceive-element"></a>\<synchronousReceive > elemento
Este elemento de configuración se usa para especificar el comportamiento del tiempo de ejecución para recibir mensajes en una aplicación de cliente o de servicio. No tiene ningún atributo o elementos secundarios.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<synchronousReceive>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 Utilice este comportamiento para indicar a la escucha del canal que utilice un receptor sincrónico en lugar del valor predeterminado, asincrónico. Windows Communication Foundation (WCF) emite un nuevo subproceso para bombear para cada canal aceptado. Si hay muchos canales, cabe la posibilidad de quedarse sin subprocesos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
