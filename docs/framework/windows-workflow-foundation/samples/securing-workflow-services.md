---
title: Proteger servicios de flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cd7620186ed51110a32e251d5239c85bb90e0f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="securing-workflow-services"></a>Proteger servicios de flujo de trabajo
En el ejemplo del servicio de flujo de trabajo seguro se muestran los siguientes procedimientos:  
  
-   Crear un servicio de flujo de trabajo básico mediante las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>.  
  
-   Utilizar la configuración de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para definir extremos seguros para que los use el servicio de flujo de trabajo.  
  
-   Crear notificaciones dentro de una directiva personalizada y utilizar <xref:System.ServiceModel.ServiceAuthorizationManager> para validarlas.  
  
## <a name="demonstrates"></a>Demostraciones  
 Usar la seguridad WCF para proteger la comunicación entre el cliente y el servicio de flujo de trabajo, con autorización basada en notificaciones  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra el uso de la infraestructura de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para proteger un servicio de flujo de trabajo de la misma manera que se haría con un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] normal. Concretamente, usa una notificación personalizada para la autorización. En este caso, utiliza <xref:System.ServiceModel.WSHttpBinding> y la seguridad de modo de mensaje con credenciales de Windows.  
  
 La interfaz <xref:System.IdentityModel.Policy.IAuthorizationPolicy> personalizada (`CustomNameCheckerPolicy`) comprueba el nombre de usuario de Windows del cliente y busca un carácter concreto. Si ese carácter está presente, crea y agrega la notificación a la clase <xref:System.IdentityModel.Policy.EvaluationContext>. Al llevar esto a cabo, la directiva personalizada indica que el cliente tiene este carácter en el nombre de usuario. Esta notificación se puede consultar mientras dura la llamada. Puede encontrar el carácter en `Constants.cs`.  
  
 La directiva de autorización busca la notificación dentro de `SecureWorkFlowAuthZManager`. Si la encuentra, devuelve `true` y permite que el flujo de trabajo continúe. De lo contrario, devuelve `false`, lo que produce que se devuelva un mensaje de acceso denegado al cliente. En el contexto hay otras notificaciones, que también se pueden examinar dentro de `SecureWorkFlowAuthZManager`.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar este ejemplo  
  
1.  Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegios de administrador.  
  
2.  Cargue SecuringWorkflowServices.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
4.  Establezca el proyecto Service como proyecto de inicio para la solución.  
  
5.  Para iniciar el servicio sin depurar, presione CTRL+F5.  
  
6.  Establezca el proyecto Client como proyecto de inicio para la solución.  
  
7.  Para iniciar el cliente sin depurar, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
