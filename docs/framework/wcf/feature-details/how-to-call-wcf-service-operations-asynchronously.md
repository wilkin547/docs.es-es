---
title: "Cómo llamar a operaciones del servicio WCF de forma asincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f8f1419deb60b1f68e47c26c0edd5523a9d23768
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="dfccc-102">Cómo llamar a operaciones del servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="dfccc-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="dfccc-103">En este tema se explica cómo puede tener acceso un cliente a una operación de servicio de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="dfccc-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="dfccc-104">El servicio en este tema implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dfccc-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="dfccc-105">El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos.</span><span class="sxs-lookup"><span data-stu-id="dfccc-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="dfccc-106">(Para obtener más información sobre el modelo de llamada asincrónico basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](http://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="dfccc-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="dfccc-107">Para obtener un ejemplo que muestra cómo implementar una operación asincrónica en un servicio, consulte [Cómo: implementar una operación de servicio asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="dfccc-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="dfccc-108">Para obtener más información acerca de las operaciones sincrónicas y asincrónicas, vea [sincrónica y operaciones asincrónicas](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="dfccc-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfccc-109">El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="dfccc-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="dfccc-110">Para obtener información acerca de cómo realizar llamadas asincrónicas mediante el <xref:System.ServiceModel.ChannelFactory%601>, consulte [Cómo: llamar a las operaciones de forma asincrónica utilizando un generador de canales](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="dfccc-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="dfccc-111">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="dfccc-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="dfccc-112">Para llamar a operaciones de servicio WCF de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="dfccc-112">To call WCF service operations asynchronously</span></span>  
  
1.  <span data-ttu-id="dfccc-113">Ejecutar la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta con ambos el `/async` y `/tcv:Version35` opciones de comando de juntos como se muestra en el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="dfccc-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="dfccc-114">De este modo se genera, además de las operaciones sincrónicas y las operaciones estándar asincrónicas basadas en delegado, una clase de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que incluye:</span><span class="sxs-lookup"><span data-stu-id="dfccc-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class that contains:</span></span>  
  
    -   <span data-ttu-id="dfccc-115">Dos <`operationName` > `Async` operaciones para su uso con el método que realiza la llamada asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="dfccc-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="dfccc-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dfccc-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   <span data-ttu-id="dfccc-117">Eventos de la operación se completó el formato <`operationName` > `Completed` para su uso con el método que realiza la llamada asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="dfccc-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="dfccc-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dfccc-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <span data-ttu-id="dfccc-119"><xref:System.EventArgs?displayProperty=nameWithType>tipos para cada operación (el formato <`operationName`>`CompletedEventArgs`) para su uso con el método que realiza la llamada asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="dfccc-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="dfccc-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dfccc-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  <span data-ttu-id="dfccc-121">En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dfccc-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  <span data-ttu-id="dfccc-122">Antes de llamar a la operación, use un tipo genérico nuevo <xref:System.EventHandler%601?displayProperty=nameWithType> de tipo <`operationName` > `EventArgs` para agregar el método de controlador (creado en el paso anterior) a la <`operationName` > `Completed` eventos.</span><span class="sxs-lookup"><span data-stu-id="dfccc-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="dfccc-123">A continuación, llame a la <`operationName` > `Async` método.</span><span class="sxs-lookup"><span data-stu-id="dfccc-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="dfccc-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dfccc-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="dfccc-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfccc-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfccc-126">Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="dfccc-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="dfccc-127">Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="dfccc-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="dfccc-128">Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="dfccc-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="dfccc-129">Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dfccc-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="dfccc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfccc-130">See Also</span></span>  
 [<span data-ttu-id="dfccc-131">Cómo implementar una operación de servicios asincrónica</span><span class="sxs-lookup"><span data-stu-id="dfccc-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
