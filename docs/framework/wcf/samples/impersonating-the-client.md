---
description: Más información acerca de la suplantación del cliente
title: Suplantar el cliente
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: cab6f342a572d357f6987f60218ef2682bedd447
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631767"
---
# <a name="impersonating-the-client"></a><span data-ttu-id="13a1d-103">Suplantar el cliente</span><span class="sxs-lookup"><span data-stu-id="13a1d-103">Impersonating the Client</span></span>

<span data-ttu-id="13a1d-104">El ejemplo de Suplantación muestra cómo suplantar la aplicación de llamador en el servicio para que el servicio pueda tener acceso a los recursos del sistema en nombre del llamador.</span><span class="sxs-lookup"><span data-stu-id="13a1d-104">The Impersonation sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>  
  
 <span data-ttu-id="13a1d-105">Este ejemplo se basa en el ejemplo de [host propio](self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="13a1d-105">This sample is based on the [Self-Host](self-host.md) sample.</span></span> <span data-ttu-id="13a1d-106">Los archivos de configuración de servicio y de cliente son los mismos que los del ejemplo de [host propio](self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="13a1d-106">The service and client configuration files are the same as that of the [Self-Host](self-host.md) sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13a1d-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="13a1d-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="13a1d-108">El código del servicio se ha modificado de tal modo que el método `Add` en el servicio suplanta al llamador mediante <xref:System.ServiceModel.OperationBehaviorAttribute> como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="13a1d-108">The service code has been modified such that the `Add` method on the service impersonates the caller using the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="13a1d-109">Como resultado, el contexto de seguridad del subproceso que se está ejecutando se intercambia para suplantar al llamador antes de entrar al método `Add` y revierte en la salida del método.</span><span class="sxs-lookup"><span data-stu-id="13a1d-109">As a result, the security context of the executing thread is switched to impersonate the caller before entering the `Add` method and reverted on exiting the method.</span></span>  
  
 <span data-ttu-id="13a1d-110">El método `DisplayIdentityInformation` mostrado en el código muestra siguiente es una función de utilidad que muestra la identidad del llamador.</span><span class="sxs-lookup"><span data-stu-id="13a1d-110">The `DisplayIdentityInformation` method shown in the following sample code is a utility function that displays the caller's identity.</span></span>  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 <span data-ttu-id="13a1d-111">El método `Subtract` en el servicio suplanta al llamador utilizando las llamadas imperativas, tal y como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="13a1d-111">The `Subtract` method on the service impersonates the caller using imperative calls as shown in the following sample code.</span></span>  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs
            // on the system resource are enforced in the caller's context.
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="13a1d-112">Tenga en cuenta que en este caso que el llamador no se suplanta para la llamada completa, sino que sólo se suplanta para una parte de la llamada.</span><span class="sxs-lookup"><span data-stu-id="13a1d-112">Note that in this case the caller is not impersonated for the entire call but is only impersonated for a portion of the call.</span></span> <span data-ttu-id="13a1d-113">En general, la suplantación para el ámbito más pequeño es preferible a la suplantación para la operación completa.</span><span class="sxs-lookup"><span data-stu-id="13a1d-113">In general, impersonating for the smallest scope is preferable to impersonating for the entire operation.</span></span>  
  
 <span data-ttu-id="13a1d-114">Los otros métodos no suplantan al llamador.</span><span class="sxs-lookup"><span data-stu-id="13a1d-114">The other methods do not impersonate the caller.</span></span>  
  
 <span data-ttu-id="13a1d-115">El código de cliente se ha modificado para establecer el nivel de suplantación en <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span><span class="sxs-lookup"><span data-stu-id="13a1d-115">The client code has been modified to set the impersonation level to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span></span> <span data-ttu-id="13a1d-116">El cliente especifica el nivel de suplantación que el servicio va a utilizar, mediante la enumeración <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="13a1d-116">The client specifies the impersonation level to be used by the service, by using the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration.</span></span> <span data-ttu-id="13a1d-117">La enumeración admite los valores siguientes: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> y <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span><span class="sxs-lookup"><span data-stu-id="13a1d-117">The enumeration supports the following values: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> and <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span> <span data-ttu-id="13a1d-118">Para realizar una comprobación de acceso al tener acceso a un recurso del sistema en el equipo local que se protege utilizando ACL de Windows, el nivel de suplantación debe estar establecido en <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="13a1d-118">To perform an access check when accessing a system resource on the local machine that is protected using Windows ACLs, the impersonation level must be set to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, as shown in the following sample code.</span></span>  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 <span data-ttu-id="13a1d-119">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="13a1d-119">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="13a1d-120">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="13a1d-120">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13a1d-121">El servicio debe ejecutarse en una cuenta administrativa o la cuenta con la que se ejecuta debe tener derechos para registrar el `http://localhost:8000/ServiceModelSamples` URI con el nivel http.</span><span class="sxs-lookup"><span data-stu-id="13a1d-121">The service must either run under an administrative account or the account it runs under must be granted rights to register the `http://localhost:8000/ServiceModelSamples` URI with the HTTP layer.</span></span> <span data-ttu-id="13a1d-122">Estos derechos se pueden conceder mediante la configuración de una [reserva de espacio de nombres](/windows/win32/http/namespace-reservations-registrations-and-routing) mediante la [ herramientaHttpcfg.exe](/windows/win32/http/httpcfg-exe).</span><span class="sxs-lookup"><span data-stu-id="13a1d-122">Such rights can be granted by setting up a [Namespace Reservation](/windows/win32/http/namespace-reservations-registrations-and-routing) using the [Httpcfg.exe tool](/windows/win32/http/httpcfg-exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13a1d-123">En los equipos que ejecutan Windows Server 2003, la suplantación solo se admite si la aplicación Host.exe tiene el privilegio de suplantación.</span><span class="sxs-lookup"><span data-stu-id="13a1d-123">On computers running Windows Server 2003, impersonation is supported only if the Host.exe application has the Impersonation privilege.</span></span> <span data-ttu-id="13a1d-124">(De forma predeterminada, solo los administradores tienen este permiso). Para agregar este privilegio a una cuenta en la que se está ejecutando el servicio, vaya a **herramientas administrativas**, Abra **Directiva de seguridad local**, Abra **Directivas locales**, haga clic en **asignación de derechos de usuario** y seleccione **Suplantar a un cliente tras la autenticación** y haga doble clic en **propiedades** para agregar un usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="13a1d-124">(By default, only administrators have this permission.) To add this privilege to an account the service is running as, go to **Administrative Tools**, open **Local Security Policy**, open **Local Policies**, click **User Rights Assignment**, and select **Impersonate a Client after Authentication** and double-click **Properties** to add a user or group.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="13a1d-125">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="13a1d-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="13a1d-126">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13a1d-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="13a1d-127">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13a1d-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="13a1d-128">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13a1d-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="13a1d-129">Para mostrar que el servicio suplanta al llamador, ejecute el cliente bajo una cuenta diferente de aquella bajo la cual el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="13a1d-129">To demonstrate that the service impersonates the caller, run the client under a different account than the one the service is running under.</span></span> <span data-ttu-id="13a1d-130">Para realizar esta operación, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="13a1d-130">To do so, at the command prompt, type:</span></span>  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     <span data-ttu-id="13a1d-131">Se solicita a continuación una contraseña.</span><span class="sxs-lookup"><span data-stu-id="13a1d-131">You are then prompted for a password.</span></span> <span data-ttu-id="13a1d-132">Escriba previamente la contraseña para la cuenta que especificó.</span><span class="sxs-lookup"><span data-stu-id="13a1d-132">Enter the password for the account you previously specified.</span></span>  
  
5. <span data-ttu-id="13a1d-133">Al ejecutar el cliente, tenga en cuenta la identidad de antes y de después de ejecutarlo con credenciales diferentes.</span><span class="sxs-lookup"><span data-stu-id="13a1d-133">When you run the client, note the identity before and after running it with different credentials.</span></span>  
