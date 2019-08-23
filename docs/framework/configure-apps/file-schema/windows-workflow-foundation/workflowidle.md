---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947164"
---
# <a name="workflowidle"></a>\<workflowIdle>
Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<workflowIdle>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|timeToPersist|Valor TimeSpan que especifica la duración entre el momento en que el flujo de trabajo se vuelve inactivo y se conserva. El valor predeterminado es TimeSpan. MaxValue.<br /><br /> La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva. Este atributo es útil si desea conservar una instancia de flujo de trabajo más agresiva mientras mantiene la instancia en memoria durante el tiempo que sea posible. Este atributo solo es válido si su valor es menor que el atributo **timeToUnload** . Si es mayor, se omite. Si este atributo transcurre antes del valor especificado por el atributo **timeToUnload** , la persistencia debe completarse antes de que se descargue el flujo de trabajo. Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo. El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables. Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.|  
|timeToUnload|Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga. El valor predeterminado es 1 minuto.<br /><br /> Descargar un flujo de trabajo implica que también se conserva. Si este atributo se establece en cero, la instancia de flujo de trabajo se conserva y se descarga inmediatamente después de que el flujo de trabajo se vuelva inactivo. Si se establece este atributo en TimeSpan. MaxValue, se deshabilita la operación de descarga. Las instancias de flujo de trabajo inactivas nunca se descargan.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<comportamiento > de \<serviceBehaviors >](behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
