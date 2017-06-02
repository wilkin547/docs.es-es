---
title: "Usar la clase WorkflowInvoker | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Usar la clase WorkflowInvoker
En este ejemplo se muestra cómo utilizar la clase <xref:System.Activities.WorkflowInvoker> para invocar una actividad como si fuera un método.  
  
## Detalles del ejemplo  
 Utilizar la clase <xref:System.Activities.WorkflowInvoker> es la manera más simple de ejecutar una actividad.Está diseñada para ejecutar una actividad directamente como si fuese una llamada a un método.Es una API ligera, con alto rendimiento y sencilla de usar para utilizar en escenarios donde la ejecución de una actividad no requiere la infraestructura de control que proporcionan otras variaciones de hospedaje.  
  
 En el ejemplo se utiliza una actividad personalizada que deriva de <xref:System.Activities.CodeActivity%601>\<Int32\> denominada `Add` que suma dos <xref:System.Activities.InArgument%601>, `X` e `Y`, y devuelve un `Result`<xref:System.Activities.OutArgument%601>.\(<xref:System.Activities.CodeActivity%601>\<T\> deriva de <xref:System.Activities.Activity%601>\<T\>, que incluye un <xref:System.Activities.OutArgument%601>\<T\> denominado `Result`.\) Se utiliza `Dictionary`\<cadena, objeto\> para pasar argumentos a una actividad que se invoca mediante <xref:System.Activities.WorkflowInvoker>.La clave del diccionario corresponde al nombre de un argumento de la actividad invocada.El valor asociado a una clave determinada se enlaza al argumento identificado por la clave.  
  
 En el ejemplo se llama a <xref:System.Activities.WorkflowInvoker.Invoke%2A> y se pasa un diccionario que contiene valores para `X` e `Y`.La clase <xref:System.Activities.WorkflowInvoker> enlaza estos valores a los argumentos de la actividad `Add`, ejecuta la actividad y devuelve el resultado.  
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución Invoker.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`  
  
## Vea también