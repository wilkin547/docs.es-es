---
title: Composición de actividad básica
ms.date: 03/30/2017
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
ms.openlocfilehash: 67cdad30c60ebbeaf546d7086c6e895fa49a51c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="basic-activity-composition"></a>Composición de actividad básica
En este ejemplo se muestra cómo crear actividades personalizadas y actividades proporcionadas por el sistema para compilar más actividades personalizadas.  
  
 El flujo de trabajo que usa la actividad Survey programa el estudio con una lista de preguntas y, a continuación, genera las respuestas recibidas.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Este ejemplo usa tres actividades personalizadas. `ReadLine` es una sencilla <xref:System.Activities.NativeActivity> \<cadena > que crea un <xref:System.Activities.Bookmark> cuando se programa y, a continuación, Establece la `Return` <xref:System.Activities.OutArgument%601> en el valor con el que el <xref:System.Activities.Bookmark> se reanuda. `Prompt` es un <xref:System.Activities.Activity%601> \<cadena > que toma un <xref:System.Activities.InArgument%601>< cadena\> denominado `Text` y devuelve los usuarios de respuesta en el `Result` <xref:System.Activities.OutArgument%601> \<cadena >. La actividad `Prompt` utiliza las actividades <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.WriteLine> que se distribuyen como parte de .NET Framework y también incorpora la actividad `ReadLine` personalizada para obtener los datos proporcionados por el usuario. La última actividad personalizada es la actividad `Survey`. Es un <xref:System.Activities.Activity>< ICollection\<cadena >>.  Esta actividad toma un <xref:System.Activities.InArgument%601>< IEnumerable < cadena\>> denominado `Questions` y rellena el `Result` argumento con las respuestas de salida. La actividad `Survey` utiliza los objetos <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.AddToCollection%601> de .NET Framework y emplea la actividad `Prompt` para realizar las preguntas del estudio y obtener las respuestas.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la **BasicActivityComposition.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`