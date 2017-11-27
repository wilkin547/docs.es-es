---
title: Usar actividades de procedimiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c391316959829c77d16dd87af51d9fe1915dc88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-procedural-activities"></a>Usar actividades de procedimiento
En el ejemplo se utilizan las actividades <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> y <xref:System.Activities.Statements.WriteLine> para implementar un juego de adivinanzas. La adivinanza selecciona un número aleatorio y el jugador tiene que adivinar el número. Cuando el jugador envía una suposición incorrecta, el flujo de trabajo proporciona una sugerencia para indicar si es mayor o menor. Si el jugador adivina el número en menos de 7 intentos, se muestra una felicitación especial.  
  
## <a name="custom-activities-in-this-sample"></a>Actividades personalizadas de este ejemplo  
  
### <a name="readline"></a>ReadLine  
 Lee una línea de texto de la consola. Esta actividad deriva de la clase <xref:System.Activities.NativeActivity> y crea un marcador que la aplicación de consola reanuda cuando se lee una línea.  
  
### <a name="promptint"></a>PromptInt  
 Solicita al usuario que escriba un número y, a continuación, lo lee de una ventana de la consola. La actividad deriva de <xref:System.Activities.Activity%601> y utiliza las actividades <xref:System.Activities.Statements.WriteLine> y `ReadLine`.  
  
##### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución GuessingGame.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## <a name="see-also"></a>Vea también
