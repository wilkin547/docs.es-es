---
title: Seguridad de transporte WS
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
ms.openlocfilehash: 5756327ccd5da9dc4ee41d038715b5630872f800
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006348"
---
# <a name="ws-transport-security"></a><span data-ttu-id="a4a76-102">Seguridad de transporte WS</span><span class="sxs-lookup"><span data-stu-id="a4a76-102">WS Transport Security</span></span>
<span data-ttu-id="a4a76-103">Este ejemplo muestra el uso de la seguridad de transporte de SSL con el enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a4a76-103">This sample demonstrates the use of SSL transport security with the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span> <span data-ttu-id="a4a76-104">De forma predeterminada, el enlace `wsHttpBinding` proporciona la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="a4a76-104">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="a4a76-105">Cuando se configura para la seguridad del transporte, el enlace admite la comunicación de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4a76-105">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="a4a76-106">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="a4a76-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="a4a76-107">`wsHttpBinding` se especifica y se configura en los archivos de configuración de la aplicación para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4a76-107">The `wsHttpBinding` is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4a76-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="a4a76-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4a76-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a4a76-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4a76-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a4a76-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a4a76-111">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a4a76-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4a76-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a4a76-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 <span data-ttu-id="a4a76-113">El código de programa en el ejemplo es idéntico de la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span><span class="sxs-lookup"><span data-stu-id="a4a76-113">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="a4a76-114">Debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web antes de compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4a76-114">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="a4a76-115">La definición de extremo y de enlace en la configuración del archivo de configuración habilitan el modo de seguridad `Transport`, tal y como se muestra en la configuración de ejemplo siguiente para el cliente.</span><span class="sxs-lookup"><span data-stu-id="a4a76-115">The endpoint definition and binding definition in the configuration file settings enable `Transport` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="a4a76-116">La dirección especificada utiliza el esquema https://.</span><span class="sxs-lookup"><span data-stu-id="a4a76-116">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="a4a76-117">La configuración de enlace establece el modo de seguridad en `Transport`.</span><span class="sxs-lookup"><span data-stu-id="a4a76-117">The binding configuration sets the security mode to `Transport`.</span></span> <span data-ttu-id="a4a76-118">Debe especificarse el mismo modo de seguridad en el archivo Web.config del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4a76-118">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="a4a76-119">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, una alerta de seguridad aparece cuando intenta tener acceso a https: dirección, como https://localhost/servicemodelsamples/service.svc, desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="a4a76-119">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="a4a76-120">Para permitir que el cliente de Windows Communication Foundation (WCF) trabajar con un certificado de prueba en su lugar, se agregó código adicional al cliente para suprimir la alerta de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4a76-120">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="a4a76-121">Este código, y la clase que lo acompaña, no son necesarios cuando se usan certificados de producción.</span><span class="sxs-lookup"><span data-stu-id="a4a76-121">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="a4a76-122">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="a4a76-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a4a76-123">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="a4a76-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a4a76-124">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4a76-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a4a76-125">Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a4a76-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="a4a76-126">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a4a76-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="a4a76-127">Asegúrese de que ha realizado la [instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="a4a76-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4. <span data-ttu-id="a4a76-128">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a4a76-128">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="a4a76-129">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a4a76-129">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
