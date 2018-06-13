---
title: Ejemplo de punto de conexión de administración de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: e34a23f76edbd957b1be7caff1b18f6934b1588b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517104"
---
# <a name="workflow-management-endpoint-sample"></a>Ejemplo de punto de conexión de administración de flujo de trabajo
En este ejemplo se muestra cómo un punto de conexión de control de flujo de trabajo se puede utilizar para crear y ejecutar flujos de trabajo de forma local y remota. En el ejemplo se muestra cómo hospedar un extremo de control y cómo escribir clientes que llamen al extremo de control para crear y ejecutar la instancia de un flujo de trabajo. El flujo de trabajo no es un servicio.  
  
 En el lado del servicio del ejemplo un flujo de trabajo se hospeda con WorkflowServiceHost y se agrega un WorkflowControlEndpoint de modo que los clientes puedan realizar operaciones de control (Suspend, Start, etc.). También se agrega un CreationEndpoint definido por el usuario para permitir la creación del flujo de trabajo. El servicio usará posteriormente estos extremos para iniciar el flujo de trabajo en un estado suspendido y después reanudar el flujo de trabajo. El cliente realiza las mismas operaciones pero desde el código de cliente. Para obtener más información acerca de estas interfaces, vea [extremo de Control de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) y [Cómo: hospedar un flujo de trabajo no pertenecientes al servicio en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegios de administrador.  
  
2.  Abra la solución ManagementEndpoint.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **generar solución** desde el **generar** menú.  
  
4.  Inicie la aplicación ManagementEndpoint.exe.  
  
5.  Inicie la aplicación Client.exe.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`