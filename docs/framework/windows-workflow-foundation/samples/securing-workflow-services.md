---
title: Proteger servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: 5dbd724f3a2f8febfc74719584f4d69cbf75b567
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806674"
---
# <a name="securing-workflow-services"></a>Proteger servicios de flujo de trabajo
En el ejemplo del servicio de flujo de trabajo seguro se muestran los siguientes procedimientos:  
  
-   Crear un servicio de flujo de trabajo básico mediante las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>.  
  
-   Usa la configuración de Windows Communication Foundation (WCF) para definir extremos seguros para su uso por el servicio de flujo de trabajo.  
  
-   Crear notificaciones dentro de una directiva personalizada y utilizar <xref:System.ServiceModel.ServiceAuthorizationManager> para validarlas.  
  
## <a name="demonstrates"></a>Demostraciones  
 Usar la seguridad WCF para proteger la comunicación entre el cliente y el servicio de flujo de trabajo, con autorización basada en notificaciones  
  
## <a name="discussion"></a>Explicación  
 Este ejemplo muestra el uso de la infraestructura de seguridad WCF para proteger un servicio de flujo de trabajo, tal como lo haría con un servicio WCF normal. Concretamente, usa una notificación personalizada para la autorización. En este caso, utiliza <xref:System.ServiceModel.WSHttpBinding> y la seguridad de modo de mensaje con credenciales de Windows.  
  
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
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
