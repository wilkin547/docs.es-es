---
title: Cómo llamar a operaciones del servicio WCF de forma asincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 5eae08ab6b8dee5ebece66a1c41c87ebab3387bc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963278"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="7ffbe-102">Cómo llamar a operaciones del servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="7ffbe-102">How to: Call WCF Service Operations Asynchronously</span></span>

<span data-ttu-id="7ffbe-103">En este artículo se explica cómo un cliente puede tener acceso de forma asincrónica a una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-103">This article covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="7ffbe-104">El servicio de este artículo implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-104">The service in this article implements the `ICalculator` interface.</span></span> <span data-ttu-id="7ffbe-105">El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="7ffbe-106">(Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span><span class="sxs-lookup"><span data-stu-id="7ffbe-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span></span> <span data-ttu-id="7ffbe-107">Para obtener un ejemplo que muestra cómo implementar una operación de forma asincrónica en un servicio, vea [Cómo: implementar una operación de servicio asincrónica](../how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="7ffbe-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="7ffbe-108">Para obtener más información sobre las operaciones sincrónicas y asincrónicas, vea [operaciones sincrónicas y asincrónicas](../synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7ffbe-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ffbe-109">El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="7ffbe-110">Para obtener información sobre cómo realizar llamadas asincrónicas mediante el <xref:System.ServiceModel.ChannelFactory%601>, consulte [Cómo: llamar a operaciones de forma asincrónica con un generador de canales](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="7ffbe-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="7ffbe-111">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="7ffbe-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="7ffbe-112">Para llamar a operaciones de servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="7ffbe-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="7ffbe-113">Ejecute la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con las opciones de comando `/async` y `/tcv:Version35`, como se muestra en el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="7ffbe-114">Esto genera, además de las operaciones asincrónicas sincrónicas y estándar basadas en delegado, una clase de cliente de WCF que contiene:</span><span class="sxs-lookup"><span data-stu-id="7ffbe-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="7ffbe-115">Dos <`operationName`>operaciones de `Async` para su uso con el enfoque de llamada asincrónica basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="7ffbe-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7ffbe-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="7ffbe-117">Los eventos de operación completada del formulario <`operationName`>`Completed` para su uso con el enfoque de llamada asincrónica basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="7ffbe-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7ffbe-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="7ffbe-119"><xref:System.EventArgs?displayProperty=nameWithType> tipos para cada operación (con el formato <`operationName`>`CompletedEventArgs`) para su uso con el enfoque de llamada asincrónica basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="7ffbe-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7ffbe-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="7ffbe-121">En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="7ffbe-122">Antes de llamar a la operación, utilice una nueva <xref:System.EventHandler%601?displayProperty=nameWithType> genérica de tipo <`operationName`>`EventArgs` para agregar el método de control (creado en el paso anterior) al <`operationName`>`Completed` evento.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="7ffbe-123">A continuación, llame al método de `Async` <`operationName`>.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="7ffbe-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7ffbe-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="7ffbe-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ffbe-125">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ffbe-126">Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="7ffbe-127">Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="7ffbe-128">Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="7ffbe-129">Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7ffbe-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="7ffbe-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ffbe-130">See also</span></span>

- [<span data-ttu-id="7ffbe-131">Cómo implementar una operación de servicios asincrónica</span><span class="sxs-lookup"><span data-stu-id="7ffbe-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
