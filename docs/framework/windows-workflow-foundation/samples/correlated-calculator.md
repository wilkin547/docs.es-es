---
title: Calculadora correlacionada
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0578553b644fd3fa3883ea9040a7daf80117866
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="correlated-calculator"></a>Calculadora correlacionada
En este ejemplo se muestra cómo utilizar las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>) en el diseñador con correlación basada en contenidos en función de un parámetro en el mensaje. En este escenario, las operaciones de la calculadora se encuentran en un convoy paralelo. Se crean una instancia y una correlación (basadas en `CalculatorId`) cuando el primer mensaje se envía al flujo de trabajo, y los mensajes subsiguientes con el mismo `CalculatorId` se envían a esa instancia hasta que se llama a la operación de restablecimiento. El cliente se implementa como una aplicación WPF que utiliza un proxy de cliente basado en código para comunicarse con el servicio.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Inicie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados y abra el archivo de solución For.sln.  
  
    1.  Navegue hasta la carpeta que contiene [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Haga clic en Devenv.exe y seleccione **ejecutar como administrador**.  
  
2.  Abra el archivo de solución de CorrelatedCalculator.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
4.  Presione CTRL+F5 para ejecutar el proyecto de servicio.  
  
5.  Cuando el servicio está listo y realizando escuchas para los mensajes, en el Explorador de soluciones, haga clic con el botón secundario en el proyecto Cliente y ejecútelo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`