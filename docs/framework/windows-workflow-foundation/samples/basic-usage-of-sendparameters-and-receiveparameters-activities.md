---
title: Uso básico de las actividades SendParameters y ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: 8732b10f3f96ccf9ed352f9b54c60a4ee0d1664c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515403"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Uso básico de las actividades SendParameters y ReceiveParameters
En este ejemplo se muestra el uso de las actividades <xref:System.ServiceModel.Activities.SendParametersContent> y <xref:System.ServiceModel.Activities.ReceiveParametersContent>. El servicio expone una operación que toma un argumento de cadena y devuelve la entrada al cliente. En el ejemplo se muestra cómo preparar los parámetros para estas actividades de mensajería.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  Primero, ejecute la aplicación EchoWorkflowService generada en [directorio base de la solución]\EchoWorkflowService\bin\debug.  
  
3.  En segundo lugar, ejecute la aplicación EchoWorkflowClient generada en [directorio base de la solución] \EchoWorkflowClient\bin\debug.  
  
4.  El cliente llama a la operación Echo en el servicio e imprime los resultados. Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.