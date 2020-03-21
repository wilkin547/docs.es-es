---
title: Autorización de acceso a operaciones de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: c2ad6977674666ef65df1ea4cfe58cfd4bff8b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183924"
---
# <a name="authorizing-access-to-service-operations"></a><span data-ttu-id="44b5f-102">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="44b5f-102">Authorizing Access to Service Operations</span></span>
<span data-ttu-id="44b5f-103">En este ejemplo se muestra cómo usar el <xref:System.Security.Permissions.PrincipalPermissionAttribute> [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) para habilitar el uso del atributo para autorizar el acceso a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="44b5f-103">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span> <span data-ttu-id="44b5f-104">Este ejemplo se basa en el ejemplo [de introducción.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="44b5f-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) sample.</span></span> <span data-ttu-id="44b5f-105">El servicio y el cliente se configuran mediante [ \<el>wsHttpBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="44b5f-105">The service and client are configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="44b5f-106">El `mode` atributo del>de `Message` [ \<seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) se ha establecido en y `clientCredentialType` se ha establecido en `Windows`.</span><span class="sxs-lookup"><span data-stu-id="44b5f-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="44b5f-107"><xref:System.Security.Permissions.PrincipalPermissionAttribute> se aplica a cada método de servicio y restringe el acceso a cada operación.</span><span class="sxs-lookup"><span data-stu-id="44b5f-107">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each service method and used to restrict access to each operation.</span></span> <span data-ttu-id="44b5f-108">El llamador debe ser un administrador de Windows para tener acceso a cada operación.</span><span class="sxs-lookup"><span data-stu-id="44b5f-108">The caller must be a Windows administrator to access each operation.</span></span>  
  
 <span data-ttu-id="44b5f-109">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="44b5f-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44b5f-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="44b5f-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="44b5f-111">El archivo de configuración del servicio `principalPermissionMode` utiliza el [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) para establecer el atributo:</span><span class="sxs-lookup"><span data-stu-id="44b5f-111">The service configuration file uses the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to set the `principalPermissionMode` attribute:</span></span>  
  
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
  
 <span data-ttu-id="44b5f-112">Establecer `principalPermissionMode` en `UseWindowsGroups` habilita el uso de <xref:System.Security.Permissions.PrincipalPermissionAttribute> basado en nombres del grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="44b5f-112">Setting the `principalPermissionMode` to `UseWindowsGroups` enables the use of <xref:System.Security.Permissions.PrincipalPermissionAttribute> based on Windows group names.</span></span>  
  
 <span data-ttu-id="44b5f-113"><xref:System.Security.Permissions.PrincipalPermissionAttribute> se aplica a cada operación para exigir al llamador que forme parte del grupo de administradores de Windows, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="44b5f-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each operation to require the caller to be part of the Windows administrators group, as shown in the following sample code.</span></span>  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 <span data-ttu-id="44b5f-114">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="44b5f-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="44b5f-115">El cliente se comunica correctamente con cada operación si se está ejecutando bajo una cuenta que forme parte del grupo Administradores; de lo contrario, se deniega el acceso.</span><span class="sxs-lookup"><span data-stu-id="44b5f-115">The client successfully communicates with each operation if it is running under an account that is part of the Administrators group; otherwise, access is denied.</span></span> <span data-ttu-id="44b5f-116">Para experimentar con un error de autorización, ejecute el cliente con una cuenta que no forme parte del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="44b5f-116">To experiment with authorization failure, run the client under an account that is not part of the Administrators group.</span></span> <span data-ttu-id="44b5f-117">Presione ENTRAR en la ventana de la consola para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="44b5f-117">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="44b5f-118">Se puede notificar un servicio de los errores de autorización implementando <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="44b5f-118">A service can be notified of authorization failures by implementing an <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span></span> <span data-ttu-id="44b5f-119">Consulte [Ampliación del control sobre el control de](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) errores y los informes para obtener información sobre la implementación `IErrorHandler`de archivos .</span><span class="sxs-lookup"><span data-stu-id="44b5f-119">See [Extending Control Over Error Handling and Reporting](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) for information about implementing `IErrorHandler`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="44b5f-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="44b5f-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="44b5f-121">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="44b5f-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="44b5f-122">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="44b5f-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="44b5f-123">Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="44b5f-123">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
