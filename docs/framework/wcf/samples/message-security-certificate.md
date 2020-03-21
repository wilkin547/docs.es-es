---
title: Certificado de seguridad de mensaje
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: 92e656f36ae0af851def393575cbb7d418bc4a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183534"
---
# <a name="message-security-certificate"></a><span data-ttu-id="982bf-102">Certificado de seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="982bf-102">Message Security Certificate</span></span>
<span data-ttu-id="982bf-103">Este ejemplo muestra cómo implementar una aplicación que utiliza WS-Security con autenticación de certificado X.509 v3 para el cliente y que requiere la autenticación del servidor mediante el certificado X.509 v3 del servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="982bf-104">Este ejemplo utiliza la configuración predeterminada de tal modo que todos los mensajes de la aplicación entre el cliente y el servidor se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="982bf-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="982bf-105">Este ejemplo se basa en [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) y consta de un programa de consola de cliente y una biblioteca de servicios hospedada por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="982bf-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="982bf-106">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="982bf-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="982bf-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="982bf-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="982bf-108">El ejemplo muestra cómo controlar la autenticación mediante la configuración y cómo obtener la identidad del autor de la llamada desde el contexto de seguridad, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="982bf-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="982bf-109">El servicio expone un punto de conexión para comunicar con el servicio y un punto de conexión para exponer el documento WSDL del servicio mediante el protocolo WS-MetadataExchange, definido utilizando el archivo de configuración (Web.config).</span><span class="sxs-lookup"><span data-stu-id="982bf-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="982bf-110">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="982bf-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="982bf-111">El enlace se configura con un elemento [ \<de>wsHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) estándar, que usa de forma predeterminada la seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="982bf-111">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="982bf-112">Este ejemplo establece el atributo `clientCredentialType` para certificar que se requiere la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="982bf-113">El comportamiento especifica las credenciales del servicio que se utilizan cuando el cliente autentica el servicio.</span><span class="sxs-lookup"><span data-stu-id="982bf-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="982bf-114">El nombre del sujeto del `findValue` certificado de servidor se especifica en el atributo del [ \<elemento de>serviceCredentials.](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="982bf-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="982bf-115">La configuración de punto de conexión de cliente está compuesta de una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="982bf-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="982bf-116">El enlace del cliente se configura con el modo de seguridad y el modo de autenticación apropiados.</span><span class="sxs-lookup"><span data-stu-id="982bf-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="982bf-117">Si se trata de un escenario de varios equipos, asegúrese de que se cambie la dirección del punto de conexión de servicio según corresponda.</span><span class="sxs-lookup"><span data-stu-id="982bf-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="982bf-118">La implementación del cliente puede establecer el certificado que se debe utilizar, bien sea a través del archivo de configuración o a través de código.</span><span class="sxs-lookup"><span data-stu-id="982bf-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="982bf-119">El ejemplo siguiente muestra cómo establecer el certificado para utilizar en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="982bf-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="982bf-120">El ejemplo siguiente muestra cómo llamar al servicio en su programa.</span><span class="sxs-lookup"><span data-stu-id="982bf-120">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="982bf-121">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="982bf-122">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="982bf-123">El archivo por lotes Setup.bat incluido con los ejemplos de Message Security permite configurar el cliente y el servidor con los certificados pertinentes para ejecutar una aplicación hospedada que exija seguridad basada en certificado.</span><span class="sxs-lookup"><span data-stu-id="982bf-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="982bf-124">El archivo por lotes se puede ejecutar en tres modos.</span><span class="sxs-lookup"><span data-stu-id="982bf-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="982bf-125">Para ejecutaren en modo de equipo único, escriba **setup.bat** en un símbolo del sistema para desarrolladores para Visual Studio ; para el servicio **setup.bat service**de tipo de modo de servicio ; y para el tipo de modo de cliente **setup.bat client**.</span><span class="sxs-lookup"><span data-stu-id="982bf-125">To run in single-computer mode type **setup.bat** in a Developer Command Prompt for Visual Studio ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="982bf-126">Utilice el modo de cliente y servidor cuando ejecute el ejemplo en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="982bf-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="982bf-127">Para obtener más detalles, vea el procedimiento de configuración al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="982bf-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="982bf-128">A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="982bf-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
- <span data-ttu-id="982bf-129">Crear el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="982bf-130">La línea siguiente en el archivo por lotes crea el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="982bf-131">El nombre de cliente especificado se utiliza en el nombre del asunto del certificado creado.</span><span class="sxs-lookup"><span data-stu-id="982bf-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="982bf-132">El certificado se guarda en el almacén `My`, en la ubicación de almacenamiento `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="982bf-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="982bf-133">Instalar el certificado de cliente en el almacén de certificados de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="982bf-134">La línea siguiente del archivo por lotes copia el certificado de cliente en el almacén TrustedPeople del servidor para que el servidor pueda tomar decisiones basadas en la confianza o la ausencia de la misma.</span><span class="sxs-lookup"><span data-stu-id="982bf-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="982bf-135">Para que un servicio de Windows Communication Foundation (WCF) confíe en un certificado instalado en el `PeerOrChainTrust` `PeerTrust`almacén TrustedPeople, el modo de validación de certificados de cliente debe establecerse en o .</span><span class="sxs-lookup"><span data-stu-id="982bf-135">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="982bf-136">Vea el ejemplo de configuración de servicio anterior para obtener información sobre cómo lograrlo con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="982bf-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```  
  
- <span data-ttu-id="982bf-137">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="982bf-138">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="982bf-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="982bf-139">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="982bf-140">El certificado se almacena en el almacén LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="982bf-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="982bf-141">Si el archivo por lotes Setup.bat se ejecuta con un argumento de servicio (por ejemplo, **el servicio setup.bat**) el %SERVER_NAME% contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="982bf-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="982bf-142">De lo contrario, tiene como valor predeterminado el host local.</span><span class="sxs-lookup"><span data-stu-id="982bf-142">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="982bf-143">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="982bf-144">La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="982bf-145">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="982bf-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="982bf-146">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="982bf-147">Conceder permisos sobre la clave privada del certificado.</span><span class="sxs-lookup"><span data-stu-id="982bf-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="982bf-148">Las siguientes líneas del archivo Setup.bat hacen que el certificado de servidor almacenado en el almacén LocalMachine sea accesible para la cuenta de proceso de trabajo ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="982bf-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
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
    > <span data-ttu-id="982bf-149">Si está utilizando una edición en inglés de Windows que no sea de EE. UU., debe editar el archivo Setup.bat y reemplazar el nombre de cuenta "NT AUTHORITY-NETWORK SERVICE" por su equivalente regional.</span><span class="sxs-lookup"><span data-stu-id="982bf-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="982bf-150">Las herramientas utilizadas en este archivo por lotes se encuentran en C:\Program Files\Microsoft Visual Studio 8\Common7\tools o C:\Program Files\Microsoft SDKs\Windows\v6.0\bin</span><span class="sxs-lookup"><span data-stu-id="982bf-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="982bf-151">Uno de estos directorios debe estar en su ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="982bf-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="982bf-152">Si tiene Visual Studio instalado, la forma más fácil de obtener este directorio en la ruta de acceso es abrir el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="982bf-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="982bf-153">Haga clic en **Inicio**y, a continuación, seleccione **Todos los programas**, Visual Studio **2012**, **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="982bf-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="982bf-154">Este símbolo del sistema tiene las rutas de acceso adecuadas ya configuradas.</span><span class="sxs-lookup"><span data-stu-id="982bf-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="982bf-155">De lo contrario, debe agregar manualmente el directorio correcto a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="982bf-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="982bf-156">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="982bf-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="982bf-157">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="982bf-157">Check for the following (default) directory before continuing:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="982bf-158">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="982bf-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="982bf-159">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="982bf-159">This sample is located in the following directory:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="982bf-160">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="982bf-160">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="982bf-161">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="982bf-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="982bf-162">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="982bf-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="982bf-163">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="982bf-163">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="982bf-164">Abra un símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="982bf-164">Open a Developer Command Prompt for Visual Studio  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="982bf-165">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="982bf-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="982bf-166">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="982bf-166">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="982bf-167">Requiere que la variable de entorno path señale al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="982bf-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="982bf-168">Esta variable de entorno se establece automáticamente en un símbolo del sistema para desarrolladores para Visual Studio (2010).</span><span class="sxs-lookup"><span data-stu-id="982bf-168">This environment variable is automatically set within a Developer Command Prompt for Visual Studio (2010).</span></span>  
  
2. <span data-ttu-id="982bf-169">Compruebe el acceso al servicio mediante un `http://localhost/servicemodelsamples/service.svc`explorador introduciendo la dirección .</span><span class="sxs-lookup"><span data-stu-id="982bf-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3. <span data-ttu-id="982bf-170">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="982bf-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="982bf-171">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-171">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="982bf-172">Si el cliente y el servicio no pueden comunicarse, vea [Sugerencias de solución de problemas para ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="982bf-172">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="982bf-173">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="982bf-173">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="982bf-174">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="982bf-174">Create a directory on the service computer.</span></span> <span data-ttu-id="982bf-175">Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="982bf-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="982bf-176">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="982bf-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="982bf-177">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="982bf-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="982bf-178">Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="982bf-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="982bf-179">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="982bf-180">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="982bf-181">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="982bf-182">En el servidor, ejecute el **servicio setup.bat** en un símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="982bf-182">On the server, run **setup.bat service** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="982bf-183">La ejecución de **setup.bat** con el argumento **service** crea un certificado de servicio con el nombre de dominio completo del equipo y exporta el certificado de servicio a un archivo denominado Service.cer.</span><span class="sxs-lookup"><span data-stu-id="982bf-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="982bf-184">Edite Web.config para reflejar el nuevo `findValue` nombre de certificado (en el atributo de [ \<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="982bf-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="982bf-185">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="982bf-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="982bf-186">En el cliente, ejecute **el cliente setup.bat** en un símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="982bf-186">On the client, run **setup.bat client** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="982bf-187">La ejecución de **setup.bat** con el argumento **de cliente** crea un certificado de cliente denominado client.com y exporta el certificado de cliente a un archivo denominado Client.cer.</span><span class="sxs-lookup"><span data-stu-id="982bf-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="982bf-188">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="982bf-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="982bf-189">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="982bf-190">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="982bf-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="982bf-191">En el cliente, ejecute ImportServiceCert.bat en un símbolo del sistema para desarrolladores para Visual Studio con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="982bf-191">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="982bf-192">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="982bf-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="982bf-193">En el servidor, ejecute ImportClientCert.bat en un símbolo del sistema para desarrolladores de Visual Studio con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="982bf-193">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="982bf-194">De esta forma se importa el certificado del cliente desde el archivo Client.cer al almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="982bf-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="982bf-195">En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="982bf-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="982bf-196">Si el cliente y el servicio no pueden comunicarse, vea [Sugerencias de solución de problemas para ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="982bf-196">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="982bf-197">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="982bf-197">To clean up after the sample</span></span>  
  
- <span data-ttu-id="982bf-198">Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="982bf-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="982bf-199">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="982bf-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="982bf-200">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="982bf-200">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="982bf-201">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="982bf-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
