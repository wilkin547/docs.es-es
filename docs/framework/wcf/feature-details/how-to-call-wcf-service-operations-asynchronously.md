---
title: Cómo llamar a operaciones del servicio WCF de forma asincrónica
description: Obtenga información sobre cómo crear un cliente WCF que pueda tener acceso de forma asincrónica a una operación de servicio mediante el modelo de llamada asincrónica orientado a eventos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: aa31f64473111800f4cd01907a0446c94f368456
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247239"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="8414f-103">Cómo llamar a operaciones del servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="8414f-103">How to: Call WCF Service Operations Asynchronously</span></span>

<span data-ttu-id="8414f-104">En este artículo se explica cómo un cliente puede tener acceso de forma asincrónica a una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="8414f-104">This article covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="8414f-105">El servicio de este artículo implementa la `ICalculator` interfaz.</span><span class="sxs-lookup"><span data-stu-id="8414f-105">The service in this article implements the `ICalculator` interface.</span></span> <span data-ttu-id="8414f-106">El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos.</span><span class="sxs-lookup"><span data-stu-id="8414f-106">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="8414f-107">(Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span><span class="sxs-lookup"><span data-stu-id="8414f-107">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span></span> <span data-ttu-id="8414f-108">Para obtener un ejemplo que muestra cómo implementar una operación de forma asincrónica en un servicio, vea [Cómo: implementar una operación de servicio asincrónica](../how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="8414f-108">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="8414f-109">Para obtener más información sobre las operaciones sincrónicas y asincrónicas, vea [operaciones sincrónicas y asincrónicas](../synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8414f-109">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8414f-110">El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="8414f-110">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="8414f-111">Para obtener información sobre cómo realizar llamadas asincrónicas mediante <xref:System.ServiceModel.ChannelFactory%601> , vea [Cómo: llamar a operaciones de forma asincrónica con un generador de canales](how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="8414f-111">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="8414f-112">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="8414f-112">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="8414f-113">Para llamar a operaciones de servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="8414f-113">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="8414f-114">Ejecute la herramienta de [utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con las `/async` Opciones de `/tcv:Version35` comando y, como se muestra en el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8414f-114">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="8414f-115">Esto genera, además de las operaciones asincrónicas sincrónicas y estándar basadas en delegado, una clase de cliente de WCF que contiene:</span><span class="sxs-lookup"><span data-stu-id="8414f-115">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="8414f-116">Dos `operationName` > `Async` operaciones de <para su uso con el enfoque de llamada asincrónica basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="8414f-116">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="8414f-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8414f-117">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="8414f-118">Los eventos de operación completada del formulario <`operationName` > `Completed` para su uso con el enfoque de llamada asincrónica basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="8414f-118">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="8414f-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8414f-119">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="8414f-120"><xref:System.EventArgs?displayProperty=nameWithType>tipos para cada operación (de la forma <`operationName` > `CompletedEventArgs` ) para su uso con el enfoque de llamada asincrónica basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="8414f-120"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="8414f-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8414f-121">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="8414f-122">En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8414f-122">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="8414f-123">Antes de llamar a la operación, utilice un nuevo genérico <xref:System.EventHandler%601?displayProperty=nameWithType> de tipo <`operationName` > `EventArgs` para agregar el método de control (creado en el paso anterior) al `operationName` > `Completed` evento <.</span><span class="sxs-lookup"><span data-stu-id="8414f-123">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="8414f-124">A continuación, llame al `operationName` > `Async` método <.</span><span class="sxs-lookup"><span data-stu-id="8414f-124">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="8414f-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8414f-125">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="8414f-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8414f-126">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8414f-127">Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="8414f-127">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="8414f-128">Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="8414f-128">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="8414f-129">Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="8414f-129">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="8414f-130">Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8414f-130">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8414f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8414f-131">See also</span></span>

- [<span data-ttu-id="8414f-132">Procedimiento para implementar una operación de servicios asincrónica</span><span class="sxs-lookup"><span data-stu-id="8414f-132">How to: Implement an Asynchronous Service Operation</span></span>](../how-to-implement-an-asynchronous-service-operation.md)
