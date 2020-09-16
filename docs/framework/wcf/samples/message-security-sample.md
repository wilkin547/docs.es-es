---
title: Ejemplo de seguridad de mensaje
ms.date: 03/30/2017
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
ms.openlocfilehash: 02e758633f810d785c914152cbd4fbe687bea4f9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558633"
---
# <a name="message-security-sample"></a><span data-ttu-id="27e64-102">Ejemplo de seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="27e64-102">Message Security Sample</span></span>
<span data-ttu-id="27e64-103">Este ejemplo muestra cómo implementar una aplicación que utiliza `basicHttpBinding` y seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="27e64-103">This sample demonstrates how to implement an application that uses the `basicHttpBinding` and message security.</span></span> <span data-ttu-id="27e64-104">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="27e64-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27e64-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="27e64-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="27e64-106">El modo de seguridad de `basicHttpBinding` puede establecerse en los valores siguientes: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` y `None`.</span><span class="sxs-lookup"><span data-stu-id="27e64-106">The security mode of `basicHttpBinding` can be set to the following values: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` and `None`.</span></span> <span data-ttu-id="27e64-107">En el siguiente archivo App.config del servicio del ejemplo, la definición de extremo especifica `basicHttpBinding` y hace referencia una configuración de enlace denominada `Binding1`, como se muestra en la configuración del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27e64-107">In the following sample service App.config file, the endpoint definition specifies the `basicHttpBinding` and references a binding configuration named `Binding1`, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="27e64-108">La configuración de enlace establece el `mode` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) en `Message` y establece el `clientCredentialType` atributo de [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) en `Certificate` como se muestra en la configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27e64-108">The binding configuration sets the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message` and sets the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) to `Certificate` as shown in the following sample configuration:</span></span>  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="27e64-109">El certificado que el servicio utiliza para autenticarse al cliente se establece en la sección de comportamientos del archivo de configuración bajo el elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="27e64-109">The certificate that the service uses to authenticate itself to the client is set in the behaviors section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="27e64-110">El modo de la validación que se aplica al certificado que el cliente utiliza para autenticarse al servicio también se establece en la sección de comportamientos bajo el elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="27e64-110">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the behaviors section under the `clientCertificate` element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="27e64-111">El mismo enlace y detalles de seguridad se especifican en el archivo de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-111">The same binding and security details are specified in the client configuration file.</span></span>  
  
 <span data-ttu-id="27e64-112">La identidad del llamador se muestra en la ventana de la consola del servicio utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="27e64-112">The identity of the caller is displayed in the service console window by using the following code:</span></span>  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 <span data-ttu-id="27e64-113">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="27e64-114">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-114">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="27e64-115">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="27e64-115">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="27e64-116">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="27e64-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="27e64-117">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="27e64-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="27e64-118">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="27e64-118">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="27e64-119">Ejecute Setup.bat desde la carpeta de instalación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="27e64-119">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="27e64-120">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="27e64-120">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="27e64-121">El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="27e64-121">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="27e64-122">Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="27e64-122">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="27e64-123">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="27e64-123">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
2. <span data-ttu-id="27e64-124">Ejecute la aplicación de servicio desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="27e64-124">Run the service application from \service\bin.</span></span>  
  
3. <span data-ttu-id="27e64-125">Ejecute la aplicación cliente desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="27e64-125">Run the client application from \client\bin.</span></span> <span data-ttu-id="27e64-126">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-126">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="27e64-127">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="27e64-127">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
5. <span data-ttu-id="27e64-128">Quite los certificados ejecutando Cleanup.bat cuando haya finalizado con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="27e64-128">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="27e64-129">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="27e64-129">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="27e64-130">Para ejecutar el ejemplo en los equipos</span><span class="sxs-lookup"><span data-stu-id="27e64-130">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="27e64-131">Cree un directorio en el equipo del servicio para los binarios del servicio.</span><span class="sxs-lookup"><span data-stu-id="27e64-131">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="27e64-132">Copie los archivos del programa de servicio en el directorio de servicio situado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="27e64-132">Copy the service program files to the service directory on the server.</span></span> <span data-ttu-id="27e64-133">Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el servidor.</span><span class="sxs-lookup"><span data-stu-id="27e64-133">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the server.</span></span>  
  
3. <span data-ttu-id="27e64-134">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-134">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="27e64-135">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-135">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="27e64-136">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-136">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="27e64-137">En el servidor, ejecute `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="27e64-137">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="27e64-138">Al ejecutar `setup.bat` con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="27e64-138">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="27e64-139">Edite Service.exe.config para reflejar el nuevo nombre del certificado (en el `findValue` atributo en el [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) elemento), que es igual que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="27e64-139">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) element) which is the same as the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="27e64-140">También cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar de `.` del host local</span><span class="sxs-lookup"><span data-stu-id="27e64-140">Also change the value of the base address to specify a fully-qualified machine name instead of localhost`.`</span></span>  
  
7. <span data-ttu-id="27e64-141">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="27e64-141">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="27e64-142">En el cliente, ejecute `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="27e64-142">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="27e64-143">Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.</span><span class="sxs-lookup"><span data-stu-id="27e64-143">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="27e64-144">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="27e64-144">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="27e64-145">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="27e64-145">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="27e64-146">Cambie también el `findValue` atributo de [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) al nuevo nombre del certificado de servicio, que es el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="27e64-146">Also change the `findValue` attribute of the [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) to the new service certificate name which is the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="27e64-147">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="27e64-147">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="27e64-148">En el cliente, ejecute ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="27e64-148">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="27e64-149">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="27e64-149">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="27e64-150">En el servidor, ejecute ImportClientCert.bat. Esto importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="27e64-150">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="27e64-151">En el equipo del servicio, ejecute Service.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="27e64-151">On the service machine, run Service.exe from a command prompt.</span></span>  
  
14. <span data-ttu-id="27e64-152">En el equipo cliente, inicie Client.exe desde la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="27e64-152">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
    1. <span data-ttu-id="27e64-153">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="27e64-153">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="27e64-154">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="27e64-154">To clean up after the sample</span></span>  
  
- <span data-ttu-id="27e64-155">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="27e64-155">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="27e64-156">Este script no quita los certificados del servicio en un cliente cuando se ejecuta este ejemplo en los equipos.</span><span class="sxs-lookup"><span data-stu-id="27e64-156">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="27e64-157">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="27e64-157">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="27e64-158">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="27e64-158">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="27e64-159">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="27e64-159">The samples may already be installed on your machine.</span></span> <span data-ttu-id="27e64-160">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="27e64-160">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="27e64-161">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="27e64-161">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="27e64-162">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="27e64-162">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`
