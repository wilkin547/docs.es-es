---
title: Usar actividades de procedimiento
ms.date: 03/30/2017
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
ms.openlocfilehash: bd83f1a0fa9f3af7c22cee73fbc4f984a9ebf53c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804781"
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
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`