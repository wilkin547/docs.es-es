---
title: Usar la clase WorkflowInvoker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 553367916ff249118a8fcdd8273382402b90cfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-workflowinvoker-class"></a>Usar la clase WorkflowInvoker
En este ejemplo se muestra cómo utilizar la clase <xref:System.Activities.WorkflowInvoker> para invocar una actividad como si fuera un método.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Utilizar la clase <xref:System.Activities.WorkflowInvoker> es la manera más simple de ejecutar una actividad. Está diseñada para ejecutar una actividad directamente como si fuese una llamada a un método. Es una API ligera, con alto rendimiento y sencilla de usar para utilizar en escenarios donde la ejecución de una actividad no requiere la infraestructura de control que proporcionan otras variaciones de hospedaje.  
  
 El ejemplo usa una actividad personalizada que deriva de <xref:System.Activities.CodeActivity%601>< Int32\> denominado `Add` que suma dos <xref:System.Activities.InArgument%601>, `X` y `Y`y devuelve un `Result` <xref:System.Activities.OutArgument%601>. (<xref:System.Activities.CodeActivity%601>\<T > deriva <xref:System.Activities.Activity%601>< T\>, que tiene un <xref:System.Activities.OutArgument%601> \<T > denominado `Result`.) A `Dictionary` \<cadena, objeto > se usa para pasar argumentos a una actividad que se invoca mediante <xref:System.Activities.WorkflowInvoker>. La clave del diccionario corresponde al nombre de un argumento de la actividad invocada. El valor asociado a una clave determinada se enlaza al argumento identificado por la clave.  
  
 En el ejemplo se llama a <xref:System.Activities.WorkflowInvoker.Invoke%2A> y se pasa un diccionario que contiene valores para `X` e `Y`. La clase <xref:System.Activities.WorkflowInvoker> enlaza estos valores a los argumentos de la actividad `Add`, ejecuta la actividad y devuelve el resultado.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución Invoker.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`