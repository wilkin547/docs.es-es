---
title: Extremo personalizado de metadatos seguros
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
ms.openlocfilehash: d699c8dedfec3068bf0fc1504b47d78fde1988dc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240906"
---
# <a name="custom-secure-metadata-endpoint"></a><span data-ttu-id="7ef3e-102">Extremo personalizado de metadatos seguros</span><span class="sxs-lookup"><span data-stu-id="7ef3e-102">Custom Secure Metadata Endpoint</span></span>

<span data-ttu-id="7ef3e-103">Este ejemplo muestra cómo implementar un servicio con un extremo de metadatos seguro que utiliza uno de los enlaces de intercambio que no son de metadatos y cómo configurar la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) o clientes para capturar los metadatos de este extremo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-103">This sample demonstrates how to implement a service with a secure metadata endpoint that uses one of the non-metadata exchange bindings, and how to configure [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) or clients to fetch the metadata from such a metadata endpoint.</span></span> <span data-ttu-id="7ef3e-104">Hay dos enlaces proporcionados por el sistema disponibles para exponer extremos de metadatos: mexHttpBinding y mexHttpsBinding.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-104">There are two system-provided bindings available for exposing metadata endpoints: mexHttpBinding and mexHttpsBinding.</span></span> <span data-ttu-id="7ef3e-105">mexHttpBinding se usa para exponer un extremo de metadatos sobre HTTP de una manera no segura.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-105">mexHttpBinding is used to expose a metadata endpoint over HTTP in a non-secure manner.</span></span> <span data-ttu-id="7ef3e-106">mexHttpsBinding se usa para exponer un extremo de metadatos sobre HTTPS de una manera no segura.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-106">mexHttpsBinding is used to expose a metadata endpoint over HTTPS in a secure manner.</span></span> <span data-ttu-id="7ef3e-107">En este ejemplo se muestra cómo exponer un extremo de metadatos seguro mediante el objeto <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-107">This sample illustrates how to expose a secure metadata endpoint using the <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="7ef3e-108">Desearía hacer esto cuando desee cambiar la configuración de seguridad en el enlace, pero no desee usar HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-108">You would want to do this when you want to change the security settings on the binding, but you do not want to use HTTPS.</span></span> <span data-ttu-id="7ef3e-109">Si utiliza mexHttpsBinding, su extremo de metadatos será seguro, pero no hay ninguna manera de modificar la configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-109">If you use the mexHttpsBinding your metadata endpoint will be secure, but there is no way to modify the binding settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ef3e-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="7ef3e-111">Servicio</span><span class="sxs-lookup"><span data-stu-id="7ef3e-111">Service</span></span>  

 <span data-ttu-id="7ef3e-112">El servicio en este ejemplo tiene dos extremos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-112">The service in this sample has two endpoints.</span></span> <span data-ttu-id="7ef3e-113">El punto de conexión de la aplicación sirve el contrato `ICalculator` en `WSHttpBinding` con `ReliableSession` habilitados y seguridad `Message` utilizando certificados.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-113">The application endpoint serves the `ICalculator` contract on a `WSHttpBinding` with `ReliableSession` enabled and `Message` security using certificates.</span></span> <span data-ttu-id="7ef3e-114">El punto de conexión de metadatos también utiliza `WSHttpBinding`, con la misma configuración de seguridad pero sin `ReliableSession`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-114">The metadata endpoint also uses `WSHttpBinding`, with the same security settings but with no `ReliableSession`.</span></span> <span data-ttu-id="7ef3e-115">Aquí está la configuración pertinente:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-115">Here is the relevant configuration:</span></span>  
  
```xml  
<services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 <span data-ttu-id="7ef3e-116">En muchos de los otros ejemplos, el extremo de metadatos utiliza el `mexHttpBinding`predeterminado, que no es seguro.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-116">In many of the other samples, the metadata endpoint uses the default `mexHttpBinding`, which is not secure.</span></span> <span data-ttu-id="7ef3e-117">Aquí los metadatos se protegen utilizando `WSHttpBinding` con seguridad `Message`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-117">Here the metadata is secured using `WSHttpBinding` with `Message` security.</span></span> <span data-ttu-id="7ef3e-118">Para que los clientes de los metadatos recuperen estos metadatos, se deben configurar con un enlace correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-118">In order for metadata clients to retrieve this metadata, they must be configured with a matching binding.</span></span> <span data-ttu-id="7ef3e-119">Este ejemplo muestra dos clientes de este tipo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-119">This sample demonstrates two such clients.</span></span>  
  
 <span data-ttu-id="7ef3e-120">El primer cliente utiliza Svcutil.exe para capturar los metadatos y generar en tiempo de diseño código y configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-120">The first client uses Svcutil.exe to fetch the metadata and generate client code and configuration at design time.</span></span> <span data-ttu-id="7ef3e-121">Dado que el servicio utiliza un enlace no predeterminado para los metadatos, se debe configurar la herramienta Svcutil.exe específicamente para que pueda recibir los metadatos del servicio utilizando ese enlace.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-121">Because the service uses a non-default binding for the metadata, the Svcutil.exe tool must be specifically configured so that it can get the metadata from the service using that binding.</span></span>  
  
 <span data-ttu-id="7ef3e-122">El segundo cliente utiliza `MetadataResolver` para capturar dinámicamente los metadatos para un contrato conocido y a continuación, invocar las operaciones en el cliente generado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-122">The second client uses the `MetadataResolver` to dynamically fetch the metadata for a known contract and then invoke operations on the dynamically generated client.</span></span>  
  
## <a name="svcutil-client"></a><span data-ttu-id="7ef3e-123">Cliente de Svcutil</span><span class="sxs-lookup"><span data-stu-id="7ef3e-123">Svcutil client</span></span>  

 <span data-ttu-id="7ef3e-124">Al utilizar el enlace predeterminado para hospedar su punto de conexión `IMetadataExchange`, puede ejecutar Svcutil.exe con la dirección de ese punto de conexión:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-124">When using the default binding to host your `IMetadataExchange` endpoint, you can run Svcutil.exe with the address of that endpoint:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="7ef3e-125">y funciona.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-125">and it works.</span></span> <span data-ttu-id="7ef3e-126">Pero en este ejemplo, el servidor utiliza un punto de conexión no predeterminado para hospedar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-126">But in this sample, the server uses a non-default endpoint to host the metadata.</span></span> <span data-ttu-id="7ef3e-127">Así que deben indicar a Svcutil.exe que utilice el enlace correcto.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-127">So Svcutil.exe must be instructed to use the correct binding.</span></span> <span data-ttu-id="7ef3e-128">Esto se puede hacer utilizando un archivo Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-128">This can be done using a Svcutil.exe.config file.</span></span>  
  
 <span data-ttu-id="7ef3e-129">El archivo Svcutil.exe.config se parece un archivo de configuración de cliente normal.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-129">The Svcutil.exe.config file looks like a normal client configuration file.</span></span> <span data-ttu-id="7ef3e-130">Los únicos aspectos raros son el nombre de punto de conexión del cliente y su contrato:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-130">The only unusual aspects are the client endpoint name and contract:</span></span>  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="7ef3e-131">El nombre de extremo debe ser el nombre del esquema de la dirección donde se hospedan los metadatos y el contrato del extremo debe ser `IMetadataExchange`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-131">The endpoint name must be the name of the scheme of the address where the metadata is hosted and the endpoint contract must be `IMetadataExchange`.</span></span> <span data-ttu-id="7ef3e-132">Así, cuando Svcutil.exe se ejecuta con una línea de comandos como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-132">Thus, when Svcutil.exe is run with a command-line such as the following:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="7ef3e-133">busca el punto de conexión denominado "http" y `IMetadataExchange` del contrato para configurar el enlace y comportamiento del intercambio de la comunicación con el punto de conexión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-133">it looks for the endpoint named "http" and contract `IMetadataExchange` to configure the binding and behavior of the communication exchange with the metadata endpoint.</span></span> <span data-ttu-id="7ef3e-134">El resto del archivo Svcutil.exe.config en el ejemplo especifica las credenciales de comportamiento y configuración de enlace para hacer que coincida con la configuración del servidor del punto de conexión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-134">The rest of the Svcutil.exe.config file in the sample specifies the binding configuration and behavior credentials to match the server's configuration of the metadata endpoint.</span></span>  
  
 <span data-ttu-id="7ef3e-135">Para que Svcutil.exe recoja la configuración en Svcutil.exe.config, Svcutil.exe debe estar en el mismo directorio que el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-135">In order for Svcutil.exe to pick up the configuration in Svcutil.exe.config, Svcutil.exe must be in the same directory as the configuration file.</span></span> <span data-ttu-id="7ef3e-136">Como resultado, debe copiar Svcutil.exe de su ubicación de la instalación en el directorio que contiene el archivo Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-136">As a result, you must copy Svcutil.exe from its install location to the directory that contains the Svcutil.exe.config file.</span></span> <span data-ttu-id="7ef3e-137">Entonces, desde ese directorio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-137">Then from that directory, run the following command:</span></span>  
  
```console  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="7ef3e-138">El ". \\ " inicial garantiza que se ejecuta la copia de Svcutil.exe en este directorio (el que tiene un Svcutil.exe.config correspondiente).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-138">The leading ".\\" ensures that the copy of Svcutil.exe in this directory (the one which has a corresponding Svcutil.exe.config) is run.</span></span>  
  
## <a name="metadataresolver-client"></a><span data-ttu-id="7ef3e-139">Cliente de MetadataResolver</span><span class="sxs-lookup"><span data-stu-id="7ef3e-139">MetadataResolver client</span></span>  

 <span data-ttu-id="7ef3e-140">Si el cliente conoce el contrato y cómo hablar en tiempo de diseño con los metadatos, el cliente puede averiguar dinámicamente el enlace y dirección de los extremos de la aplicación utilizando `MetadataResolver`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-140">If the client knows the contract and how to talk to the metadata at design time, the client can dynamically find out the binding and address of application endpoints using the `MetadataResolver`.</span></span> <span data-ttu-id="7ef3e-141">Este cliente de ejemplo demuestra esto mostrando cómo configurar el enlace y las credenciales utilizadas por `MetadataResolver` creando y configurando `MetadataExchangeClient`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-141">This sample client demonstrates this, showing how to configure the binding and credentials used by `MetadataResolver` by creating and configuring a `MetadataExchangeClient`.</span></span>  
  
 <span data-ttu-id="7ef3e-142">El mismo enlace e información del certificado que aparecieron en Svcutil.exe.config se pueden especificar imperiosamente en `MetadataExchangeClient`:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-142">The same binding and certificate information that appeared in Svcutil.exe.config can be specified imperatively on the `MetadataExchangeClient`:</span></span>  
  
```csharp  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 <span data-ttu-id="7ef3e-143">Con `mexClient` configurado, podemos enumerar los contratos en los que estamos interesados y utilizar `MetadataResolver` para capturar una lista de puntos de conexión con esos contratos:</span><span class="sxs-lookup"><span data-stu-id="7ef3e-143">With the `mexClient` configured, we can enumerate the contracts we are interested in, and use `MetadataResolver` to fetch a list of endpoints with those contracts:</span></span>  
  
```csharp  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts = new Collection<ContractDescription>();  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints = MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 <span data-ttu-id="7ef3e-144">Finalmente, podemos utilizar la información de esos extremos para inicializar el enlace y la dirección de `ChannelFactory` utilizadas para crear los canales para comunicarse con los extremos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-144">Finally we can use the information from those endpoints to initialize the binding and address of a `ChannelFactory` used to create channels to communicate with the application endpoints.</span></span>  
  
```csharp  
ChannelFactory<ICalculator> cf = new ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 <span data-ttu-id="7ef3e-145">El punto clave de este cliente de ejemplo es mostrar eso, si está utilizando `MetadataResolver`, y debe especificar enlaces personalizados o comportamientos para la comunicación de intercambio de metadatos, puede utilizar `MetadataExchangeClient` para especificar esos valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-145">The key point of this sample client is to demonstrate that, if you are using `MetadataResolver`, and you must specify custom bindings or behaviors for the metadata exchange communication, you can use a `MetadataExchangeClient` to specify those custom settings.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="7ef3e-146">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ef3e-146">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="7ef3e-147">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-147">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7ef3e-148">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-148">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="7ef3e-149">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="7ef3e-149">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="7ef3e-150">Ejecute Setup.bat desde la carpeta de instalación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-150">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="7ef3e-151">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-151">This installs all the certificates required for running the sample.</span></span> <span data-ttu-id="7ef3e-152">Tenga en cuenta que Setup.bat usa la herramienta de FindPrivateKey.exe, que se instala al ejecutar setupCertTool.bat desde [el procedimiento de instalación único para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-152">Note that Setup.bat uses the FindPrivateKey.exe tool, which is installed by running setupCertTool.bat from [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7ef3e-153">Ejecutar la aplicación cliente desde \MetadataResolverClient\bin o \SvcutilClient\bin.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-153">Run the client application from \MetadataResolverClient\bin or \SvcutilClient\bin.</span></span> <span data-ttu-id="7ef3e-154">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-154">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="7ef3e-155">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-155">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
4. <span data-ttu-id="7ef3e-156">Quite los certificados ejecutando Cleanup.bat cuando haya finalizado con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-156">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="7ef3e-157">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-157">Other security samples use the same certificates.</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="7ef3e-158">Para ejecutar el ejemplo en los equipos</span><span class="sxs-lookup"><span data-stu-id="7ef3e-158">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="7ef3e-159">En el servidor, ejecute `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-159">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="7ef3e-160">Al ejecutar `setup.bat` con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
2. <span data-ttu-id="7ef3e-161">En el servidor, edite Web.config para reflejar el nuevo nombre del certificado.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-161">On the server, edit Web.config to reflect the new certificate name.</span></span> <span data-ttu-id="7ef3e-162">Es decir, cambie el `findValue` atributo del [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) elemento al nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-162">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the machine.</span></span>  
  
3. <span data-ttu-id="7ef3e-163">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-163">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
4. <span data-ttu-id="7ef3e-164">En el cliente, ejecute `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-164">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="7ef3e-165">Al ejecutar `setup.bat` con el `client` argumento se crea un certificado de cliente denominado Client.com y se exporta el certificado de cliente a un archivo denominado Client. cer.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-165">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5. <span data-ttu-id="7ef3e-166">En el archivo App.config de `MetadataResolverClient` en el equipo cliente, cambie el valor de la dirección del extremo mex para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-166">In the App.config file of the `MetadataResolverClient` on the client machine, change the address value of the mex endpoint to match the new address of your service.</span></span> <span data-ttu-id="7ef3e-167">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-167">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="7ef3e-168">Cambie también la cadena "localhost" en el archivo metadataResolverClient.cs por el nuevo nombre del certificado del servicio (el nombre de dominio completo del servidor).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-168">Also change the occurrence of "localhost" in the metadataResolverClient.cs file to the new service certificate name (the fully-qualified domain name of the server).</span></span> <span data-ttu-id="7ef3e-169">Haga lo mismo para App.config en el proyecto SvcutilClient.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-169">Do the same thing for the App.config of the SvcutilClient project.</span></span>  
  
6. <span data-ttu-id="7ef3e-170">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-170">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7. <span data-ttu-id="7ef3e-171">En el cliente, ejecute `ImportServiceCert.bat`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-171">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="7ef3e-172">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-172">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8. <span data-ttu-id="7ef3e-173">En el servidor, ejecute `ImportClientCert.bat`. De esta manera se importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-173">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="7ef3e-174">En el equipo del servicio, compile el proyecto de servicio en Visual Studio y seleccione la página de ayuda en un explorador web para comprobar que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-174">On the service machine, build the service project in Visual Studio and select the help page in a web browser to verify that it is running.</span></span>  
  
10. <span data-ttu-id="7ef3e-175">En el equipo cliente, ejecute MetadataResolverClient o SvcutilClient desde VS.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-175">On the client machine, run the MetadataResolverClient or the SvcutilClient from VS.</span></span>  
  
    1. <span data-ttu-id="7ef3e-176">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="7ef3e-176">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="7ef3e-177">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ef3e-177">To clean up after the sample</span></span>  
  
- <span data-ttu-id="7ef3e-178">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-178">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7ef3e-179">Este script no quita los certificados del servicio en un cliente cuando se ejecuta este ejemplo en los equipos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-179">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="7ef3e-180">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-180">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="7ef3e-181">Para ello, utilice el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span></span> <span data-ttu-id="7ef3e-182">Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-182">For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7ef3e-183">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7ef3e-184">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-184">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7ef3e-185">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7ef3e-186">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7ef3e-186">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`
