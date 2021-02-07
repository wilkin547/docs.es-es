---
description: 'Más información acerca de: seguridad de mensajes en Message Queue Server'
title: Seguridad de mensajes mediante Message Queuing
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: bfbec02dec11d4f4eb153db942eb12ce4cb595e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752332"
---
# <a name="message-security-over-message-queuing"></a><span data-ttu-id="e4314-103">Seguridad de mensajes mediante Message Queuing</span><span class="sxs-lookup"><span data-stu-id="e4314-103">Message Security over Message Queuing</span></span>

<span data-ttu-id="e4314-104">Este ejemplo muestra cómo implementar una aplicación que utiliza WS-Security con autenticación de certificado X.509v3 para el cliente y que requiere la autenticación del servidor mediante el certificado X.509v3 del servidor sobre MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4314-104">This sample demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span> <span data-ttu-id="e4314-105">En ocasiones es más apropiado utilizar la seguridad del mensaje para garantizar que los mensajes en el almacén de MSMQ permanezcan cifrados y la aplicación pueda realizar su propia autenticación del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4314-105">Message security is sometimes more desirable to ensure that the messages in the MSMQ store stay encrypted and the application can perform its own authentication of the message.</span></span>

 <span data-ttu-id="e4314-106">Este ejemplo se basa en el ejemplo de [enlace de MSMQ de transacciones](transacted-msmq-binding.md) .</span><span class="sxs-lookup"><span data-stu-id="e4314-106">This sample is based on the [Transacted MSMQ Binding](transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="e4314-107">Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="e4314-107">The messages are encrypted and signed.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e4314-108">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4314-108">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e4314-109">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4314-109">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="e4314-110">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="e4314-110">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="e4314-111">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="e4314-111">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="e4314-112">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4314-112">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="e4314-113">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="e4314-113">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="e4314-114">Abra Administrador del servidor en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="e4314-114">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="e4314-115">Expanda la pestaña **características** .</span><span class="sxs-lookup"><span data-stu-id="e4314-115">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="e4314-116">Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nuevo**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="e4314-116">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="e4314-117">Active la casilla **transaccional** .</span><span class="sxs-lookup"><span data-stu-id="e4314-117">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="e4314-118">Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="e4314-118">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="e4314-119">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4314-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="e4314-120">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="e4314-120">To run the sample on the same computer</span></span>

1. <span data-ttu-id="e4314-121">Asegúrese de que la ruta de acceso incluye la carpeta que contiene Makecert.exe y FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="e4314-121">Ensure that the path includes the folder that contains Makecert.exe and FindPrivateKey.exe.</span></span>

2. <span data-ttu-id="e4314-122">Ejecute Setup.bat desde la carpeta de instalación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e4314-122">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="e4314-123">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e4314-123">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4314-124">Asegúrese de que quita los certificados ejecutando Cleanup.bat cuando haya terminado con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e4314-124">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="e4314-125">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="e4314-125">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="e4314-126">Inicie Service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="e4314-126">Launch Service.exe from \service\bin.</span></span>  
  
4. <span data-ttu-id="e4314-127">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="e4314-127">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="e4314-128">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-128">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="e4314-129">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e4314-129">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e4314-130">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="e4314-130">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="e4314-131">Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="e4314-131">Copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
2. <span data-ttu-id="e4314-132">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-132">Create a directory on the client computer for the client binaries.</span></span>  
  
3. <span data-ttu-id="e4314-133">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-133">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="e4314-134">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-134">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
4. <span data-ttu-id="e4314-135">En el servidor, ejecute `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="e4314-135">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="e4314-136">`setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="e4314-136">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
5. <span data-ttu-id="e4314-137">Edite el service.exe.config del servicio para que refleje el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="e4314-137">Edit service's service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
6. <span data-ttu-id="e4314-138">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-138">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
7. <span data-ttu-id="e4314-139">En el cliente, ejecute `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="e4314-139">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="e4314-140">Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.</span><span class="sxs-lookup"><span data-stu-id="e4314-140">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
8. <span data-ttu-id="e4314-141">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="e4314-141">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="e4314-142">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="e4314-142">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  <span data-ttu-id="e4314-143">También debe cambiar el nombre del certificado del servicio para que sea igual que el nombre de dominio completo del equipo del servicio (en el atributo `findValue` del elemento `defaultCertificate` de `serviceCertificate`, bajo `clientCredentials`).</span><span class="sxs-lookup"><span data-stu-id="e4314-143">You must also change the certificate name of the service to be the same as the fully-qualified domain name of the service computer (in the `findValue` attribute in the `defaultCertificate` element of `serviceCertificate` under `clientCredentials`).</span></span>  
  
9. <span data-ttu-id="e4314-144">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e4314-144">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
10. <span data-ttu-id="e4314-145">En el cliente, ejecute `ImportServiceCert.bat`.</span><span class="sxs-lookup"><span data-stu-id="e4314-145">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="e4314-146">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="e4314-146">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
11. <span data-ttu-id="e4314-147">En el servidor, ejecute `ImportClientCert.bat`. De esta manera se importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="e4314-147">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="e4314-148">En el equipo del servicio, inicie Service.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4314-148">On the service computer, launch Service.exe from the command prompt.</span></span>  
  
13. <span data-ttu-id="e4314-149">En el equipo cliente, inicie Client.exe desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4314-149">On the client computer, launch Client.exe from the command prompt.</span></span> <span data-ttu-id="e4314-150">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e4314-150">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="e4314-151">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4314-151">To clean up after the sample</span></span>  
  
- <span data-ttu-id="e4314-152">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e4314-152">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e4314-153">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="e4314-153">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="e4314-154">Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="e4314-154">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="e4314-155">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="e4314-155">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4314-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4314-156">Requirements</span></span>

 <span data-ttu-id="e4314-157">Este ejemplo exige que MSMQ se instale y se ejecute.</span><span class="sxs-lookup"><span data-stu-id="e4314-157">This sample requires that MSMQ is installed and running.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e4314-158">Muestra</span><span class="sxs-lookup"><span data-stu-id="e4314-158">Demonstrates</span></span>

 <span data-ttu-id="e4314-159">El cliente cifra el mensaje mediante la clave pública del servicio y firma el mensaje con su propio certificado.</span><span class="sxs-lookup"><span data-stu-id="e4314-159">The client encrypts the message using the public key of the service and signs the message using its own certificate.</span></span> <span data-ttu-id="e4314-160">El servicio que lee el mensaje de la cola autentica el certificado de cliente con el certificado en su almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="e4314-160">The service reading the message from the queue authenticates the client certificate with the certificate in its trusted people store.</span></span> <span data-ttu-id="e4314-161">Después descifra el mensaje y lo envía a la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e4314-161">It then decrypts the message and dispatches the message to the service operation.</span></span>

 <span data-ttu-id="e4314-162">Dado que el mensaje de Windows Communication Foundation (WCF) se lleva como una carga en el cuerpo del mensaje de MSMQ, el cuerpo permanece cifrado en el almacén de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4314-162">Because the Windows Communication Foundation (WCF) message is carried as a payload in the body of the MSMQ message, the body remains encrypted in the MSMQ store.</span></span> <span data-ttu-id="e4314-163">Esto protege el mensaje de la divulgación no deseada del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4314-163">This secures the message from unwanted disclosure of the message.</span></span> <span data-ttu-id="e4314-164">Tenga en cuenta que el propio MSMQ no sabe si el mensaje que transporta está cifrado.</span><span class="sxs-lookup"><span data-stu-id="e4314-164">Note that MSMQ itself is not aware whether the message it is carrying is encrypted.</span></span>

 <span data-ttu-id="e4314-165">El ejemplo muestra cómo se puede utilizar la autenticación mutua en el nivel de mensaje con MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4314-165">The sample demonstrates how mutual authentication at the message level can be used with MSMQ.</span></span> <span data-ttu-id="e4314-166">Los certificados se intercambian fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="e4314-166">The certificates are exchanged out-of-band.</span></span> <span data-ttu-id="e4314-167">Siempre es el caso de la aplicación con cola porque el servicio y el cliente no tienen que estar al mismo tiempo conectados y ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="e4314-167">This is always the case with queued application because the service and the client do not have to be up and running at the same time.</span></span>

## <a name="description"></a><span data-ttu-id="e4314-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4314-168">Description</span></span>

 <span data-ttu-id="e4314-169">El cliente de ejemplo y el código de servicio son los mismos que el ejemplo de [enlace de MSMQ de transacción](transacted-msmq-binding.md) con una diferencia.</span><span class="sxs-lookup"><span data-stu-id="e4314-169">The sample client and service code are the same as the [Transacted MSMQ Binding](transacted-msmq-binding.md) sample with one difference.</span></span> <span data-ttu-id="e4314-170">En el contrato de operación se anota el nivel de protección, que sugiere que el mensaje se debe firmar y cifrar.</span><span class="sxs-lookup"><span data-stu-id="e4314-170">The operation contract is annotated with protection level, which suggests that the message must be signed and encrypted.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="e4314-171">Para asegurarse de que el mensaje se protege utilizando el token necesario para identificar el servicio y el cliente, App.config contiene la información de la credencial.</span><span class="sxs-lookup"><span data-stu-id="e4314-171">To ensure that the message is secured using the required token to identify the service and client, the App.config contains credential information.</span></span>

 <span data-ttu-id="e4314-172">La configuración del cliente especifica el certificado de servicio para autenticar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e4314-172">The client configuration specifies the service certificate to authenticate the service.</span></span> <span data-ttu-id="e4314-173">Utiliza su almacén LocalMachine como almacén de confianza para confiar en la validez del servicio.</span><span class="sxs-lookup"><span data-stu-id="e4314-173">It uses its LocalMachine store as the trusted store to rely on the validity of the service.</span></span> <span data-ttu-id="e4314-174">También especifica el certificado de cliente que está asociado con el mensaje para la autenticación del servicio del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-174">It also specifies the client certificate that is attached with the message for service authentication of the client.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
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
</configuration>
```

 <span data-ttu-id="e4314-175">Observe que el modo de seguridad se ha definido en "Message" y que ClientCredentialType se ha establecido en "Certificate".</span><span class="sxs-lookup"><span data-stu-id="e4314-175">Note that the security mode is set to Message and the ClientCredentialType is set to Certificate.</span></span>

 <span data-ttu-id="e4314-176">La configuración de servicio incluye un comportamiento de servicio que especifica las credenciales del servicio que se utilizan cuando el cliente autentica el servicio.</span><span class="sxs-lookup"><span data-stu-id="e4314-176">The service configuration includes a service behavior that specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="e4314-177">El nombre de sujeto del certificado de servidor se especifica en el `findValue` atributo en [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="e4314-177">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
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

</configuration>
```

 <span data-ttu-id="e4314-178">El ejemplo muestra cómo controlar la autenticación mediante la configuración y cómo obtener la identidad del autor de la llamada desde el contexto de seguridad, tal y como se muestra en el siguiente código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e4314-178">The sample demonstrates controlling authentication using configuration, and how to obtain the caller’s identity from the security context, as shown in the following sample code:</span></span>

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 <span data-ttu-id="e4314-179">Cuando se ejecuta, el código de servicio muestra la identificación del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-179">When run, the service code displays the client identification.</span></span> <span data-ttu-id="e4314-180">Se proporciona a continuación la siguiente salida de ejemplo desde el código de servicio:</span><span class="sxs-lookup"><span data-stu-id="e4314-180">The following is a sample output from the service code:</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a><span data-ttu-id="e4314-181">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4314-181">Comments</span></span>

- <span data-ttu-id="e4314-182">Crear el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-182">Creating the client certificate.</span></span>

     <span data-ttu-id="e4314-183">La línea siguiente en el archivo por lotes crea el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-183">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="e4314-184">El nombre de cliente especificado se utiliza en el nombre del asunto del certificado creado.</span><span class="sxs-lookup"><span data-stu-id="e4314-184">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="e4314-185">El certificado se guarda en el almacén `My`, en la ubicación de almacenamiento `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="e4314-185">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="e4314-186">Instalar el certificado del cliente en el almacén de certificados de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="e4314-186">Installing the client certificate into server’s trusted certificate store.</span></span>

     <span data-ttu-id="e4314-187">La línea siguiente del archivo por lotes copia el certificado de cliente en el almacén TrustedPeople del servidor para que el servidor pueda tomar decisiones basadas en la confianza o la ausencia de la misma.</span><span class="sxs-lookup"><span data-stu-id="e4314-187">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="e4314-188">Para que un servicio de Windows Communication Foundation (WCF) confíe en un certificado instalado en el almacén TrustedPeople, el modo de validación del certificado de cliente debe establecerse en `PeerOrChainTrust` o en `PeerTrust` valor.</span><span class="sxs-lookup"><span data-stu-id="e4314-188">For a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust` value.</span></span> <span data-ttu-id="e4314-189">Vea el ejemplo de configuración de servicio anterior para obtener información sobre cómo puede hacerse usando un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e4314-189">See the previous service configuration sample to learn how this can be done using a configuration file.</span></span>

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="e4314-190">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="e4314-190">Creating the server certificate.</span></span>

     <span data-ttu-id="e4314-191">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar:</span><span class="sxs-lookup"><span data-stu-id="e4314-191">The following lines from the Setup.bat batch file create the server certificate to be used:</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="e4314-192">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="e4314-192">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="e4314-193">El certificado se almacena en el almacén LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="e4314-193">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="e4314-194">Si el archivo por lotes de instalación se ejecuta con un argumento de servicio (como `setup.bat service` ), el% SERVER_NAME% contiene el nombre de dominio completo del equipo. De lo contrario, el valor predeterminado es localhost.</span><span class="sxs-lookup"><span data-stu-id="e4314-194">If the setup batch file is run with an argument of service (such as, `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.Otherwise it defaults to localhost</span></span>

- <span data-ttu-id="e4314-195">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-195">Installing server certificate into the client’s trusted certificate store.</span></span>

     <span data-ttu-id="e4314-196">La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="e4314-196">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="e4314-197">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="e4314-197">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="e4314-198">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="e4314-198">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="e4314-199">Si usa un valor que no es de U. S. Edición en Inglés de Microsoft Windows debe modificar el archivo Setup.bat y reemplazar el nombre de cuenta "NT AUTHORITY\NETWORK SERVICE" con su equivalente regional.</span><span class="sxs-lookup"><span data-stu-id="e4314-199">If you are using a non-U.S. English edition of Microsoft Windows you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4314-200">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e4314-200">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e4314-201">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e4314-201">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e4314-202">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e4314-202">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e4314-203">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e4314-203">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`
