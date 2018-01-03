---
title: '&lt;comportamientos&gt; de flujo de trabajo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83c1bf4beb244b72d2fe3d82d749ff6ae6723baf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a>&lt;comportamientos&gt; de flujo de trabajo
Este elemento contiene el **serviceBehaviors** colección.  Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo. Su único identifica cada elemento de comportamiento **nombre** atributo.  
  
 \<sistema. ServiceModel >  
  
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
 Ninguna  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de flujo de trabajo.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
