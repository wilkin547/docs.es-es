---
title: Autorización de acceso a operaciones de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: a0ea82c876b3bd8c2a3218f84399fbb69e1d0080
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932496"
---
# <a name="authorizing-access-to-service-operations"></a>Autorización de acceso a operaciones de servicio
Este ejemplo muestra cómo utilizar el [ \<> serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) para habilitar el uso del atributo <xref:System.Security.Permissions.PrincipalPermissionAttribute> para autorizar el acceso a las operaciones de servicio. Este ejemplo se basa en el ejemplo [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) . El servicio y el cliente se configuran mediante el [ \<> wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). El `mode` `Message` atributo `Windows` `clientCredentialType` [ del>deseguridadsehaestablecidoenysehaestablecidoen.\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) <xref:System.Security.Permissions.PrincipalPermissionAttribute> se aplica a cada método de servicio y restringe el acceso a cada operación. El llamador debe ser un administrador de Windows para tener acceso a cada operación.  
  
 En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El archivo de configuración de servicio utiliza el [ \<> serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) para `principalPermissionMode` establecer el atributo:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Establecer `principalPermissionMode` en `UseWindowsGroups` habilita el uso de <xref:System.Security.Permissions.PrincipalPermissionAttribute> basado en nombres del grupo de Windows.  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> se aplica a cada operación para exigir al llamador que forme parte del grupo de administradores de Windows, como se muestra en el siguiente código de ejemplo.  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. El cliente se comunica correctamente con cada operación si se está ejecutando bajo una cuenta que forme parte del grupo Administradores; de lo contrario, se deniega el acceso. Para experimentar con un error de autorización, ejecute el cliente con una cuenta que no forme parte del grupo Administradores. Presione ENTRAR en la ventana de la consola para cerrar el cliente.  
  
 Se puede notificar un servicio de los errores de autorización implementando <xref:System.ServiceModel.Dispatcher.IErrorHandler>. Vea [extender el control sobre](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) el control de errores y los informes `IErrorHandler`para obtener información sobre la implementación de.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
