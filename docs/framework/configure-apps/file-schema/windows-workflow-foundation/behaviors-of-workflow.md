---
title: "&lt;behaviors&gt; de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;behaviors&gt; de flujo de trabajo
Este elemento contiene la colección **serviceBehaviors**.  Cada elemento de la colección define elementos de comportamiento utilizados por servicios del flujo de trabajo.  Su atributo de **name** único identifica cada elemento de comportamiento.  
  
 \<system.ServiceModel\>  
  
## Sintaxis  
  
```  
  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguna  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Esta sección de configuración representa todos los comportamientos definidos para un servicio de flujo de trabajo concreto.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de flujo de trabajo.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>   
 [Configuración y extensión del tiempo de ejecución con comportamientos](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)