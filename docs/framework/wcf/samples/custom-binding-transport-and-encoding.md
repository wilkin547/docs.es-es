---
title: Transporte y codificación de enlace personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 3b3a0f1b52afce495ca41a426ebc9e57314d8254
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592533"
---
# <a name="custom-binding-transport-and-encoding"></a><span data-ttu-id="f2426-102">Transporte y codificación de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="f2426-102">Custom Binding Transport and Encoding</span></span>
<span data-ttu-id="f2426-103">Un enlace personalizado se define mediante una lista ordenada de elementos de enlace discretos.</span><span class="sxs-lookup"><span data-stu-id="f2426-103">A custom binding is defined by an ordered list of discrete binding elements.</span></span> <span data-ttu-id="f2426-104">Este ejemplo muestra cómo configurar un enlace personalizado con varios elementos de codificación de mensajes y transporte.</span><span class="sxs-lookup"><span data-stu-id="f2426-104">This sample demonstrates how to configure a custom binding with various transport and message encoding elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2426-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f2426-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f2426-106">Este ejemplo se basa en el [propio host](self-host.md)y se ha modificado para configurar tres puntos de conexión para que admitan transportes http, TCP y NamedPipe con enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="f2426-106">This sample is based on the [Self-Host](self-host.md), and has been modified to configure three endpoints to support HTTP, TCP, and NamedPipe transports with custom bindings.</span></span> <span data-ttu-id="f2426-107">La configuración del cliente se modificó de igual forma y el código de cliente cambió para comunicarse con cada uno de los tres puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="f2426-107">The client configuration was similarly modified, and the client code changed to communicate with each of the three endpoints.</span></span>  
  
 <span data-ttu-id="f2426-108">El ejemplo muestra cómo configurar un enlace personalizado que admite un transporte determinado y la codificación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f2426-108">The sample demonstrates a how to configure a custom binding that supports a particular transport and message encoding.</span></span> <span data-ttu-id="f2426-109">Esto se logra configurando un transporte y una codificación de mensajes para el elemento `binding`.</span><span class="sxs-lookup"><span data-stu-id="f2426-109">This is accomplished by configuring a transport and a message encoding for the `binding` element.</span></span> <span data-ttu-id="f2426-110">El orden de los elementos de enlace es importante en la definición de un enlace personalizado, ya que cada uno representa una capa en la pila del canal (vea [enlaces personalizados](../extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="f2426-110">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../extending/custom-bindings.md)).</span></span> <span data-ttu-id="f2426-111">Este ejemplo configura tres enlaces personalizados: un transporte HTTP con codificación de texto, un transporte TCP con codificación de texto y un transporte NamedPipe con una codificación binaria.</span><span class="sxs-lookup"><span data-stu-id="f2426-111">This sample configures three custom bindings: an HTTP transport with text encoding, a TCP transport with text encoding, and a NamedPipe transport with a binary encoding.</span></span>  
  
 <span data-ttu-id="f2426-112">La configuración de servicio define los enlaces personalizados de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="f2426-112">The service configuration defines the custom bindings as follows:</span></span>  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="f2426-113">Al ejecutar el ejemplo, las solicitudes de operación y las respuestas se muestran en la ventana de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="f2426-113">When you run the sample, the operation requests and responses are displayed in both the service and client console window.</span></span> <span data-ttu-id="f2426-114">El cliente se comunica con cada uno de los tres puntos de conexión, teniendo acceso primero a HTTP, después a TCP y finalmente a NamedPipe.</span><span class="sxs-lookup"><span data-stu-id="f2426-114">The client communicates with each of the three endpoints, accessing first HTTP, then TCP, and finally NamedPipe.</span></span> <span data-ttu-id="f2426-115">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="f2426-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="f2426-116">El enlace `namedPipeTransport` no admite las operaciones de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="f2426-116">The `namedPipeTransport` binding does not support machine-to-machine operations.</span></span> <span data-ttu-id="f2426-117">Sólo se utiliza para la comunicación en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="f2426-117">It is used only for communication on the same machine.</span></span> <span data-ttu-id="f2426-118">Por consiguiente, al ejecutar el ejemplo en un escenario con varios equipos, marque como comentarios las líneas siguientes en el archivo de código de cliente:</span><span class="sxs-lookup"><span data-stu-id="f2426-118">Therefore, when running the sample in a cross-machine scenario, comment out the following lines in the client code file:</span></span>  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> <span data-ttu-id="f2426-119">Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="f2426-119">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f2426-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2426-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f2426-121">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2426-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="f2426-122">Para compilar la edición de C#, C++ o Visual Basic .NET de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2426-122">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="f2426-123">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2426-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f2426-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f2426-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f2426-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f2426-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f2426-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f2426-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f2426-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f2426-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
