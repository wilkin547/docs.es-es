---
title: BasicBinding con seguridad de transporte
ms.date: 03/30/2017
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 9591c3556bf38d1af288c2c3c4a465af2c0722eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502694"
---
# <a name="basicbinding-with-transport-security"></a><span data-ttu-id="59ea3-102">BasicBinding con seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="59ea3-102">BasicBinding with Transport Security</span></span>
<span data-ttu-id="59ea3-103">El ejemplo muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="59ea3-103">This sample demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="59ea3-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="59ea3-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59ea3-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="59ea3-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="59ea3-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="59ea3-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="59ea3-107">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="59ea3-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59ea3-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="59ea3-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`  
  
## <a name="sample-details"></a><span data-ttu-id="59ea3-109">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="59ea3-109">Sample Details</span></span>  
 <span data-ttu-id="59ea3-110">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="59ea3-110">By default, the basic binding supports HTTP communication.</span></span> <span data-ttu-id="59ea3-111">El ejemplo muestra cómo habilitar la seguridad de transporte para el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="59ea3-111">The sample shows how to enable transport security for the basic binding.</span></span> <span data-ttu-id="59ea3-112">Antes de ejecutar el ejemplo, se debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web.</span><span class="sxs-lookup"><span data-stu-id="59ea3-112">Before you run the sample, you must create a certificate and assign it by using the Web Server Certificate Wizard.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59ea3-113">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="59ea3-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="59ea3-114">El código de programa en el ejemplo es idéntico de la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) servicio.</span><span class="sxs-lookup"><span data-stu-id="59ea3-114">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="59ea3-115">La definición de punto de conexión y la definición de enlace en los valores de archivo de configuración se han modificado para habilitar la comunicación segura, como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="59ea3-115">The endpoint definition and binding definition in the configuration file settings are modified to enable secure communication, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
   </services>  
  <bindings>  
    <basicHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"/>  
        </security>  
      </binding>  
    </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="59ea3-116">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, una alerta de seguridad aparece cuando se intenta acceder a un HTTPS: dirección en el explorador, como https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="59ea3-116">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an HTTPS: address in your browser, such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="59ea3-117">Para permitir que el cliente de Windows Communication Foundation (WCF) para que funcione con un certificado de prueba, se ha añadido código adicional al cliente para suprimir la alerta de seguridad.</span><span class="sxs-lookup"><span data-stu-id="59ea3-117">To allow the Windows Communication Foundation (WCF) client to work with a test certificate, some additional code is added to the client to suppress the security alert.</span></span> <span data-ttu-id="59ea3-118">Este código y la clase acompañante, no es necesario al utilizar los certificados reales.</span><span class="sxs-lookup"><span data-stu-id="59ea3-118">This code, and the accompanying class, is not necessary when using real certificates.</span></span>  

```csharp
// This code is required only for test certificates such as those   
// created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="59ea3-119">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="59ea3-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="59ea3-120">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="59ea3-120">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="59ea3-121">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="59ea3-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="59ea3-122">Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="59ea3-122">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command:</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="59ea3-123">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59ea3-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="59ea3-124">Asegúrese de que ha llevado a cabo la [instrucciones de instalación de certificado de servidor de Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="59ea3-124">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="59ea3-125">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59ea3-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="59ea3-126">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59ea3-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ea3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="59ea3-127">See Also</span></span>
