---
title: Servicio de fachada confiable
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: 40264ee018d3c09d86e1bcd0b8cc96c0610219f9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711889"
---
# <a name="trusted-facade-service"></a>Servicio de fachada confiable
Este ejemplo de escenario muestra cómo fluir la información de identidad del llamador de un servicio a otro utilizando la infraestructura de seguridad de Windows Communication Foundation (WCF).  
  
 Es un patrón de diseño común para exponer la funcionalidad proporcionada por un servicio a la red pública utilizando un servicio de fachada. El servicio de fachada reside normalmente en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada) y se comunica con un servicio back-end que implementa la lógica comercial y tiene acceso a datos internos. El canal de comunicación entre el servicio de la fachada y el servicio back-end va a través de un firewall y se limita normalmente solo para un único propósito.  
  
 Este ejemplo consta de los siguientes componentes:  
  
- Cliente de la calculadora  
  
- Servicio de fachada de calculadora  
  
- Servicio back-end de calculadora.  
  
 El servicio de la fachada es responsable de validar la solicitud y autenticar el llamador. Después de la autenticación y validación correctas, reenvía la solicitud al servicio back-end utilizando el canal de comunicación controlado de la red perimetral a la red interna. Como parte de la solicitud reenviada, el servicio de fachada incluye información sobre la identidad del llamador para que el servicio back-end pueda utilizar esta información en su procesamiento. La identidad del llamador se transmite utilizando un token de seguridad `Username` dentro del encabezado `Security` del mensaje . El ejemplo utiliza la infraestructura de seguridad de WCF para transmitir y extraer esta información del encabezado `Security`.  
  
> [!IMPORTANT]
> El servicio back-end confia en el servicio de fachada para autenticar el llamador. Debido a esto, el servicio back-end no autentica de nuevo el llamador; utiliza la información de identidad proporcionada por el servicio de fachada en la solicitud reenviada. Debido a esta relación de confianza, el servicio back-end debe autenticar el servicio de fachada para asegurarse de que el mensaje reenviado procede de una fuente de confianza, en este caso el servicio de fachada.  
  
## <a name="implementation"></a>Implementación  
 Hay dos rutas de comunicación en este ejemplo. El primero se da entre el cliente y el servicio de fachada, el segundo entre el servicio de fachada y el servicio back-end.  
  
### <a name="communication-path-between-client-and-faade-service"></a>Ruta de acceso de comunicación entre Cliente y Servicio de Fachada  
 El cliente a la ruta de comunicación de servicio de fachada utiliza `wsHttpBinding` con un tipo de credencial de cliente `UserName` . Esto significa que el cliente utiliza nombre de usuario y contraseña para autenticarse al servicio de fachada y el servicio de fachada utiliza el certificado X.509 para autenticarse al cliente. El archivo de configuración de enlace se parece al siguiente ejemplo.:  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 El servicio de fachada autentica el llamador mediante la implementación `UserNamePasswordValidator` personalizada. Durante la demostración, la autenticación solo asegura que el nombre de usuario del llamador coincide con la contraseña presentada. En una situación real, el usuario se autentica probablemente utilizando Active Directory o el proveedor de suscripciones de ASP.NET personalizado. La implementación del validador reside en el archivo `FacadeService.cs` .  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 El validador personalizado se configura para ser utilizado dentro del comportamiento `serviceCredentials` en el archivo de configuración de servicio de fachada. Este comportamiento también se utiliza para configurar el certificado X.509 del servicio.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate   
               findValue="localhost"   
               storeLocation="LocalMachine"   
               storeName="My"   
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a>Ruta de acceso de comunicación entre el Servicio de Fachada y el Servicio Back-end  
 La ruta de comunicación entre el servicio de fachada y el servicio back-end utiliza `customBinding` que está compuesto por varios elementos de enlace. Este enlace logra dos cosas. Autentica el servicio de fachada y el servicio back-end para asegurar que la comunicación es segura y viene de una fuente de confianza. Además, también transmite la identidad del llamador inicial dentro del token de seguridad `Username` . En este caso, solo se transmite el nombre de usuario del llamador inicial al servicio back-end, la contraseña no está incluida en el mensaje. Esto es porque el servicio back-end confia en el servicio de fachada para autenticar el llamador antes de reenviar la solicitud a él. Dado que el servicio de fachada se autentica en el servicio back-end, el servicio back-end puede confiar en la información contenida en la solicitud reenviada.  
  
 A continuación, se muestra la configuración de enlace para esta ruta de comunicación.  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 El elemento de enlace de [> de seguridad de\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) se encarga de la transmisión y extracción del nombre de usuario del llamador inicial. Los [\<windowsStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md) y [\<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) se encargan de autenticar los servicios de fachada y back-end y la protección de mensajes.  
  
 Para reenviar la solicitud, la implementación del servicio de fachada debe proporcionar el nombre de usuario del llamador inicial para que la infraestructura de seguridad de WCF pueda colocarlo en el mensaje reenviado. El nombre de usuario del llamador inicial se proporciona en la implementación del servicio de fachada estableciéndolo en la propiedad `ClientCredentials` en la instancia del proxy de cliente que el servicio de fachada utiliza para comunicarse con el servicio back-end.  
  
 El código siguiente muestra cómo el método `GetCallerIdentity` se implementa en el servicio de fachada. Otros métodos utilizan el mismo patrón.  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 Como se muestra en el código anterior, la contraseña no se establece en la propiedad `ClientCredentials` , solo se establece el nombre de usuario. La infraestructura de seguridad de WCF crea un token de seguridad de nombre de usuario sin contraseña en este caso, que es exactamente lo que se necesita en este escenario.  
  
 En el servicio back-end, la información contenida en el token de seguridad del nombre de usuario se debe autenticar. De forma predeterminada, la seguridad de WCF intenta asignar el usuario a una cuenta de Windows con la contraseña proporcionada. En este caso, no hay ninguna contraseña proporcionada y no se exige al servicio back-end que autentique el nombre de usuario porque ya la realizó el servicio de fachada. Para implementar esta funcionalidad en WCF, se proporciona un `UserNamePasswordValidator` personalizado que solo exige que un nombre de usuario se especifique en el token y no realiza ninguna autenticación adicional.  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,   
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the   
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new   
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 El validador personalizado se configura para ser utilizado dentro del comportamiento `serviceCredentials` en el archivo de configuración de servicio de fachada.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,   
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Para extraer la información del nombre de usuario e información sobre la cuenta de servicio de fachada confiable, la implementación del servicio back-end utiliza la clase `ServiceSecurityContext` . El código siguiente muestra cómo se implementa el método `GetCallerIdentity` .  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =   
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on   
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in   
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets   
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in   
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&   
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject   
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 La información de cuenta de servicio de fachada se extrae utilizando la propiedad `ServiceSecurityContext.Current.WindowsIdentity` . Para tener acceso a la información sobre el llamador inicial el servicio back-end utiliza la propiedad `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` . Busca una notificación `Identity` con un tipo `Name`. Esta demanda se genera automáticamente mediante la infraestructura de seguridad de WCF a partir de la información contenida en el token de seguridad de `Username`.  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente. Puede presionar Entrar en las ventanas de la consola de servicio de fachada y back-end para cerrar los servicios.  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 El archivo por lotes Setup.bat incluido con el ejemplo de escenario de Fachada Confiable le permite configurar el servidor con un certificado pertinente para ejecutar el servicio de fachada que exige que la seguridad basada en certificado se autentique al cliente. Para obtener más detalles, vea el procedimiento de configuración al final de este tema.  
  
 A continuación se proporciona una información general breve de las diferentes secciones de los archivos por lotes.  
  
- Crear el certificado de servidor.  
  
     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     La variable `%SERVER_NAME%` especifica el nombre del servidor; el valor predeterminado es el host local. El certificado se almacena en el almacén LocalMachine.  
  
- Instalar el certificado del servicio de fachada en el almacén de certificados de confianza de cliente.  
  
     La línea siguiente copia el certificado del servicio de fachada en el almacén de personas de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a>Para ejecutar el ejemplo en el mismo equipo  
  
1. Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentra Makecert.exe.  
  
2. Ejecute Setup.bat desde la carpeta de instalación del ejemplo. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.  
  
3. Inicie BackendService.exe desde el directorio \BackendService\bin en una ventana de la consola independiente  
  
4. Inicie FacadeService.exe desde el directorio \FacadeService\bin en una ventana de la consola independiente  
  
5. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
6. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
1. Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`  
