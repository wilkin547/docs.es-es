---
title: "Composición de actividad básica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f1c94a276cf2e76d595a22c5c930614818bbf2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="basic-activity-composition"></a>Composición de actividad básica
En este ejemplo se muestra cómo crear actividades personalizadas y actividades proporcionadas por el sistema para compilar más actividades personalizadas.  
  
 El flujo de trabajo que usa la actividad Survey programa el estudio con una lista de preguntas y, a continuación, genera las respuestas recibidas.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Este ejemplo usa tres actividades personalizadas. `ReadLine`es una sencilla <xref:System.Activities.NativeActivity> \<cadena > que crea un <xref:System.Activities.Bookmark> cuando se programa y, a continuación, Establece la `Return` <xref:System.Activities.OutArgument%601> en el valor con el que el <xref:System.Activities.Bookmark> se reanuda. `Prompt`es un <xref:System.Activities.Activity%601> \<cadena > que toma un <xref:System.Activities.InArgument%601>< cadena\> denominado `Text` y devuelve los usuarios de respuesta en el `Result` <xref:System.Activities.OutArgument%601> \<cadena >. La actividad `Prompt` utiliza las actividades <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.WriteLine> que se distribuyen como parte de .NET Framework y también incorpora la actividad `ReadLine` personalizada para obtener los datos proporcionados por el usuario. La última actividad personalizada es la actividad `Survey`. Es un <xref:System.Activities.Activity>< ICollection\<cadena >>.  Esta actividad toma un <xref:System.Activities.InArgument%601>< IEnumerable < cadena\>> denominado `Questions` y rellena el `Result` argumento con las respuestas de salida. La actividad `Survey` utiliza los objetos <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.AddToCollection%601> de .NET Framework y emplea la actividad `Prompt` para realizar las preguntas del estudio y obtener las respuestas.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la **BasicActivityComposition.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## <a name="see-also"></a>Vea también
