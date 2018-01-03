---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2440f322ea7dbd3a6d6f9d56878273c49b26bfa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.  
  
\<sistema. ServiceModel >  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<workflowIdle >  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|timeToPersist|Un valor Timespan que especifica la duración entre el momento en el flujo de trabajo se vuelve inactivo y se conserva. El valor predeterminado es TimeSpan.MaxValue.<br /><br /> La duración comienza a transcurrir cuando la instancia de flujo de trabajo se vuelve inactiva. Este atributo es útil si desea conservar una instancia de flujo de trabajo de una forma más agresiva mientras mantiene la instancia en memoria mientras sea posible. Este atributo solo es válido si su valor es menor que el **timeToUnload** atributo. Si es mayor, se omite. Si este atributo transcurre antes de que el valor especificado por el **timeToUnload** atributo, la persistencia deberá completarse antes de que se descarga el flujo de trabajo. Esto implica que se puede retrasar la operación de descarga hasta que se conserve el flujo de trabajo. El nivel de conservación es responsable de administrar todos los reintentos de errores transitorios y solo produce excepciones con errores no recuperables. Por consiguiente, cualquier excepción producida durante la conservación se trata como grave y se anula la instancia de flujo de trabajo.|  
|timeToUnload|Un valor Timespan que especifica el tiempo que transcurre entre el momento en que el flujo de trabajo se vuelve inactivo y descarga. El valor predeterminado es 1 minuto.<br /><br /> Descargar un flujo de trabajo implica que también se conserva. Si este atributo se establece en cero se conservan y se descargan inmediatamente después de la instancia de flujo de trabajo del flujo de trabajo se vuelve inactivo. Establecer este atributo en TimeSpan.MaxValue eficazmente, deshabilita la operación de descarga. Las instancias de flujo de trabajo inactivas nunca se descargan.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamiento > de \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
