---
title: "Composici&#243;n de actividad b&#225;sica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Composici&#243;n de actividad b&#225;sica
En este ejemplo se muestra cómo crear actividades personalizadas y actividades proporcionadas por el sistema para compilar más actividades personalizadas.  
  
 El flujo de trabajo que usa la actividad Survey programa el estudio con una lista de preguntas y, a continuación, genera las respuestas recibidas.  
  
## Detalles del ejemplo  
 Este ejemplo usa tres actividades personalizadas.`ReadLine` es una <xref:System.Activities.NativeActivity>\<cadena\> que crea un <xref:System.Activities.Bookmark> cuando se programa, y establece el <xref:System.Activities.OutArgument%601>`Return` en el valor con el que se reanuda <xref:System.Activities.Bookmark>.`Prompt` es una <xref:System.Activities.Activity%601>\<cadena\> que toma un <xref:System.Activities.InArgument%601>\<cadena\> denominado `Text` y devuelve la respuesta de los usuarios en `Result`<xref:System.Activities.OutArgument%601>\<string\>.La actividad `Prompt` utiliza las actividades <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.WriteLine> que se distribuyen como parte de .NET Framework y también incorpora la actividad `ReadLine` personalizada para obtener los datos proporcionados por el usuario.La última actividad personalizada es la actividad `Survey`.Es un objeto <xref:System.Activities.Activity>\<ICollection\<cadena\>\>.Esta actividad toma un argumento <xref:System.Activities.InArgument%601>\<IEnumerable\<cadena\>\> denominado `Questions` y rellena el argumento de salida `Result` con las respuestas.La actividad `Survey` utiliza los objetos <xref:System.Activities.Statements.ForEach>, <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.AddToCollection%601> de .NET Framework y emplea la actividad `Prompt` para realizar las preguntas del estudio y obtener las respuestas.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo **BasicActivityComposition.sln** en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## Vea también