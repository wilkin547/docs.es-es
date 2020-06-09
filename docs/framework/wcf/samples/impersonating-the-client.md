---
title: Suplantar el cliente
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: b5272d8b4dbac60e14fe87accbb08a2073ed65ab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594639"
---
# <a name="impersonating-the-client"></a>Suplantar el cliente
El ejemplo de Suplantación muestra cómo suplantar la aplicación de llamador en el servicio para que el servicio pueda tener acceso a los recursos del sistema en nombre del llamador.  
  
 Este ejemplo se basa en el ejemplo de [host propio](self-host.md) . Los archivos de configuración de servicio y de cliente son los mismos que los del ejemplo de [host propio](self-host.md) .  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El código del servicio se ha modificado de tal modo que el método `Add` en el servicio suplanta al llamador mediante <xref:System.ServiceModel.OperationBehaviorAttribute> como se muestra en el código muestra siguiente.  
  
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
  
 Como resultado, el contexto de seguridad del subproceso que se está ejecutando se intercambia para suplantar al llamador antes de entrar al método `Add` y revierte en la salida del método.  
  
 El método `DisplayIdentityInformation` mostrado en el código muestra siguiente es una función de utilidad que muestra la identidad del llamador.  
  
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
  
 El método `Subtract` en el servicio suplanta al llamador utilizando las llamadas imperativas, tal y como se muestra en el código muestra siguiente.  
  
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
  
 Tenga en cuenta que en este caso que el llamador no se suplanta para la llamada completa, sino que sólo se suplanta para una parte de la llamada. En general, la suplantación para el ámbito más pequeño es preferible a la suplantación para la operación completa.  
  
 Los otros métodos no suplantan al llamador.  
  
 El código de cliente se ha modificado para establecer el nivel de suplantación en <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>. El cliente especifica el nivel de suplantación que el servicio va a utilizar, mediante la enumeración <xref:System.Security.Principal.TokenImpersonationLevel>. La enumeración admite los valores siguientes: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> y <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. Para realizar una comprobación de acceso al tener acceso a un recurso del sistema en el equipo local que se protege utilizando ACL de Windows, el nivel de suplantación debe estar establecido en <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, como se muestra en el código muestra siguiente.  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
> [!NOTE]
> El servicio debe ejecutarse en una cuenta administrativa o la cuenta con la que se ejecuta debe tener derechos para registrar el `http://localhost:8000/ServiceModelSamples` URI con el nivel http. Estos derechos se pueden conceder mediante la configuración de una [reserva de espacio de nombres](/windows/win32/http/namespace-reservations-registrations-and-routing) mediante la [herramienta Httpcfg. exe](/windows/win32/http/httpcfg-exe).  
  
> [!NOTE]
> En los equipos que ejecutan Windows Server 2003, la suplantación solo se admite si la aplicación host. exe tiene el privilegio de suplantación. (De forma predeterminada, solo los administradores tienen este permiso). Para agregar este privilegio a una cuenta en la que se está ejecutando el servicio, vaya a **herramientas administrativas**, Abra **Directiva de seguridad local**, Abra **Directivas locales**, haga clic en **asignación de derechos de usuario**y seleccione **Suplantar a un cliente tras la autenticación** y haga doble clic en **propiedades** para agregar un usuario o grupo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
4. Para mostrar que el servicio suplanta al llamador, ejecute el cliente bajo una cuenta diferente de aquella bajo la cual el servicio se está ejecutando. Para realizar esta operación, en el símbolo del sistema, escriba:  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     Se solicita a continuación una contraseña. Escriba previamente la contraseña para la cuenta que especificó.  
  
5. Al ejecutar el cliente, tenga en cuenta la identidad de antes y de después de ejecutarlo con credenciales diferentes.  
