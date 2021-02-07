---
description: 'Más información acerca de: certificado de seguridad de mensajes'
title: Certificado de seguridad de mensaje
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: 6ed48466d0b5155a5f14a2ec2eae0d879b7377a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732441"
---
# <a name="message-security-certificate"></a><span data-ttu-id="8dbec-103">Certificado de seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="8dbec-103">Message Security Certificate</span></span>

<span data-ttu-id="8dbec-104">Este ejemplo muestra cómo implementar una aplicación que utiliza WS-Security con autenticación de certificado X.509 v3 para el cliente y que requiere la autenticación del servidor mediante el certificado X.509 v3 del servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-104">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="8dbec-105">Este ejemplo utiliza la configuración predeterminada de tal modo que todos los mensajes de la aplicación entre el cliente y el servidor se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="8dbec-105">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="8dbec-106">Este ejemplo se basa en [wsHttpBinding](wshttpbinding.md) y consta de un programa de consola de cliente y una biblioteca de servicios hospedada por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8dbec-106">This sample is based on the [WSHttpBinding](wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="8dbec-107">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="8dbec-107">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8dbec-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8dbec-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8dbec-109">El ejemplo muestra cómo controlar la autenticación mediante la configuración y cómo obtener la identidad del autor de la llamada desde el contexto de seguridad, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-109">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

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
  
 <span data-ttu-id="8dbec-110">El servicio expone un punto de conexión para comunicar con el servicio y un punto de conexión para exponer el documento WSDL del servicio mediante el protocolo WS-MetadataExchange, definido utilizando el archivo de configuración (Web.config).</span><span class="sxs-lookup"><span data-stu-id="8dbec-110">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="8dbec-111">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="8dbec-111">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="8dbec-112">El enlace se configura con un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento estándar, que tiene como valor predeterminado el uso de la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="8dbec-112">The binding is configured with a standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="8dbec-113">Este ejemplo establece el atributo `clientCredentialType` para certificar que se requiere la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-113">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
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
  
 <span data-ttu-id="8dbec-114">El comportamiento especifica las credenciales del servicio que se utilizan cuando el cliente autentica el servicio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-114">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="8dbec-115">El nombre de sujeto del certificado de servidor se especifica en el `findValue` atributo del [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8dbec-115">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
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
  
 <span data-ttu-id="8dbec-116">La configuración de punto de conexión de cliente está compuesta de una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="8dbec-116">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="8dbec-117">El enlace del cliente se configura con el modo de seguridad y el modo de autenticación apropiados.</span><span class="sxs-lookup"><span data-stu-id="8dbec-117">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="8dbec-118">Si se trata de un escenario de varios equipos, asegúrese de que se cambie la dirección del punto de conexión de servicio según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8dbec-118">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
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
  
 <span data-ttu-id="8dbec-119">La implementación del cliente puede establecer el certificado que se debe utilizar, bien sea a través del archivo de configuración o a través de código.</span><span class="sxs-lookup"><span data-stu-id="8dbec-119">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="8dbec-120">El ejemplo siguiente muestra cómo establecer el certificado para utilizar en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8dbec-120">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="8dbec-121">El ejemplo siguiente muestra cómo llamar al servicio en su programa.</span><span class="sxs-lookup"><span data-stu-id="8dbec-121">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="8dbec-122">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8dbec-123">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="8dbec-124">El archivo por lotes Setup.bat incluido con los ejemplos de Message Security permite configurar el cliente y el servidor con los certificados pertinentes para ejecutar una aplicación hospedada que exija seguridad basada en certificado.</span><span class="sxs-lookup"><span data-stu-id="8dbec-124">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="8dbec-125">El archivo por lotes se puede ejecutar en tres modos.</span><span class="sxs-lookup"><span data-stu-id="8dbec-125">The batch file can be run in three modes.</span></span> <span data-ttu-id="8dbec-126">Para ejecutarse en modo de un solo equipo **setup.bat** en un símbolo del sistema para desarrolladores para Visual Studio; para el tipo de modo de servicio **setup.bat servicio**; y para el modo de cliente, escriba **setup.bat cliente**.</span><span class="sxs-lookup"><span data-stu-id="8dbec-126">To run in single-computer mode type **setup.bat** in a Developer Command Prompt for Visual Studio ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="8dbec-127">Utilice el modo de cliente y servidor cuando ejecute el ejemplo en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="8dbec-127">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="8dbec-128">Para obtener más detalles, vea el procedimiento de configuración al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8dbec-128">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="8dbec-129">A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="8dbec-129">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
- <span data-ttu-id="8dbec-130">Crear el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-130">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="8dbec-131">La línea siguiente en el archivo por lotes crea el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-131">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="8dbec-132">El nombre de cliente especificado se utiliza en el nombre del asunto del certificado creado.</span><span class="sxs-lookup"><span data-stu-id="8dbec-132">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="8dbec-133">El certificado se guarda en el almacén `My`, en la ubicación de almacenamiento `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="8dbec-133">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="8dbec-134">Instalar el certificado de cliente en el almacén de certificados de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-134">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="8dbec-135">La línea siguiente del archivo por lotes copia el certificado de cliente en el almacén TrustedPeople del servidor para que el servidor pueda tomar decisiones basadas en la confianza o la ausencia de la misma.</span><span class="sxs-lookup"><span data-stu-id="8dbec-135">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="8dbec-136">Para que un servicio de Windows Communication Foundation (WCF) confíe en un certificado instalado en el almacén TrustedPeople, el modo de validación del certificado de cliente debe establecerse en `PeerOrChainTrust` o `PeerTrust` .</span><span class="sxs-lookup"><span data-stu-id="8dbec-136">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="8dbec-137">Vea el ejemplo de configuración de servicio anterior para obtener información sobre cómo lograrlo con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8dbec-137">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```  
  
- <span data-ttu-id="8dbec-138">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-138">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="8dbec-139">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="8dbec-139">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="8dbec-140">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-140">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="8dbec-141">El certificado se almacena en el almacén LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="8dbec-141">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="8dbec-142">Si el archivo por lotes de Setup.bat se ejecuta con un argumento de servicio (como, **setup.bat servicio**), el% SERVER_NAME% contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-142">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="8dbec-143">De lo contrario, tiene como valor predeterminado el host local.</span><span class="sxs-lookup"><span data-stu-id="8dbec-143">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="8dbec-144">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-144">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="8dbec-145">La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-145">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="8dbec-146">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="8dbec-146">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="8dbec-147">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-147">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="8dbec-148">Conceder permisos sobre la clave privada del certificado.</span><span class="sxs-lookup"><span data-stu-id="8dbec-148">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="8dbec-149">Las siguientes líneas del archivo Setup.bat hacen que el certificado de servidor almacenado en el almacén LocalMachine sea accesible para la cuenta de proceso de trabajo ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8dbec-149">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
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
    > <span data-ttu-id="8dbec-150">Si usa un valor que no es de U. S. Edición en Inglés de Windows, debe modificar el archivo Setup.bat y reemplazar el nombre de cuenta "NT AUTHORITY\NETWORK SERVICE" con su equivalente regional.</span><span class="sxs-lookup"><span data-stu-id="8dbec-150">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8dbec-151">Las herramientas utilizadas en este archivo por lotes se encuentran en C:\Program Files\Microsoft Visual Studio 8\Common7\tools o C:\Program Files\Microsoft SDKs\Windows\v6.0\bin</span><span class="sxs-lookup"><span data-stu-id="8dbec-151">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="8dbec-152">Uno de estos directorios debe estar en su ruta de acceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="8dbec-152">One of these directories must be in your system path.</span></span> <span data-ttu-id="8dbec-153">Si tiene Visual Studio instalado, la manera más fácil de obtener este directorio en su ruta de acceso es abrir el Símbolo del sistema para desarrolladores para Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-153">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="8dbec-154">Haga clic en **Inicio** y, a continuación, seleccione **todos los programas**, **Visual Studio 2012**, **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="8dbec-154">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="8dbec-155">Este símbolo del sistema tiene las rutas de acceso adecuadas ya configuradas.</span><span class="sxs-lookup"><span data-stu-id="8dbec-155">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="8dbec-156">De lo contrario, debe agregar manualmente el directorio correcto a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8dbec-156">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8dbec-157">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-157">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8dbec-158">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="8dbec-158">Check for the following (default) directory before continuing:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8dbec-159">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8dbec-159">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8dbec-160">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="8dbec-160">This sample is located in the following directory:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8dbec-161">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dbec-161">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8dbec-162">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8dbec-162">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="8dbec-163">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8dbec-163">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="8dbec-164">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="8dbec-164">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="8dbec-165">Abra una Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-165">Open a Developer Command Prompt for Visual Studio  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="8dbec-166">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-166">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8dbec-167">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un Símbolo del sistema para desarrolladores para Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-167">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="8dbec-168">Requiere que la variable de entorno path señale al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="8dbec-168">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="8dbec-169">Esta variable de entorno se establece automáticamente dentro de una Símbolo del sistema para desarrolladores para Visual Studio (2010).</span><span class="sxs-lookup"><span data-stu-id="8dbec-169">This environment variable is automatically set within a Developer Command Prompt for Visual Studio (2010).</span></span>  
  
2. <span data-ttu-id="8dbec-170">Escriba la dirección para comprobar el acceso al servicio mediante un explorador `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="8dbec-170">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3. <span data-ttu-id="8dbec-171">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="8dbec-171">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="8dbec-172">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-172">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="8dbec-173">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8dbec-173">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="8dbec-174">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="8dbec-174">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="8dbec-175">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-175">Create a directory on the service computer.</span></span> <span data-ttu-id="8dbec-176">Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8dbec-176">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="8dbec-177">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-177">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="8dbec-178">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="8dbec-178">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="8dbec-179">Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-179">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="8dbec-180">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-180">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="8dbec-181">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-181">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="8dbec-182">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-182">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="8dbec-183">En el servidor, ejecute **setup.bat servicio** en un símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8dbec-183">On the server, run **setup.bat service** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="8dbec-184">Al ejecutar **setup.bat** con el argumento **Service** se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="8dbec-184">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="8dbec-185">Edite Web.config para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-185">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="8dbec-186">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="8dbec-186">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="8dbec-187">En el cliente, ejecute **setup.bat cliente** en un símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8dbec-187">On the client, run **setup.bat client** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="8dbec-188">La ejecución de **setup.bat** con el argumento **Client** crea un certificado de cliente denominado Client.com y exporta el certificado de cliente a un archivo denominado Client. cer.</span><span class="sxs-lookup"><span data-stu-id="8dbec-188">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="8dbec-189">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-189">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="8dbec-190">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-190">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="8dbec-191">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8dbec-191">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="8dbec-192">En el cliente, ejecute ImportServiceCert.bat en un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8dbec-192">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="8dbec-193">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="8dbec-193">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="8dbec-194">En el servidor, ejecute ImportClientCert.bat en un Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8dbec-194">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="8dbec-195">De esta forma se importa el certificado del cliente desde el archivo Client.cer al almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="8dbec-195">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="8dbec-196">En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="8dbec-196">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="8dbec-197">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8dbec-197">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="8dbec-198">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dbec-198">To clean up after the sample</span></span>  
  
- <span data-ttu-id="8dbec-199">Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8dbec-199">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8dbec-200">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="8dbec-200">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="8dbec-201">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="8dbec-201">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="8dbec-202">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="8dbec-202">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
