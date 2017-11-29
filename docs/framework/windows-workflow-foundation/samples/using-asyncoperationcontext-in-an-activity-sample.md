---
title: Usar AsyncOperationContext en un ejemplo de actividad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa2a68bccb4daff380b8de7368c6709c41c5799a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a>Usar AsyncOperationContext en un ejemplo de actividad
En este ejemplo se muestra cómo desarrollar una actividad <xref:System.Activities.CodeActivity> personalizada que utiliza <xref:System.Activities.AsyncCodeActivityContext> para realizar trabajo de forma asincrónica fuera del flujo de trabajo.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 La actividad de ejemplo utiliza los métodos <xref:System.IO.FileStream.BeginWrite%2A> y <xref:System.IO.FileStream.EndWrite%2A> de la clase <xref:System.IO.FileStream> para escribir datos en un archivo de forma asincrónica. El patrón introducido aquí se puede adaptar para el uso con otros métodos asincrónicos. Mientras se está ejecutando la operación asincrónica, se pueden ejecutar otras actividades del flujo de trabajo, pero este no se puede guardar.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo Async.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`  
  
## <a name="see-also"></a>Vea también
