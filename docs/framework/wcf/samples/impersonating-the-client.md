---
title: "Suplantar el cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ejemplo de suplantación de cliente [Windows Communication Foundation]"
  - "suplantación, Ejemplo de Windows Communication Foundation"
  - "comportamientos del servicio, ejemplo de suplantación"
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Suplantar el cliente
El ejemplo de Suplantación muestra cómo suplantar la aplicación de llamador en el servicio para que el servicio pueda tener acceso a los recursos del sistema en nombre del llamador.  
  
 Este ejemplo se basa en el ejemplo [Autohospedaje](../../../../docs/framework/wcf/samples/self-host.md).Los archivos de configuración de cliente y servicio son igual que los del ejemplo [Autohospedaje](../../../../docs/framework/wcf/samples/self-host.md).  
  
> [!NOTE]
>  El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El código del servicio se ha modificado de tal modo que el método `Add` en el servicio suplanta al llamador mediante <xref:System.ServiceModel.OperationBehaviorAttribute> como se muestra en el código muestra siguiente.  
  
```  
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
  
```  
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
  
```  
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
  
 Tenga en cuenta que en este caso que el llamador no se suplanta para la llamada completa, sino que sólo se suplanta para una parte de la llamada.En general, la suplantación para el ámbito más pequeño es preferible a la suplantación para la operación completa.  
  
 Los otros métodos no suplantan al llamador.  
  
 El código de cliente se ha modificado para establecer el nivel de suplantación en <xref:System.Security.Principal.TokenImpersonationLevel>.El cliente especifica el nivel de suplantación que el servicio va a utilizar, mediante la enumeración <xref:System.Security.Principal.TokenImpersonationLevel>.La enumeración admite los valores siguientes: <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel>, <xref:System.Security.Principal.TokenImpersonationLevel> y <xref:System.Security.Principal.TokenImpersonationLevel>.Para realizar una comprobación de acceso al tener acceso a un recurso del sistema en el equipo local que se protege utilizando ACL de Windows, el nivel de suplantación debe estar establecido en <xref:System.Security.Principal.TokenImpersonationLevel>, como se muestra en el código muestra siguiente.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 Al ejecutar el ejemplo, las solicitudes de la operación y las respuestas se muestran en las ventanas de la consola del cliente y del servicio.Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
> [!NOTE]
>  El servicio se debe ejecutar o bajo una cuenta administrativa, o a la cuenta bajo la que ejecuta se le debe conceder derechos para registrar el URI del http:\/\/localhost:8000\/ServiceModelSamples con la capa del HTTP.Tales derechos se pueden permitir preparando una [Reserva de espacio de nombres](http://go.microsoft.com/fwlink/?LinkId=95012) mediante la herramienta [Httpcfg.exe](http://go.microsoft.com/fwlink/?LinkId=95010).  
  
> [!NOTE]
>  En los equipos que ejecutan [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], la suplantación se admite sólo si la aplicación Host.exe tiene el privilegio de Suplantación.\(De forma predeterminada, sólo los administradores tienen este permiso.\) Para agregar este privilegio a una cuenta como la que el servicio está suplantando, vaya a **Herramientas administrativas**, abra **Directiva de seguridad local**, abra **Directivas locales**, haga clic en **Asignación de derechos de usuario**y seleccione **Suplantar a un cliente tras la autenticación** y haga doble clic en **Propiedades** para agregar un usuario o grupo.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4.  Para mostrar que el servicio suplanta al llamador, ejecute el cliente bajo una cuenta diferente de aquella bajo la cual el servicio se está ejecutando.Para realizar esta operación, en el símbolo del sistema, escriba:  
  
    ```  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     Se solicita a continuación una contraseña.Escriba previamente la contraseña para la cuenta que especificó.  
  
5.  Al ejecutar el cliente, tenga en cuenta la identidad de antes y de después de ejecutarlo con credenciales diferentes.  
  
## Vea también