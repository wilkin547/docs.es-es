---
description: 'Más información sobre: codificación MTOM'
title: Codificación MTOM
ms.date: 03/30/2017
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
ms.openlocfilehash: 0663ab07b27dc8d1458af9935f3402432c00ee25
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752267"
---
# <a name="mtom-encoding"></a><span data-ttu-id="c7a1a-103">Codificación MTOM</span><span class="sxs-lookup"><span data-stu-id="c7a1a-103">MTOM Encoding</span></span>

<span data-ttu-id="c7a1a-104">Este ejemplo muestra el uso de la codificación de mensajes del Mecanismo de optimización de transmisión del mensaje (MTOM) con WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-104">This sample demonstrates the use of the Message Transmission Optimization Mechanism (MTOM) message encoding with a WSHttpBinding.</span></span> <span data-ttu-id="c7a1a-105">MTOM es un mecanismo para transmitir los datos adjuntos binarios grandes con mensajes SOAP como bytes sin formato, permitiendo los mensajes menores.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-105">MTOM is a mechanism for transmitting large binary attachments with SOAP messages as raw bytes, allowing for smaller messages.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c7a1a-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c7a1a-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-107">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c7a1a-108">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c7a1a-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-109">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 <span data-ttu-id="c7a1a-110">De forma predeterminada, WSHttpBinding envía y recibe los mensajes como texto normal XML.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-110">By default, the WSHttpBinding sends and received messages as normal text XML.</span></span> <span data-ttu-id="c7a1a-111">Para habilitar la recepción y el envío de los mensajes MTOM, establezca el atributo `messageEncoding` en la configuración (como en el código de ejemplo siguiente) del enlace o directamente en el enlace utilizando la propiedad `MessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-111">To enable sending and receiving MTOM messages, set the `messageEncoding` attribute on the binding's configuration (as in the following example code), or directly on the binding using the `MessageEncoding` property.</span></span> <span data-ttu-id="c7a1a-112">El servicio o cliente puede enviar y recibir ahora los mensajes MTOM.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-112">The service or client can now send and receive MTOM messages.</span></span>  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 <span data-ttu-id="c7a1a-113">El codificador MTOM puede optimizar matrices de bytes y secuencias.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-113">The MTOM encoder can optimize arrays of bytes and streams.</span></span> <span data-ttu-id="c7a1a-114">En este ejemplo, la operación utiliza un parámetro `Stream` y, por consiguiente, puede optimizarse.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-114">In this sample, the operation uses a `Stream` parameter and can therefore be optimized.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 <span data-ttu-id="c7a1a-115">El contrato elegido porque este ejemplo transmite los datos binarios al servicio y recibe el número de bytes cargado como el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-115">The contract chosen for this sample transmits binary data to the service and receives the number of bytes uploaded as the return value.</span></span> <span data-ttu-id="c7a1a-116">Cuando se instala el servicio y se ejecuta el cliente, imprime el número 1000, que indica que se recibieron 1000 bytes por completo.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-116">When the service is installed and the client is run, it prints out the number 1000, which indicates that all 1000 bytes were received.</span></span> <span data-ttu-id="c7a1a-117">El resto de las listas de salida optimizó y no optimizó los tamaños del mensaje para varias cargas útiles.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-117">The remainder of the output lists optimized and non-optimized message sizes for various payloads.</span></span>  
  
```console
Output:  
1000  
  
Text encoding with a 100 byte payload: 433  
MTOM encoding with a 100 byte payload: 912  
  
Text encoding with a 1000 byte payload: 1633  
MTOM encoding with a 1000 byte payload: 2080  
  
Text encoding with a 10000 byte payload: 13633  
MTOM encoding with a 10000 byte payload: 11080  
  
Text encoding with a 100000 byte payload: 133633  
MTOM encoding with a 100000 byte payload: 101080  
  
Text encoding with a 1000000 byte payload: 1333633  
MTOM encoding with a 1000000 byte payload: 1001080  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="c7a1a-118">El propósito para utilizar MTOM es optimizar la transmisión de grandes cargas útiles binarias.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-118">The purpose for using MTOM is to optimize the transmission of large binary payloads.</span></span> <span data-ttu-id="c7a1a-119">Al enviar un mensaje SOAP mediante MTOM, se tiene una sobrecarga notable para las cargas útiles binarias pequeñas, pero implica un gran ahorro cuando la cifra se eleva a unos miles de bytes.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-119">Sending a SOAP message using MTOM has a noticeable overhead for small binary payloads, but becomes a great savings when they grow over a few thousand bytes.</span></span> <span data-ttu-id="c7a1a-120">La razón es que el texto normal XML codifica datos binarios mediante Base64, lo cual requiere cuatro caracteres para cada tres bytes, y aumenta el tamaño de los datos en un tercio.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-120">The reason for this is that normal text XML encodes binary data using Base64, which requires four characters for every three bytes, and increases the size of the data by one third.</span></span> <span data-ttu-id="c7a1a-121">MTOM puede transmitir los datos binarios como bytes sin formato, guardando el tiempo de codificación/descodificando y lo que resulta son los mensajes menores.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-121">MTOM is able to transmit binary data as raw bytes, saving the encoding/decoding time and resulting is smaller messages.</span></span> <span data-ttu-id="c7a1a-122">El umbral de unos miles de bytes es pequeño cuando se compara con los documentos comerciales y las fotos digitales de hoy en día.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-122">The threshold of a few thousand bytes is small when compared to today's business documents and digital photographs.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c7a1a-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7a1a-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c7a1a-124">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="c7a1a-124">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="c7a1a-125">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c7a1a-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="c7a1a-126">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c7a1a-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="c7a1a-127">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c7a1a-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
