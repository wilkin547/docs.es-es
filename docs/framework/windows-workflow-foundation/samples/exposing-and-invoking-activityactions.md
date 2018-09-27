---
title: Exponer e invocar ActivityActions
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 99207c33d82ec9028da2355cc792c366dc5e0cc6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47398568"
---
# <a name="exposing-and-invoking-activityactions"></a>Exponer e invocar ActivityActions
En este ejemplo se muestra cómo desarrollar una actividad personalizada que tiene un objeto <xref:System.Activities.ActivityAction>. También muestra cómo utilizar esta actividad proporcionando una implementación de <xref:System.Activities.ActivityAction>.  
  
 Un <xref:System.Activities.ActivityAction> permite que un autor de actividad exponen "agujeros" con firmas específicas donde el usuario de la actividad puede conectar un comportamiento personalizado. Por ejemplo, la actividad <xref:System.Activities.Statements.ForEach%601>, (que actúa sobre una colección de elementos) tiene un objeto <xref:System.Activities.ActivityAction> que permite al usuario de la actividad agregar un comportamiento que actúa sobre el elemento de iteración actual.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra el **ActivityAction.sln** solución de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`