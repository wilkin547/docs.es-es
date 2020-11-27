---
title: Proveedor de tokens
ms.date: 03/30/2017
ms.assetid: 947986cf-9946-4987-84e5-a14678d96edb
ms.openlocfilehash: e761f32ab26cf620b6ef1dddff2bcba53289af84
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262338"
---
# <a name="token-provider"></a>Proveedor de tokens

Este ejemplo muestra cómo implementar un proveedor de tokens personalizado. Un proveedor de tokens en Windows Communication Foundation (WCF) se usa para proporcionar credenciales a la infraestructura de seguridad. En general, el proveedor de tokens examina el destino y emite las credenciales adecuadas de manera que la infraestructura de seguridad pueda proteger el mensaje. WCF se suministra con el proveedor de tokens del administrador de credenciales predeterminado. WCF también se suministra con un proveedor de tokens de CardSpace. Los proveedores de tokens personalizados son útiles en los casos siguientes:

- Si tiene un almacén de credenciales con el que estos proveedores de tokens no pueden funcionar.

- Si desea proporcionar su propio mecanismo personalizado para transformar las credenciales desde el punto en el que el usuario proporciona detalles cuando el marco de trabajo de cliente de WCF usa las credenciales.

- Si está creando un token personalizado.

 Este ejemplo muestra cómo crear un proveedor de tokens personalizado que transforma la entrada del usuario a un formato diferente.

 En resumen, este ejemplo muestra lo siguiente:

- Cómo un cliente puede autenticar utilizando un par de nombre de usuario y contraseña.

- Cómo se puede configurar un cliente con un proveedor de tokens personalizado.

- Cómo el servidor puede validar las credenciales del cliente utilizando una contraseña con un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizado que valida que el nombre de usuario y la contraseña coinciden.

- Cómo el cliente autentica el servidor usando el certificado X.509 del servidor.

 Este ejemplo también muestra cómo la identidad del llamador es accesible después del proceso de autenticación del token personalizado.

 El servicio expone un extremo único para comunicarse con el servicio, definido mediante el archivo de configuración App.config. El punto de conexión está compuesto por una dirección, un enlace y un contrato. El enlace se configura con un `wsHttpBinding` estándar, que usa la seguridad de mensaje de forma predeterminada. Este ejemplo establece el `wsHttpBinding` estándar para utilizar la autenticación mediante el nombre de usuario del cliente. El servicio también configura el certificado del servicio utilizando el comportamiento serviceCredentials. El comportamiento serviceCredentials le permite configurar un certificado de servicio. Un cliente utiliza un certificado de servicio para autenticar el servicio y proporcionar protección al mensaje. La configuración siguiente hace referencia al certificado del host local instalado durante la configuración del ejemplo tal y como se describe en las siguientes instrucciones de configuración.

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service"/>
          </baseAddresses>
        </host>
        <!-- use base address provided by host -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults="False" />
          <!--
        The serviceCredentials behavior allows one to define a service certificate.
        A service certificate is used by a client to authenticate the service and provide message protection.
        This configuration references the "localhost" certificate installed during the setup instructions.
        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
```

 La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato. El enlace del cliente se configura con el adecuado `Mode` y `clientCredentialType`del mensaje.

```xml
<system.serviceModel>
  <client>
    <endpoint name=""
              address="http://localhost:8000/servicemodelsamples/service"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              contract="Microsoft.ServiceModel.Samples.ICalculator">
    </endpoint>
  </client>

  <bindings>
    <wsHttpBinding>
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>
</system.serviceModel>
```

 En los pasos siguientes se muestra cómo desarrollar un proveedor de tokens personalizado e integrarlo con el marco de seguridad de WCF:

1. Escriba un proveedor de tokens personalizado.

     El ejemplo implementa un proveedor de tokens personalizado que obtiene el nombre de usuario y contraseña. La contraseña debe coincidir con este nombre de usuario. Este proveedor de tokens personalizado solo tiene propósitos de muestra y no se recomienda para una implementación real.

     Para realizar esta tarea, el proveedor de tokens personalizado deriva la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>. Este método crea y devuelve un nuevo `UserNameSecurityToken`.

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
        // obtain username and password from the user using console window
        string username = GetUserName();
        string password = GetPassword();
        Console.WriteLine("username: {0}", username);

        // return new UserNameSecurityToken containing information obtained from user
        return new UserNameSecurityToken(username, password);
    }
    ```

2. Escribir el administrador de tokens de seguridad personalizado.

     <xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear <xref:System.IdentityModel.Selectors.SecurityTokenProvider> para el <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concreto que se pasa en el método `CreateSecurityTokenProvider`. El administrador de tokens de seguridad también se utiliza para crear autenticadores de tokens y serializadores de tokens, aunque en este ejemplo no se explica. En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenProvider` para devolver el proveedor de tokens de nombre de usuario personalizado cuando los requisitos de tokens pasados indican que se solicita un proveedor de nombre de usuario.

    ```csharp
    public class MyUserNameSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        MyUserNameClientCredentials myUserNameClientCredentials;

        public MyUserNameSecurityTokenManager(MyUserNameClientCredentials myUserNameClientCredentials)
            : base(myUserNameClientCredentials)
        {
            this.myUserNameClientCredentials = myUserNameClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // if token requirement matches username token return custom username token provider
            // otherwise use base implementation
            if (tokenRequirement.TokenType == SecurityTokenTypes.UserName)
            {
                return new MyUserNameTokenProvider();
            }
            else
            {
                return base.CreateSecurityTokenProvider(tokenRequirement);
            }
        }
    }
    ```

3. Escribir una credencial de cliente personalizada.

     Se usa una clase de credenciales de cliente para representar las credenciales que se configuran para el proxy de cliente y crear el administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y un serializador de tokens.

    ```csharp
    public class MyUserNameClientCredentials : ClientCredentials
    {
        public MyUserNameClientCredentials()
            : base()
        {
        }

        protected override ClientCredentials CloneCore()
        {
            return new MyUserNameClientCredentials();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            // return custom security token manager
            return new MyUserNameSecurityTokenManager(this);
        }
    }
    ```

4. Configure el cliente para utilizar la credencial del cliente personalizada.

     Para que el cliente utilice la credencial de cliente personalizada, el ejemplo elimina la clase de credencial de cliente predeterminada y proporciona la nueva.

    ```csharp
    static void Main()
    {
        // ...
           // Create a client with given client endpoint configuration
          CalculatorClient client = new CalculatorClient();

          // set new credentials
           client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
         client.ChannelFactory.Endpoint.Behaviors.Add(new MyUserNameClientCredentials());
       // ...
    }
    ```

 En el servicio, para mostrar la información del llamador, utilice como se muestra <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> en el ejemplo de código siguiente. <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene información de las notificaciones sobre el llamador actual.

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
        ServiceSecurityContext.Current.PrimaryIdentity.Name);
}
```

 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes

 El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con el certificado pertinente para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado de servidor. Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.

 A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar para su ejecución en la configuración adecuada:

- Crear el certificado de servidor.

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar. La variable `%SERVER_NAME%`especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado en este archivo por lotes es el host local.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del servidor en el almacén de certificados de confianza de cliente:

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

> [!NOTE]
> El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK. Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.

#### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 abierto con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.  
  
2. Inicie service.exe desde \service\bin.  
  
3. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
4. Cuando se pida el nombre de usuario, escriba un nombre de usuario.  
  
5. Cuando se pida la contraseña, utilice la misma cadena que escribió cuando se solicitó el nombre de usuario.  
  
6. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Cree un directorio en el equipo del servicio para los binarios del servicio.  
  
2. Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3. Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo. El archivo Service.exe.config debe actualizarse para reflejar este nuevo nombre de certificado. Puede crear el certificado de servidor modificando el archivo por lotes Setup.bat. Tenga en cuenta que el archivo de setup.bat se debe ejecutar desde un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Debe establecer la variable `%SERVER_NAME%` en el nombre de host completo del equipo que se utiliza para hospedar el servicio.  
  
4. Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente. No es necesario cuando un emisor de confianza para el cliente ha emitido el certificado de servidor.  
  
5. En el archivo Service.exe.config situado en el equipo del servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.  
  
6. En el equipo del servicio, ejecute service.exe desde un símbolo del sistema.  
  
7. Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.  
  
9. En el equipo cliente, inicie `Client.exe` desde una ventana de símbolo del sistema.  
  
10. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
1. Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.
