---
title: Envío y control de errores
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 896f209e7daeeab2bb33c1fde15298aae96c8776
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037716"
---
# <a name="sending-and-handling-faults"></a>Envío y control de errores
En este ejemplo se muestra cómo utilizar las actividades de mensajería <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply> para enviar y recibir errores esperados e inesperados. En este escenario, la primera solicitud de cliente genera un error esperado que se ha incluido en su colección <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>. Las siguientes solicitudes de cliente producen la recepción de errores inesperados, antes de que la solicitud final se realice correctamente.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.  
  
2.  Abra el archivo de solución Faults.sln.  
  
3.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
4.  Ejecute el proyecto de servicio.  
  
    1.  En **el Explorador de soluciones**, haga clic en el `FaultService` del proyecto y seleccione **establecer como proyecto de inicio**.  
  
    2.  Presione CTRL+F5.  
  
5.  Abra otra copia del [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.  
  
6.  Abra el archivo de solución Faults.sln.  
  
7.  Ejecute el proyecto de cliente.  
  
    1.  En **el Explorador de soluciones**, haga clic en el `FaultClient` del proyecto y seleccione **establecer como proyecto de inicio**.  
  
    2.  Presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`