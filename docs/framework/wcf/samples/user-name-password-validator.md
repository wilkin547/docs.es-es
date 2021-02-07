---
description: 'Más información acerca de: validador de contraseña de nombre de usuario'
title: Validador de contraseña de nombre de usuario
ms.date: 03/30/2017
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
ms.openlocfilehash: 8195549da81c8fbb7259d2b3e00db39017817c41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755751"
---
# <a name="user-name-password-validator"></a><span data-ttu-id="13b86-103">Validador de contraseña de nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="13b86-103">User Name Password Validator</span></span>

<span data-ttu-id="13b86-104">Este ejemplo muestra cómo implementar un validador UserNamePassword personalizado.</span><span class="sxs-lookup"><span data-stu-id="13b86-104">This sample demonstrates how to implement a custom UserNamePassword Validator.</span></span> <span data-ttu-id="13b86-105">Esto es útil en casos donde ninguno de los modos de validación UserNamePassword integrados es apropiado para los requisitos de la aplicación; por ejemplo, cuando los pares nombre de usuario/contraseña se almacenan en un almacén externo, como una base de datos.</span><span class="sxs-lookup"><span data-stu-id="13b86-105">This is useful in cases where none of the built-in UserNamePassword Validation modes is appropriate for the requirements of the application; for example, when username/password pairs are stored in some external store, such as a database.</span></span> <span data-ttu-id="13b86-106">Este ejemplo muestra un servicio que tiene un validador personalizado que comprueba dos pares de nombre de usuario y contraseña determinados.</span><span class="sxs-lookup"><span data-stu-id="13b86-106">This sample shows a service that has a custom validator that checks for two particular username/password pairs.</span></span> <span data-ttu-id="13b86-107">El cliente usa un par de nombre de usuario y contraseña para autenticar en el servicio.</span><span class="sxs-lookup"><span data-stu-id="13b86-107">The client uses such a username/password pair to authenticate to the service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13b86-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="13b86-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="13b86-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="13b86-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="13b86-110">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="13b86-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13b86-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="13b86-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
> <span data-ttu-id="13b86-112">Dado que cualquiera puede construir una credencial de nombre de usuario que utilice los pares de nombre de usuario y contraseña que el validador personalizado acepta, el servicio es menos seguro que el comportamiento predeterminado proporcionado por el validador UserNamePassword estándar.</span><span class="sxs-lookup"><span data-stu-id="13b86-112">Because anyone can construct a Username credential that uses the username/password pairs that the custom validator accepts, the service is less secure than the default behavior provided by the standard UserNamePassword Validator.</span></span> <span data-ttu-id="13b86-113">El validador UserNamePassword estándar intenta asignar el par de nombre de usuario/contraseña proporcionado a una cuenta de Windows y si esta asignación no es correcta, se produce un error en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="13b86-113">The standard UserNamePassword Validator attempts to map the provided username/password pair to a Windows account and fails authentication if this mapping fails.</span></span> <span data-ttu-id="13b86-114">El validador UserNamePassword personalizado en este ejemplo NO SE DEBE utilizar en el código de producción, solo es para fines informativos.</span><span class="sxs-lookup"><span data-stu-id="13b86-114">The custom UserNamePassword Validator in this sample MUST NOT be used in production code, it is for illustration purposes only.</span></span>

 <span data-ttu-id="13b86-115">En resumen, este ejemplo muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="13b86-115">In summary this sample demonstrates how:</span></span>

- <span data-ttu-id="13b86-116">Se puede autenticar el cliente con un token de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="13b86-116">The client can be authenticated using a Username Token.</span></span>

- <span data-ttu-id="13b86-117">El servidor valida las credenciales del cliente con un UserNamePasswordValidator personalizado y cómo propagar los errores personalizados desde la lógica de validación del nombre de usuario y la contraseña al cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-117">The server validates the client credentials against a custom UserNamePasswordValidator and how to propagate custom faults from the username and password validation logic to the client.</span></span>

- <span data-ttu-id="13b86-118">El servidor se autentica utilizando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="13b86-118">The server is authenticated using the server's X.509 certificate.</span></span>

 <span data-ttu-id="13b86-119">El servicio expone un extremo único para comunicarse con el servicio, definido mediante el archivo de configuración App.config. El punto de conexión consta de una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="13b86-119">The service exposes a single endpoint for communicating with the service, defined using the configuration file, App.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="13b86-120">El enlace se configura con un estándar `wsHttpBinding` que tiene como valor predeterminado el uso de WS-Security y la autenticación de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="13b86-120">The binding is configured with a standard `wsHttpBinding` that defaults to using WS-Security and username authentication.</span></span> <span data-ttu-id="13b86-121">El comportamiento del servicio especifica el modo `Custom` para validar los pares de nombre de usuario y contraseña del cliente con el tipo de la clase de validador.</span><span class="sxs-lookup"><span data-stu-id="13b86-121">The service behavior specifies the `Custom` mode for validating client username/password pairs along with the type of the validator class.</span></span> <span data-ttu-id="13b86-122">El comportamiento también especifica el certificado de servidor mediante el elemento `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="13b86-122">The behavior also specifies the server certificate using the `serviceCertificate` element.</span></span> <span data-ttu-id="13b86-123">El certificado de servidor debe contener el mismo valor para el `SubjectName` que `findValue` en el [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="13b86-123">The server certificate has to contain the same value for the `SubjectName` as the `findValue` in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <!-- use host/baseAddresses to configure base address provided by host -->
      <host>
        <baseAddresses>
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />
        </baseAddresses>
      </host>
      <!-- use base address specified above, provide one endpoint -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- username binding -->
      <binding name="Binding">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceDebug includeExceptionDetailInFaults ="true"/>
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to
          specify a custom validator for username/password
          combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom"
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="13b86-124">La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="13b86-124">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="13b86-125">El enlace del cliente se configura con el modo adecuado y el `clientCredentialType` del mensaje.</span><span class="sxs-lookup"><span data-stu-id="13b86-125">The client binding is configured with the appropriate mode and message `clientCredentialType`.</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
address="http://localhost:8001/servicemodelsamples/service/username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
```

 <span data-ttu-id="13b86-126">La implementación del cliente pide al usuario que introduzca un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="13b86-126">The client implementation prompts the user to enter a username and password.</span></span>

```csharp
// Get the username and password
Console.WriteLine("Username authentication required.");
Console.WriteLine("Provide a username.");
Console.WriteLine("   Enter username: (test1)");
string username = Console.ReadLine();
Console.WriteLine("   Enter password:");
string password = "";
ConsoleKeyInfo info = Console.ReadKey(true);
while (info.Key != ConsoleKey.Enter)
{
    if (info.Key != ConsoleKey.Backspace)
    {
        if (info.KeyChar != '\0')
        {
            password += info.KeyChar;
        }
        info = Console.ReadKey(true);
    }
    else if (info.Key == ConsoleKey.Backspace)
    {
        if (password != "")
        {
            password = password.Substring(0, password.Length - 1);
        }
        info = Console.ReadKey(true);
    }
}
for (int i = 0; i < password.Length; i++)
{
    Console.Write("*");
}
Console.WriteLine();
// Create a proxy with Certificate endpoint configuration
CalculatorProxy proxy = new CalculatorProxy("Username")
try
{
  proxy.ClientCredentials.Username.Username = username;
  proxy.ClientCredentials.Username.Password = password;
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = proxy.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
  }
  catch (Exception e)
  {
      Console.WriteLine("Call failed:");
      while (e != null)
      {
          Console.WriteLine("\t{0}", e.Message);
          e = e.InnerException;
      }
      proxy.Abort();
  }
}
```

 <span data-ttu-id="13b86-127">Este ejemplo utiliza un UserNamePasswordValidator personalizado para validar pares de nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="13b86-127">This sample uses a custom UserNamePasswordValidator to validate username/password pairs.</span></span> <span data-ttu-id="13b86-128">El ejemplo implementa `CustomUserNamePasswordValidator`, derivado de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="13b86-128">The sample implements `CustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="13b86-129">Consulte la documentación existente sobre <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="13b86-129">See the documentation for <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="13b86-130">Este ejemplo de validador personalizado determinado implementa el método `Validate` para aceptar dos pares de nombre de usuario y contraseña determinados tal y como se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="13b86-130">This particular custom validator sample implements the `Validate` method to accept two particular username/password pairs as shown in the following code.</span></span>

```csharp
public class CustomUserNameValidator : UserNamePasswordValidator
{
 // This method validates users. It allows in two users,
 // test1 and test2 with passwords 1tset and 2tset respectively.
 // This code is for illustration purposes only and
 // MUST NOT be used in a production environment because it
 // is NOT secure.
 public override void Validate(string userName, string password)
 {
  if (null == userName || null == password)
  {
   throw new ArgumentNullException();
  }

  if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
  {
   throw new FaultException("Unknown Username or Incorrect Password");
   }
  }
 }
```

 <span data-ttu-id="13b86-131">Una vez que se implementa el validador en el código de servicio, se debe informar al host de servicio sobre la instancia del validador que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="13b86-131">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="13b86-132">Esto se hace mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="13b86-132">This is done using the following code.</span></span>

```csharp
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();
```

 <span data-ttu-id="13b86-133">O puede hacer lo mismo en la configuración tal y como se explica a continuación.</span><span class="sxs-lookup"><span data-stu-id="13b86-133">Or you can do the same thing in configuration as follows.</span></span>

```xml
<behaviors>
 <serviceBehaviors>
  <behavior name="CalculatorServiceBehavior">
  ...
   <serviceCredentials>
    <!--
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.
    -->
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />
   ...
   </serviceCredentials>
  </behavior>
 </serviceBehaviors>
</behaviors>
```

 <span data-ttu-id="13b86-134">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-134">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="13b86-135">El cliente debería llamar correctamente a todos los métodos.</span><span class="sxs-lookup"><span data-stu-id="13b86-135">The client should successfully call all the methods.</span></span> <span data-ttu-id="13b86-136">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-136">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="13b86-137">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="13b86-137">Setup Batch File</span></span>

 <span data-ttu-id="13b86-138">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="13b86-138">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="13b86-139">Este archivo por lotes debe modificarse para que funcione en los equipos o en un caso no autohospedado.</span><span class="sxs-lookup"><span data-stu-id="13b86-139">This batch file must be modified to work across machines or to work in a non-self-hosted case.</span></span>

 <span data-ttu-id="13b86-140">A continuación, se proporciona una breve descripción de las diferentes secciones de los archivos por lotes de manera que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="13b86-140">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="13b86-141">Crear el certificado de servidor:</span><span class="sxs-lookup"><span data-stu-id="13b86-141">Creating the server certificate:</span></span>

     <span data-ttu-id="13b86-142">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="13b86-142">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="13b86-143">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="13b86-143">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="13b86-144">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="13b86-144">Change this variable to specify your own server name.</span></span> <span data-ttu-id="13b86-145">El valor predeterminado es el host local.</span><span class="sxs-lookup"><span data-stu-id="13b86-145">The default value is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="13b86-146">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente:</span><span class="sxs-lookup"><span data-stu-id="13b86-146">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="13b86-147">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-147">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="13b86-148">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="13b86-148">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="13b86-149">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="13b86-149">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="13b86-150">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="13b86-150">To set up and build the sample</span></span>

1. <span data-ttu-id="13b86-151">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13b86-151">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="13b86-152">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="13b86-152">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>

#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="13b86-153">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="13b86-153">To run the sample on the same machine</span></span>

1. <span data-ttu-id="13b86-154">Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="13b86-154">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt.</span></span> <span data-ttu-id="13b86-155">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="13b86-155">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13b86-156">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="13b86-156">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="13b86-157">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="13b86-157">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="13b86-158">Inicie Service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="13b86-158">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="13b86-159">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="13b86-159">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="13b86-160">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-160">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="13b86-161">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="13b86-161">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="13b86-162">Para ejecutar el ejemplo en los equipos</span><span class="sxs-lookup"><span data-stu-id="13b86-162">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="13b86-163">Cree un directorio en el equipo del servicio para los binarios del servicio.</span><span class="sxs-lookup"><span data-stu-id="13b86-163">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="13b86-164">Copie los archivos del programa de servicio en el directorio de servicio situado en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="13b86-164">Copy the service program files the service directory on the service machine.</span></span> <span data-ttu-id="13b86-165">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="13b86-165">Also copy the Setup.bat and Cleanup.bat files to the service machine.</span></span>  
  
3. <span data-ttu-id="13b86-166">Necesita un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="13b86-166">You need a server certificate with the subject name that contains the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="13b86-167">El archivo de configuración para el servidor debe estar actualizado para reflejar este nuevo nombre del certificado.</span><span class="sxs-lookup"><span data-stu-id="13b86-167">The configuration file for the server must be updated to reflect this new certificate name.</span></span>  
  
4. <span data-ttu-id="13b86-168">Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-168">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="13b86-169">Solo necesita hacerlo si el certificado del servidor no está emitido por el emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="13b86-169">You need to do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5. <span data-ttu-id="13b86-170">En el archivo App.config situado en el equipo de servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="13b86-170">In the App.config file on the service machine, change the value of the base address to specify a fully-qualified machine name instead of localhost.</span></span>  
  
6. <span data-ttu-id="13b86-171">En el equipo de servicio, inicie Service.exe desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="13b86-171">On the service machine, launch Service.exe from a command prompt window.</span></span>  
  
7. <span data-ttu-id="13b86-172">Copie los archivos de programa del cliente de la carpeta \client\bin\, en la carpeta específica del lenguaje, al equipo del cliente.</span><span class="sxs-lookup"><span data-stu-id="13b86-172">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
8. <span data-ttu-id="13b86-173">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="13b86-173">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="13b86-174">En el equipo cliente, inicie Client.exe desde la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="13b86-174">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="13b86-175">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="13b86-175">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="13b86-176">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="13b86-176">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="13b86-177">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="13b86-177">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="13b86-178">Así se elimina el certificado del servidor del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="13b86-178">This removes the server certificate from the certificate store.</span></span>
