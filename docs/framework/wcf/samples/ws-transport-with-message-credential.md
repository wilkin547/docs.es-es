---
title: Transporte WS con credencial de mensaje
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b954e2d19f601476876beef6482ca10eb3f113b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="b0563-102">Transporte WS con credencial de mensaje</span><span class="sxs-lookup"><span data-stu-id="b0563-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="b0563-103">Este ejemplo muestra el uso de la seguridad de transporte de SSL en combinación con la credencial del cliente que se lleva en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0563-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="b0563-104">El ejemplo usa el enlace `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b0563-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="b0563-105">De forma predeterminada, el enlace `wsHttpBinding` proporciona la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="b0563-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="b0563-106">Cuando se configura para la seguridad del transporte, el enlace admite la comunicación de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b0563-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="b0563-107">HTTPS proporciona confidencialidad y protección de integridad para los mensajes que se transmiten a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="b0563-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="b0563-108">Sin embargo, el conjunto de mecanismos de autenticación que se pueden usar para autenticar el cliente en el servicio está limitado a lo que admite el transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b0563-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="b0563-109"> ofrece un modo de seguridad `TransportWithMessageCredential` que está diseñado para superar esta limitación.</span><span class="sxs-lookup"><span data-stu-id="b0563-109"> offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="b0563-110">Cuando se configura este modo de seguridad, la seguridad de transporte se utiliza para proporcionar confidencialidad e integridad para los mensajes transmitidos y realizar la autenticación del servicio.</span><span class="sxs-lookup"><span data-stu-id="b0563-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="b0563-111">Sin embargo, la autenticación del cliente se realiza colocando la credencial del cliente directamente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b0563-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="b0563-112">Esto le permite utilizar cualquier tipo de credencial que es compatible con el modo de seguridad de mensajes para la autenticación de cliente manteniendo la ventaja de rendimiento del modo de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="b0563-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="b0563-113">En este ejemplo, se utiliza un tipo de credencial `UserName` para autenticar el cliente con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b0563-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="b0563-114">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="b0563-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="b0563-115">Se especifica y se configura el enlace `wsHttpBinding` en los archivos de configuración de la aplicación para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="b0563-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0563-116">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="b0563-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b0563-117">El código de programa en el ejemplo es casi idéntico de la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) servicio.</span><span class="sxs-lookup"><span data-stu-id="b0563-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="b0563-118">Hay una operación adicional proporcionada por el contrato de servicios: `GetCallerIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b0563-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="b0563-119">Esta operación devuelve el nombre de la identidad del autor de la llamada a éste.</span><span class="sxs-lookup"><span data-stu-id="b0563-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="b0563-120">Debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web antes de compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b0563-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="b0563-121">La definición de extremo y de enlace en la configuración del archivo de configuración habilitan el modo de seguridad `TransportWithMessageCredential`, tal y como se muestra en la configuración de ejemplo siguiente para el cliente.</span><span class="sxs-lookup"><span data-stu-id="b0563-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="b0563-122">La dirección especificada utiliza el esquema https://.</span><span class="sxs-lookup"><span data-stu-id="b0563-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="b0563-123">La configuración de enlace establece el modo de seguridad en `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="b0563-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="b0563-124">Debe especificarse el mismo modo de seguridad en el archivo Web.config del servicio.</span><span class="sxs-lookup"><span data-stu-id="b0563-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="b0563-125">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, una alerta de seguridad aparece cuando se intenta acceder a un https: dirección, como https://localhost/servicemodelsamples/service.svc, desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="b0563-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="b0563-126">Para permitir al cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trabajar con un certificado de prueba, se ha añadido código adicional al cliente para suprimir la alerta de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b0563-126">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="b0563-127">Este código, y la clase que lo acompaña, no son necesarios cuando se usan certificados de producción.</span><span class="sxs-lookup"><span data-stu-id="b0563-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="b0563-128">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="b0563-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b0563-129">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b0563-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0563-130">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0563-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b0563-131">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0563-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b0563-132">Asegúrese de que ha llevado a cabo la [instrucciones de instalación de certificado de servidor de Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="b0563-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="b0563-133">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0563-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="b0563-134">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0563-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0563-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0563-135">See Also</span></span>
