---
title: Exponer e invocar ActivityActions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4285718ef1829e9432957278d5ca7959e32e4511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-and-invoking-activityactions"></a>Exponer e invocar ActivityActions
En este ejemplo se muestra cómo desarrollar una actividad personalizada que tiene un objeto <xref:System.Activities.ActivityAction>. También muestra cómo utilizar esta actividad proporcionando una implementación de <xref:System.Activities.ActivityAction>.  
  
 Un <xref:System.Activities.ActivityAction> permite que un autor de actividad exponer los "agujeros" con firmas concretas donde el usuario de la actividad puede conectar un comportamiento personalizado. Por ejemplo, el <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` actividad, (que actúa sobre una colección de elementos), tiene un <xref:System.Activities.ActivityAction> que permite al usuario de la actividad agregar un comportamiento que actúa sobre el elemento de iteración actual.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la **ActivityAction.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`