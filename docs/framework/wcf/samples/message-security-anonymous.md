---
description: 'Más información acerca de: seguridad de mensajes anónima'
title: Seguridad de mensaje anónima
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
ms.openlocfilehash: a49b3542d2b3dd0173b31c9f7b81645ec1098afb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703905"
---
# <a name="message-security-anonymous"></a><span data-ttu-id="c8dc9-103">Seguridad de mensaje anónima</span><span class="sxs-lookup"><span data-stu-id="c8dc9-103">Message Security Anonymous</span></span>

<span data-ttu-id="c8dc9-104">El ejemplo de seguridad anónima de mensajes muestra cómo implementar una aplicación Windows Communication Foundation (WCF) que usa la seguridad de nivel de mensaje sin autenticación de cliente, pero que requiere la autenticación de servidor mediante el certificado X. 509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-104">The Message Security Anonymous sample demonstrates how to implement a Windows Communication Foundation (WCF) application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span> <span data-ttu-id="c8dc9-105">Todos los mensajes de la aplicación entre el cliente y el servidor se firman y se cifran.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-105">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="c8dc9-106">Este ejemplo se basa en el ejemplo [wsHttpBinding](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c8dc9-106">This sample is based on the [WSHttpBinding](wshttpbinding.md) sample.</span></span> <span data-ttu-id="c8dc9-107">Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-107">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="c8dc9-108">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-108">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
> <span data-ttu-id="c8dc9-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="c8dc9-110">Este ejemplo agrega una nueva operación a la interfaz de calculadora que devuelve `True` si no se autenticó el cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-110">This sample adds a new operation to the calculator interface that returns `True` if the client was not authenticated.</span></span>

```csharp
public class CalculatorService : ICalculator
{
    public bool IsCallerAnonymous()
    {
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.
        return ServiceSecurityContext.Current.IsAnonymous;
    }
    ...
}
```

 <span data-ttu-id="c8dc9-111">El servicio expone un extremo único para comunicarse con el servicio, que se define utilizando el archivo de configuración (Web.config).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-111">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="c8dc9-112">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-112">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="c8dc9-113">El enlace se configura con un enlace `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-113">The binding is configured with a `wsHttpBinding` binding.</span></span> <span data-ttu-id="c8dc9-114">El modo de seguridad predeterminado para el enlace `wsHttpBinding`es`Message`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-114">The default security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="c8dc9-115">El atributo `clientCredentialType` está establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-115">The `clientCredentialType` attribute is set to `None`.</span></span>

```xml
<system.serviceModel>

  <protocolMapping>
    <add scheme="http" binding="wsHttpBinding" />
  </protocolMapping>

  <bindings>
    <wsHttpBinding>
     <!-- This configuration defines the security mode as Message and -->
     <!-- the clientCredentialType as None. This mode provides -->
     <!-- server authentication only using the service certificate. -->

     <binding>
       <security mode="Message">
         <message clientCredentialType="None" />
       </security>
     </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 <span data-ttu-id="c8dc9-116">Las credenciales que se van a utilizar para la autenticación del servicio se especifican en [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="c8dc9-116">The credentials to be used for service authentication are specified in the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span></span> <span data-ttu-id="c8dc9-117">El certificado de servidor debe contener el mismo valor para `SubjectName` que el valor especificado para el atributo `findValue` como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-117">The server certificate must contain the same value for the `SubjectName` as the value specified for the `findValue` attribute as shown in the following sample code.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior>
      <!--
    The serviceCredentials behavior allows you to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
      <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
      </serviceCredentials>
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

 <span data-ttu-id="c8dc9-118">La configuración de punto de conexión de cliente está compuesta de una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-118">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="c8dc9-119">El modo de seguridad del cliente para el enlace `wsHttpBinding`es`Message`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-119">The client security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="c8dc9-120">El atributo `clientCredentialType` está establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-120">The `clientCredentialType` attribute is set to `None`.</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint name=""
             address="http://localhost/servicemodelsamples/service.svc"
             binding="wsHttpBinding"
             behaviorConfiguration="ClientCredentialsBehavior"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </client>

  <bindings>
    <wsHttpBinding>
      <!--This configuration defines the security mode as -->
      <!--Message and the clientCredentialType as None. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="None"/>
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 <span data-ttu-id="c8dc9-121">El ejemplo establece <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> para autenticar el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-121">The sample sets the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> to <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> for authenticating the service's certificate.</span></span> <span data-ttu-id="c8dc9-122">Esto se hace en el archivo App.config del cliente en la sección `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-122">This is done in the client's App.config file in the `behaviors` section.</span></span> <span data-ttu-id="c8dc9-123">Esto significa que si el certificado está en el almacén de personas de confianza del usuario, se confía sin realizar una validación de la cadena del emisor del certificado.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-123">This means that if the certificate is in the user's Trusted People store, then it is trusted without performing a validation of the certificate's issuer chain.</span></span> <span data-ttu-id="c8dc9-124">Este valor se utiliza aquí por comodidad, para que el ejemplo se pueda ejecutar sin que sean precisos certificados emitidos por una entidad de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-124">This setting is used here for convenience so that the sample can be run without requiring certificates issued by a certification authority (CA).</span></span> <span data-ttu-id="c8dc9-125">Este valor es menos seguro que el valor predeterminado, ChainTrust.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-125">This setting is less secure than the default, ChainTrust.</span></span> <span data-ttu-id="c8dc9-126">Las implicaciones de seguridad de este valor deberían considerarse cuidadosamente antes de utilizar `PeerOrChainTrust` en código de producción.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-126">The security implications of this setting should be carefully considered before using `PeerOrChainTrust` in production code.</span></span>

 <span data-ttu-id="c8dc9-127">La implementación del cliente agrega una llamada al `IsCallerAnonymous` método y, de lo contrario, no difiere del ejemplo [wsHttpBinding](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c8dc9-127">The client implementation adds a call to the `IsCallerAnonymous` method and otherwise does not differ from the [WSHttpBinding](wshttpbinding.md) sample.</span></span>

```csharp
// Create a client with a client endpoint configuration.
CalculatorClient client = new CalculatorClient();

// Call the GetCallerIdentity operation.
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

...

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 <span data-ttu-id="c8dc9-128">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c8dc9-129">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-129">Press ENTER in the client window to shut down the client.</span></span>

```console
IsCallerAnonymous returned: True
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 <span data-ttu-id="c8dc9-130">El archivo por lotes Setup.bat incluido con el ejemplo de Message Security Anonymous permite configurar el servidor con un certificado pertinente para ejecutar una aplicación hospedada que requiera seguridad basada en certificado.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-130">The Setup.bat batch file included with the Message Security Anonymous sample enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="c8dc9-131">El archivo por lotes se puede ejecutar en dos modos.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-131">The batch file can be run in two modes.</span></span> <span data-ttu-id="c8dc9-132">Para ejecutar el archivo por lotes en modo de equipo único, escriba `setup.bat` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-132">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="c8dc9-133">Para ejecutarlo en modo de servicio, escriba `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-133">To run it in service mode, type `setup.bat service`.</span></span> <span data-ttu-id="c8dc9-134">Utilice este modo al ejecutar el ejemplo en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-134">Use this mode when running the sample across computers.</span></span> <span data-ttu-id="c8dc9-135">Para obtener más detalles, vea el procedimiento de configuración al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-135">See the setup procedure at the end of this topic for details.</span></span>

 <span data-ttu-id="c8dc9-136">A continuación se proporciona una información general breve de las diferentes secciones de los archivos por lotes:</span><span class="sxs-lookup"><span data-stu-id="c8dc9-136">The following provides a brief overview of the different sections of the batch files:</span></span>

- <span data-ttu-id="c8dc9-137">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-137">Creating the server certificate.</span></span>

     <span data-ttu-id="c8dc9-138">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="c8dc9-139">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="c8dc9-140">El certificado se almacena en el almacén LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="c8dc9-141">Si el archivo por lotes de instalación se ejecuta con un argumento de servicio (como `setup.bat service`), % SERVER_NAME% contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-141">If the setup batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="c8dc9-142">De lo contrario, tiene como valor predeterminado el host local.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-142">Otherwise it defaults to localhost.</span></span>

- <span data-ttu-id="c8dc9-143">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-143">Installing the server certificate into the client's trusted certificate store.</span></span>

     <span data-ttu-id="c8dc9-144">La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c8dc9-145">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c8dc9-146">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="c8dc9-147">Conceder permisos sobre la clave privada del certificado.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-147">Granting permissions on the certificate's private key.</span></span>

     <span data-ttu-id="c8dc9-148">Las líneas siguientes del archivo por lotes de Setup.bat hacen que el certificado de servidor almacenado en el almacén LocalMachine sea accesible para la cuenta de proceso de trabajo de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-148">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>

    ```bat
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
> <span data-ttu-id="c8dc9-149">Si usa un valor que no es de U. S. Edición en Inglés de Windows debe modificar el archivo Setup.bat y reemplazar el `NT AUTHORITY\NETWORK SERVICE` nombre de cuenta por su equivalente regional.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-149">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c8dc9-150">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8dc9-150">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c8dc9-151">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c8dc9-152">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="c8dc9-153">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="c8dc9-153">To run the sample on the same computer</span></span>

1. <span data-ttu-id="c8dc9-154">Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentran Makecert.exe y FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-154">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>

2. <span data-ttu-id="c8dc9-155">Ejecute Setup.bat desde la carpeta de instalación de ejemplo en un Símbolo del sistema para desarrolladores para que Visual Studio se ejecute con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-155">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="c8dc9-156">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-156">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c8dc9-157">El archivo por lotes de instalación está diseñado para ejecutarse desde un Símbolo del sistema para desarrolladores para Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-157">The setup batch file is designed to be run from a  Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="c8dc9-158">Requiere que la variable de entorno path señale al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-158">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="c8dc9-159">Esta variable de entorno se establece automáticamente dentro de una Símbolo del sistema para desarrolladores para Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-159">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="c8dc9-160">Escriba la dirección para comprobar el acceso al servicio mediante un explorador `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="c8dc9-160">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
4. <span data-ttu-id="c8dc9-161">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-161">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="c8dc9-162">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-162">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="c8dc9-163">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-163">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="c8dc9-164">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="c8dc9-164">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="c8dc9-165">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-165">Create a directory on the service computer.</span></span> <span data-ttu-id="c8dc9-166">Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-166">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="c8dc9-167">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-167">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="c8dc9-168">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-168">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="c8dc9-169">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-169">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="c8dc9-170">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-170">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="c8dc9-171">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-171">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="c8dc9-172">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-172">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="c8dc9-173">En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-173">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="c8dc9-174">`setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-174">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="c8dc9-175">Edite Web.config para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-175">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="c8dc9-176">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-176">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="c8dc9-177">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-177">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="c8dc9-178">En el cliente, ejecute ImportServiceCert.bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-178">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="c8dc9-179">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-179">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="c8dc9-180">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-180">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="c8dc9-181">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c8dc9-181">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="c8dc9-182">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8dc9-182">To clean up after the sample</span></span>  
  
- <span data-ttu-id="c8dc9-183">Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-183">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8dc9-184">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-184">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="c8dc9-185">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-185">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="c8dc9-186">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`.</span><span class="sxs-lookup"><span data-stu-id="c8dc9-186">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span></span>
