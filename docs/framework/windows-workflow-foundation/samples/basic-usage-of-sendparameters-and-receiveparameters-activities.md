---
title: "Uso básico de las actividades SendParameters y ReceiveParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 375168f45ee0bba5df1ca723398d448ead89555c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Uso básico de las actividades SendParameters y ReceiveParameters
En este ejemplo se muestra el uso de las actividades <xref:System.ServiceModel.Activities.SendParametersContent> y <xref:System.ServiceModel.Activities.ReceiveParametersContent>. El servicio expone una operación que toma un argumento de cadena y devuelve la entrada al cliente. En el ejemplo se muestra cómo preparar los parámetros para estas actividades de mensajería.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  Primero, ejecute la aplicación EchoWorkflowService generada en [directorio base de la solución]\EchoWorkflowService\bin\debug.  
  
3.  En segundo lugar, ejecute la aplicación EchoWorkflowClient generada en [directorio base de la solución] \EchoWorkflowClient\bin\debug.  
  
4.  El cliente llama a la operación Echo en el servicio e imprime los resultados. Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.