---
title: <behaviors>del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 7dd3b0b20c9d7accd80a85b3693e67ffc9b729e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946004"
---
# <a name="behaviors-of-workflow"></a>\<comportamientos > del flujo de trabajo
Este elemento contiene la colección **serviceBehaviors** .  Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo. Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de flujo de trabajo.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Configuración y extensión del tiempo de ejecución con comportamientos](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
