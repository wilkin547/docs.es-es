---
title: "&lt;workflowIdle&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;workflowIdle&gt;
Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <workflowIdle timeToPersist=”TimeSpan”  
          timeToUnload=”TimeSpan” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|timeToPersist|Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva.  El valor predeterminado es TimeSpan.MaxValue.<br /><br /> La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva.  Este atributo es útil si desea conservar de forma más agresiva una instancia de flujo de trabajo mientras se mantiene la instancia en memoria durante el máximo tiempo posible.  Este atributo solo es válido si su valor es menor que el atributo **timeToUnload**.  Si es mayor, se omite.  Si este atributo transcurre antes de que el valor especificado por el atributo **timeToUnload**, la conservación debe completarse antes de que se descargue el flujo de trabajo.  Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo.  El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables.  Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.|  
|timeToUnload|Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga.  El valor predeterminado es 1 minuto.<br /><br /> Descargar un flujo de trabajo implica que también se conserva.  Si este atributo se pone a cero, la instancia de flujo de trabajo se conserva y se descarga de inmediato en cuanto el flujo de trabajo se vuelve inactivo.  Al establecer este atributo en TimeSpan.MaxValue, se deshabilita de forma eficaz la operación de descarga.  Las instancias de flujo de trabajo inactivas nunca se descargan.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\> de \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## Vea también  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>