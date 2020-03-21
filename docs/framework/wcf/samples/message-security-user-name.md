---
title: Nombre de usuario de seguridad de mensaje
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
ms.openlocfilehash: 62b6f24bab1c655038ad3295f5af3dee0fa198fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183511"
---
# <a name="message-security-user-name"></a><span data-ttu-id="37aa5-102">Nombre de usuario de seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="37aa5-102">Message Security User Name</span></span>
<span data-ttu-id="37aa5-103">Este ejemplo muestra cómo implementar una aplicación que utiliza WS-Security con autenticación de nombre de usuario para el cliente y que requiere la autenticación del servidor mediante el certificado X.509v3 del servidor.</span><span class="sxs-lookup"><span data-stu-id="37aa5-103">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span> <span data-ttu-id="37aa5-104">Todos los mensajes de la aplicación entre el cliente y el servidor se firman y se cifran.</span><span class="sxs-lookup"><span data-stu-id="37aa5-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="37aa5-105">De forma predeterminada, el nombre de usuario y contraseña proporcionadas por el cliente se utilizan para iniciar una sesión con una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="37aa5-105">By default, the username and password supplied by the client are used to logon to a valid Windows account.</span></span> <span data-ttu-id="37aa5-106">Este ejemplo se basa en [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="37aa5-106">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md).</span></span> <span data-ttu-id="37aa5-107">Este ejemplo está compuesto de un programa de consola de cliente (Client.exe) y una biblioteca de servicios (Service.dll) hospedada por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="37aa5-107">This sample consists of a client console program (Client.exe) and a service library (Service.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="37aa5-108">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="37aa5-108">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37aa5-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="37aa5-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="37aa5-110">Este ejemplo también muestra:</span><span class="sxs-lookup"><span data-stu-id="37aa5-110">This sample also demonstrates:</span></span>  
  
- <span data-ttu-id="37aa5-111">La asignación predeterminada a cuentas Windows, para que se pueda realizar autorización adicional.</span><span class="sxs-lookup"><span data-stu-id="37aa5-111">The default mapping to Windows accounts so that additional authorization can be performed.</span></span>  
  
- <span data-ttu-id="37aa5-112">Cómo tener acceso a la información de identidad del llamador desde el código del servicio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-112">How to access the caller's identity information from the service code.</span></span>  
  
 <span data-ttu-id="37aa5-113">El servicio expone un único punto de conexión para comunicarse con el servicio, que se define mediante el archivo de configuración Web.config. El punto de conexión consta de una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="37aa5-113">The service exposes a single endpoint for communicating with the service, which is defined using the configuration file Web.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="37aa5-114">El enlace se configura con un [ \<>wsHttpBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)estándar , que usa de forma predeterminada la seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="37aa5-114">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), which defaults to using message security.</span></span> <span data-ttu-id="37aa5-115">En este ejemplo se establece el [ \<estándar wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) para usar la autenticación de nombre de usuario de cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-115">This sample sets the standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to use client username authentication.</span></span> <span data-ttu-id="37aa5-116">El comportamiento especifica que se van a usar las credenciales del usuario para la autenticación del servicio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-116">The behavior specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="37aa5-117">El certificado de servidor debe contener el `findValue` mismo valor para el nombre de sujeto que el atributo en el [ \<>serviceCredentials ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="37aa5-117">The server certificate must contain the same value for the subject name as the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
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
</system.serviceModel>  
```  
  
 <span data-ttu-id="37aa5-118">La configuración de punto de conexión de cliente está compuesta de una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="37aa5-118">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="37aa5-119">El enlace del cliente se configura con el `securityMode` adecuado y `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="37aa5-119">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span> <span data-ttu-id="37aa5-120">Cuando se utilice un escenario de varios equipos, la dirección del extremo de servicio debe cambiarse según corresponda.</span><span class="sxs-lookup"><span data-stu-id="37aa5-120">When running in a cross-computer scenario, the service endpoint address must be changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="37aa5-121">La implementación del cliente establece el nombre de usuario y la contraseña que utilizar.</span><span class="sxs-lookup"><span data-stu-id="37aa5-121">The client implementation sets the user name and password to use.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```

 <span data-ttu-id="37aa5-122">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="37aa5-123">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="37aa5-124">El archivo por lotes Setup.bat incluido con los ejemplos de MessageSecurity le permite configurar el servidor con un certificado pertinente para ejecutar una aplicación hospedada que exija seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="37aa5-124">The Setup.bat batch file included with the MessageSecurity samples enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="37aa5-125">El archivo por lotes se puede ejecutar en dos modos.</span><span class="sxs-lookup"><span data-stu-id="37aa5-125">The batch file can be run in two modes.</span></span> <span data-ttu-id="37aa5-126">Para ejecutar el archivo por lotes en modo de equipo único, escriba `setup.bat` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="37aa5-126">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="37aa5-127">Para ejecutarlo en modo de servicio, escriba `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="37aa5-127">To run it in service mode type `setup.bat service`.</span></span> <span data-ttu-id="37aa5-128">Este modo se usa al ejecutar el ejemplo en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="37aa5-128">You use this mode when running the sample across computers.</span></span> <span data-ttu-id="37aa5-129">Para obtener más detalles, vea el procedimiento de configuración al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="37aa5-129">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="37aa5-130">A continuación se proporciona una información general breve de las diferentes secciones de los archivos por lotes.</span><span class="sxs-lookup"><span data-stu-id="37aa5-130">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="37aa5-131">Crear el certificado de servidor</span><span class="sxs-lookup"><span data-stu-id="37aa5-131">Creating the server certificate</span></span>  
  
     <span data-ttu-id="37aa5-132">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="37aa5-132">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="37aa5-133">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="37aa5-133">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="37aa5-134">El certificado se almacena en el almacén LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="37aa5-134">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="37aa5-135">Si el archivo por lotes Setup.bat se ejecuta con un argumento de servicio (como `setup.bat service`), % SERVER_NAME% contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="37aa5-135">If the Setup.bat batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span>  <span data-ttu-id="37aa5-136">De lo contrario, tiene como valor predeterminado el host local.</span><span class="sxs-lookup"><span data-stu-id="37aa5-136">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="37aa5-137">Instalar el certificado del servidor en el almacén de certificados de confianza de cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-137">Installing the server certificate into the client's trusted certificate store</span></span>  
  
     <span data-ttu-id="37aa5-138">La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-138">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="37aa5-139">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="37aa5-139">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="37aa5-140">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="37aa5-140">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="37aa5-141">Conceder permisos sobre la clave privada del certificado.</span><span class="sxs-lookup"><span data-stu-id="37aa5-141">Granting permissions on the certificate's private key</span></span>  
  
     <span data-ttu-id="37aa5-142">Las siguientes líneas del archivo por lotes Setup.bat hacen que el certificado de servidor almacenado en el almacén LocalMachine sea accesible para la cuenta de proceso de trabajo ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="37aa5-142">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="37aa5-143">Si utiliza una edición en inglés de Windows que no sea de `NT AUTHORITY\NETWORK SERVICE` EE. UU., debe editar el archivo Setup.bat y reemplazar el nombre de la cuenta por su equivalente regional.</span><span class="sxs-lookup"><span data-stu-id="37aa5-143">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="37aa5-144">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="37aa5-144">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="37aa5-145">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="37aa5-145">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="37aa5-146">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="37aa5-146">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="37aa5-147">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="37aa5-147">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="37aa5-148">Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentran Makecert.exe y FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="37aa5-148">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2. <span data-ttu-id="37aa5-149">Ejecute Setup.bat desde la carpeta de instalación de ejemplo en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="37aa5-149">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="37aa5-150">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="37aa5-150">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="37aa5-151">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-151">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="37aa5-152">Requiere que la variable de entorno path señale al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="37aa5-152">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="37aa5-153">Esta variable de entorno se establece automáticamente en un símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-153">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="37aa5-154">Compruebe el acceso al servicio mediante un `http://localhost/servicemodelsamples/service.svc`explorador introduciendo la dirección .</span><span class="sxs-lookup"><span data-stu-id="37aa5-154">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>
  
4. <span data-ttu-id="37aa5-155">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="37aa5-155">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="37aa5-156">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-156">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="37aa5-157">Si el cliente y el servicio no pueden comunicarse, vea [Sugerencias de solución de problemas para ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="37aa5-157">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="37aa5-158">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="37aa5-158">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="37aa5-159">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-159">Create a directory on the service computer.</span></span> <span data-ttu-id="37aa5-160">Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="37aa5-160">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services management tool.</span></span>  
  
2. <span data-ttu-id="37aa5-161">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-161">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="37aa5-162">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="37aa5-162">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="37aa5-163">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-163">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="37aa5-164">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-164">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="37aa5-165">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-165">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="37aa5-166">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-166">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="37aa5-167">En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="37aa5-167">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="37aa5-168">Si `setup.bat` se `service` ejecuta con el argumento, se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado de servicio a un archivo denominado Service.cer.</span><span class="sxs-lookup"><span data-stu-id="37aa5-168">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="37aa5-169">Modifique el archivo Web.config para reflejar el nuevo nombre del certificado (en el atributo findValue del elemento serviceCertificate), que es igual que el nombre de dominio completo del equipo`.`</span><span class="sxs-lookup"><span data-stu-id="37aa5-169">Edit Web.config to reflect the new certificate name (in the findValue attribute in the serviceCertificate element) which is the same as the fully-qualified domain name of the computer`.`</span></span>  
  
7. <span data-ttu-id="37aa5-170">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="37aa5-170">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="37aa5-171">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="37aa5-171">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="37aa5-172">En el cliente, ejecute ImportServiceCert.bat en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="37aa5-172">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="37aa5-173">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="37aa5-173">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="37aa5-174">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="37aa5-174">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="37aa5-175">Si el cliente y el servicio no pueden comunicarse, vea [Sugerencias de solución de problemas para ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="37aa5-175">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="37aa5-176">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="37aa5-176">To clean up after the sample</span></span>  
  
- <span data-ttu-id="37aa5-177">Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="37aa5-177">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="37aa5-178">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="37aa5-178">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="37aa5-179">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="37aa5-179">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="37aa5-180">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="37aa5-180">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
