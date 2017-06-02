---
title: "Usar actividades de procedimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Usar actividades de procedimiento
En el ejemplo se utilizan las actividades <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> y <xref:System.Activities.Statements.WriteLine> para implementar un juego de adivinanzas.La adivinanza selecciona un número aleatorio y el jugador tiene que adivinar el número.Cuando el jugador envía una suposición incorrecta, el flujo de trabajo proporciona una sugerencia para indicar si es mayor o menor.Si el jugador adivina el número en menos de 7 intentos, se muestra una felicitación especial.  
  
## Actividades personalizadas de este ejemplo  
  
### ReadLine  
 Lee una línea de texto de la consola.Esta actividad deriva de la clase <xref:System.Activities.NativeActivity> y crea un marcador que la aplicación de consola reanuda cuando se lee una línea.  
  
### PromptInt  
 Solicita al usuario que escriba un número y, a continuación, lo lee de una ventana de la consola.La actividad deriva de <xref:System.Activities.Activity%601> y utiliza las actividades <xref:System.Activities.Statements.WriteLine> y `ReadLine`.  
  
##### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución GuessingGame.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## Vea también