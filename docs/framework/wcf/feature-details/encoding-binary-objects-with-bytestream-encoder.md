---
title: Codificar objetos binarios con codificador de ByteStream
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: 9619fdf6979833c30159e1ea02b3f8d6b98a6629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61856510"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="b6973-102">Codificar objetos binarios con codificador de ByteStream</span><span class="sxs-lookup"><span data-stu-id="b6973-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="b6973-103">Enviar y recibir datos binarios sin formato con Windows Communication Foundation (WCF) se configuran mediante <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="b6973-103">Sending and receiving raw binary data with Windows Communication Foundation (WCF) is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="b6973-104">Arquitectura de codificador de mensajes de secuencia de bytes</span><span class="sxs-lookup"><span data-stu-id="b6973-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="b6973-105">El codificador de mensajes binarios utilizado por WCF no tiene ninguna facilidad para procesar, validar o identificar los datos binarios subyacentes en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b6973-105">The binary message encoder used by WCF has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="b6973-106">El paquete de datos se codifica en XML, se envía, se recibe y se descodifica.</span><span class="sxs-lookup"><span data-stu-id="b6973-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="b6973-107">El codificador procesa los datos tras haberse enviado al transporte y antes de que el mensaje se envíe a la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b6973-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="b6973-108">Funcionalmente, el codificador binario ajusta los datos del mensaje en elementos `<binary>` para enviar y quita los elementos una vez recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b6973-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="b6973-109">Usar el codificador de mensajes de secuencia de bytes</span><span class="sxs-lookup"><span data-stu-id="b6973-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="b6973-110">En el siguiente ejemplo, se muestra un contrato de servicios que implementa el codificador de mensajes de secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="b6973-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="b6973-111">El siguiente ejemplo muestra el servicio que se invoca.</span><span class="sxs-lookup"><span data-stu-id="b6973-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="b6973-112">En caso de utilizar un servicio que implementa una infraestructura del mensaje (como un enrutador), el mensaje se procesa sin inspeccionar, validar o interactuar de cualquier manera con el mensaje, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b6973-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="b6973-113">Escenarios</span><span class="sxs-lookup"><span data-stu-id="b6973-113">Scenarios</span></span>  
 <span data-ttu-id="b6973-114">El codificador de secuencias de bytes es útil en los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="b6973-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
-   <span data-ttu-id="b6973-115">Transferir una imagen JPEG entre equipos mediante WCF.</span><span class="sxs-lookup"><span data-stu-id="b6973-115">Transferring a JPEG image between computers using WCF.</span></span> <span data-ttu-id="b6973-116">En este escenario, la imagen llegará a través del transporte desde un origen externo y los datos enviados serán los bytes sin formato que formen la imagen.</span><span class="sxs-lookup"><span data-stu-id="b6973-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="b6973-117">Un servicio recibirá los datos binarios y mostrará la imagen.</span><span class="sxs-lookup"><span data-stu-id="b6973-117">A service will receive the binary data and display the image.</span></span>  
  
-   <span data-ttu-id="b6973-118">Al leer información de una cola de mensajes y procesarla.</span><span class="sxs-lookup"><span data-stu-id="b6973-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="b6973-119">El mensaje se leerá de un administrador de colas de mensajes y se pasará al canal de cola de mensajes para tratarlo.</span><span class="sxs-lookup"><span data-stu-id="b6973-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="b6973-120">El canal de cola de mensajes actuará como un administrador de cola en la pila de canales WCF.</span><span class="sxs-lookup"><span data-stu-id="b6973-120">The message queue channel will act as a queue manager in the WCF channel stack.</span></span>  
  
 <span data-ttu-id="b6973-121">En el caso de enviar un mensaje a través de un canal de cola de mensajes, el remitente no tiene el control sobre los bytes que se reciben del administrador de la cola.</span><span class="sxs-lookup"><span data-stu-id="b6973-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="b6973-122">Si el proceso de recepción no tiene la capacidad de leer los bytes sin formato, el mensaje se recibirá con formato incorrecto y no se procesará; se supone que el proceso de recepción tendrá la capacidad de traducir los bytes recibidos de nuevo a un formato utilizable.</span><span class="sxs-lookup"><span data-stu-id="b6973-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
