---
title: Procedimiento Llamar a operaciones de servicio WCF de forma asincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: aba41d707426f29c2bcd626dbbe13d16d9e1b1f7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624498"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="0c304-102">Procedimiento Llamar a operaciones de servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="0c304-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="0c304-103">En este tema se explica cómo puede tener acceso un cliente a una operación de servicio de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="0c304-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="0c304-104">El servicio en este tema implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="0c304-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="0c304-105">El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos.</span><span class="sxs-lookup"><span data-stu-id="0c304-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="0c304-106">(Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](https://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="0c304-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="0c304-107">Para obtener un ejemplo que muestra cómo implementar una operación asincrónica en un servicio, vea [Cómo: Implementar una operación de servicio asincrónico](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="0c304-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="0c304-108">Para obtener más información acerca de las operaciones sincrónicas y asincrónicas, vea [sincrónica y operaciones asincrónicas](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0c304-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c304-109">El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="0c304-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="0c304-110">Para obtener información acerca de cómo realizar llamadas asincrónicas mediante el <xref:System.ServiceModel.ChannelFactory%601>, vea [Cómo: Llamar a operaciones de forma asincrónica utilizando un generador de canales](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="0c304-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="0c304-111">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="0c304-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="0c304-112">Para llamar a operaciones de servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="0c304-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="0c304-113">Ejecute el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta con ambos el `/async` y `/tcv:Version35` las opciones del comando juntos como se muestra en el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="0c304-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="0c304-114">Esto genera, además de las operaciones sincrónicas y estándares basado en delegados asincrónicas, una clase de cliente WCF que contiene:</span><span class="sxs-lookup"><span data-stu-id="0c304-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="0c304-115">Dos <`operationName` > `Async` operaciones para su uso con el enfoque de llamada asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="0c304-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="0c304-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c304-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="0c304-117">Eventos completados de operación del formulario <`operationName` > `Completed` para su uso con el enfoque de llamada asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="0c304-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="0c304-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c304-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="0c304-119"><xref:System.EventArgs?displayProperty=nameWithType> tipos para cada operación (el formato <`operationName`>`CompletedEventArgs`) para su uso con el enfoque de llamada asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="0c304-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="0c304-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c304-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="0c304-121">En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c304-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="0c304-122">Antes de llamar a la operación, utilice un nuevo genérico <xref:System.EventHandler%601?displayProperty=nameWithType> de tipo <`operationName` > `EventArgs` para agregar el método de controlador (creado en el paso anterior) a la <`operationName` > `Completed` eventos.</span><span class="sxs-lookup"><span data-stu-id="0c304-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="0c304-123">A continuación, llame a la <`operationName` > `Async` método.</span><span class="sxs-lookup"><span data-stu-id="0c304-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="0c304-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c304-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="0c304-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c304-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c304-126">Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0c304-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="0c304-127">Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="0c304-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="0c304-128">Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0c304-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="0c304-129">Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0c304-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0c304-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c304-130">See also</span></span>

- [<span data-ttu-id="0c304-131">Cómo: Implementar una operación de servicio asincrónico</span><span class="sxs-lookup"><span data-stu-id="0c304-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
