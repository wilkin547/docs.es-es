---
title: Usar la clase WorkflowInvoker
ms.date: 03/30/2017
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
ms.openlocfilehash: 70fc94b1f190236cb2cb40c407e0172f0213fb7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515819"
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
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`