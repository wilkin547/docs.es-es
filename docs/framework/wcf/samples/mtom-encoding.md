---
title: Codificación MTOM
ms.date: 03/30/2017
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
ms.openlocfilehash: 1f30c3a1c7a9a4874f4b831ee27192468e63c192
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501421"
---
# <a name="mtom-encoding"></a><span data-ttu-id="cba5a-102">Codificación MTOM</span><span class="sxs-lookup"><span data-stu-id="cba5a-102">MTOM Encoding</span></span>
<span data-ttu-id="cba5a-103">Este ejemplo muestra el uso de la codificación de mensajes del Mecanismo de optimización de transmisión del mensaje (MTOM) con WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="cba5a-103">This sample demonstrates the use of the Message Transmission Optimization Mechanism (MTOM) message encoding with a WSHttpBinding.</span></span> <span data-ttu-id="cba5a-104">MTOM es un mecanismo para transmitir los datos adjuntos binarios grandes con mensajes SOAP como bytes sin formato, permitiendo los mensajes menores.</span><span class="sxs-lookup"><span data-stu-id="cba5a-104">MTOM is a mechanism for transmitting large binary attachments with SOAP messages as raw bytes, allowing for smaller messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cba5a-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="cba5a-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cba5a-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cba5a-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cba5a-107">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="cba5a-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cba5a-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="cba5a-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 <span data-ttu-id="cba5a-109">De forma predeterminada, WSHttpBinding envía y recibe los mensajes como texto normal XML.</span><span class="sxs-lookup"><span data-stu-id="cba5a-109">By default, the WSHttpBinding sends and received messages as normal text XML.</span></span> <span data-ttu-id="cba5a-110">Para habilitar la recepción y el envío de los mensajes MTOM, establezca el atributo `messageEncoding` en la configuración (como en el código de ejemplo siguiente) del enlace o directamente en el enlace utilizando la propiedad `MessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="cba5a-110">To enable sending and receiving MTOM messages, set the `messageEncoding` attribute on the binding's configuration (as in the following example code), or directly on the binding using the `MessageEncoding` property.</span></span> <span data-ttu-id="cba5a-111">El servicio o cliente puede enviar y recibir ahora los mensajes MTOM.</span><span class="sxs-lookup"><span data-stu-id="cba5a-111">The service or client can now send and receive MTOM messages.</span></span>  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 <span data-ttu-id="cba5a-112">El codificador MTOM puede optimizar matrices de bytes y secuencias.</span><span class="sxs-lookup"><span data-stu-id="cba5a-112">The MTOM encoder can optimize arrays of bytes and streams.</span></span> <span data-ttu-id="cba5a-113">En este ejemplo, la operación utiliza un parámetro `Stream` y, por consiguiente, puede optimizarse.</span><span class="sxs-lookup"><span data-stu-id="cba5a-113">In this sample, the operation uses a `Stream` parameter and can therefore be optimized.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 <span data-ttu-id="cba5a-114">El contrato elegido porque este ejemplo transmite los datos binarios al servicio y recibe el número de bytes cargado como el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="cba5a-114">The contract chosen for this sample transmits binary data to the service and receives the number of bytes uploaded as the return value.</span></span> <span data-ttu-id="cba5a-115">Cuando se instala el servicio y se ejecuta el cliente, imprime el número 1000, que indica que se recibieron 1000 bytes por completo.</span><span class="sxs-lookup"><span data-stu-id="cba5a-115">When the service is installed and the client is run, it prints out the number 1000, which indicates that all 1000 bytes were received.</span></span> <span data-ttu-id="cba5a-116">El resto de las listas de salida optimizó y no optimizó los tamaños del mensaje para varias cargas útiles.</span><span class="sxs-lookup"><span data-stu-id="cba5a-116">The remainder of the output lists optimized and non-optimized message sizes for various payloads.</span></span>  
  
```  
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
  
 <span data-ttu-id="cba5a-117">El propósito para utilizar MTOM es optimizar la transmisión de grandes cargas útiles binarias.</span><span class="sxs-lookup"><span data-stu-id="cba5a-117">The purpose for using MTOM is to optimize the transmission of large binary payloads.</span></span> <span data-ttu-id="cba5a-118">Al enviar un mensaje SOAP mediante MTOM, se tiene una sobrecarga notable para las cargas útiles binarias pequeñas, pero implica un gran ahorro cuando la cifra se eleva a unos miles de bytes.</span><span class="sxs-lookup"><span data-stu-id="cba5a-118">Sending a SOAP message using MTOM has a noticeable overhead for small binary payloads, but becomes a great savings when they grow over a few thousand bytes.</span></span> <span data-ttu-id="cba5a-119">La razón es que el texto normal XML codifica datos binarios mediante Base64, lo cual requiere cuatro caracteres para cada tres bytes, y aumenta el tamaño de los datos en un tercio.</span><span class="sxs-lookup"><span data-stu-id="cba5a-119">The reason for this is that normal text XML encodes binary data using Base64, which requires four characters for every three bytes, and increases the size of the data by one third.</span></span> <span data-ttu-id="cba5a-120">MTOM puede transmitir los datos binarios como bytes sin formato, guardando el tiempo de codificación/descodificando y lo que resulta son los mensajes menores.</span><span class="sxs-lookup"><span data-stu-id="cba5a-120">MTOM is able to transmit binary data as raw bytes, saving the encoding/decoding time and resulting is smaller messages.</span></span> <span data-ttu-id="cba5a-121">El umbral de unos miles de bytes es pequeño cuando se compara con los documentos comerciales y las fotos digitales de hoy en día.</span><span class="sxs-lookup"><span data-stu-id="cba5a-121">The threshold of a few thousand bytes is small when compared to today's business documents and digital photographs.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cba5a-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cba5a-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cba5a-123">Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="cba5a-123">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="cba5a-124">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cba5a-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="cba5a-125">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cba5a-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="cba5a-126">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cba5a-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba5a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="cba5a-127">See Also</span></span>
