---
title: "Cómo: Implementar una operación de servicios asincrónica"
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
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 65cd45a2510aa43c3f0c58a7cbf78c13e47d821e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="7e6b7-102">Cómo: Implementar una operación de servicios asincrónica</span><span class="sxs-lookup"><span data-stu-id="7e6b7-102">How to: Implement an Asynchronous Service Operation</span></span>
<span data-ttu-id="7e6b7-103">En aplicaciones de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], se puede implementar una operación de servicio de forma asincrónica o sincrónica sin dictar al cliente cómo llamarla.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-103">In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="7e6b7-104">Por ejemplo, las operaciones de servicio asincrónicas pueden realizar llamadas sincrónicamente y a las operaciones de servicio sincrónicas se las puede llamar de manera asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-104">For example, asynchronous service operations can be calling synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="7e6b7-105">Para obtener un ejemplo que muestra cómo llamar a una operación de forma asincrónica en una aplicación cliente, consulte [Cómo: llamar a las operaciones de servicio de forma asincrónica](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="7e6b7-105">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7e6b7-106">operaciones sincrónicas y asincrónicas, vea [diseñar contratos de servicio](../../../docs/framework/wcf/designing-service-contracts.md) y [sincrónica y operaciones asincrónicas](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="7e6b7-106"> synchronous and asynchronous operations, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md) and [Synchronous and Asynchronous Operations](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="7e6b7-107">En este tema se describe la estructura básica de una operación de servicio asincrónica, el código no está completo.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-107">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="7e6b7-108">Para obtener un ejemplo completo de servicio y el cliente consulte [asincrónico](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7).</span><span class="sxs-lookup"><span data-stu-id="7e6b7-108">For a complete example of both the service and client sides see [Asynchronous](http://msdn.microsoft.com/en-us/833db946-f511-4f64-a26f-2759a11217c7).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="7e6b7-109">Implementación de una operación de servicio de manera asincrónica</span><span class="sxs-lookup"><span data-stu-id="7e6b7-109">Implement a service operation asynchronously</span></span>  
  
1.  <span data-ttu-id="7e6b7-110">En su contrato de servicio, declare un par de métodos asincrónicos según las instrucciones de diseño asincrónico de .NET.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-110">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="7e6b7-111">El método `Begin` toma un parámetro, un objeto de devolución de llamada y un objeto de estado, y devuelve un <xref:System.IAsyncResult?displayProperty=nameWithType> y un método `End` correspondiente que toma <xref:System.IAsyncResult?displayProperty=nameWithType> y devuelven el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-111">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="7e6b7-112">Para obtener más información acerca de las llamadas asincrónicas, vea [asincrónica Programming Design Patterns](http://go.microsoft.com/fwlink/?LinkId=248221).</span><span class="sxs-lookup"><span data-stu-id="7e6b7-112">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](http://go.microsoft.com/fwlink/?LinkId=248221).</span></span>  
  
2.  <span data-ttu-id="7e6b7-113">Marque el método `Begin` del par de métodos asincrónicos con el atributo <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> y establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> en `true`.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-113">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="7e6b7-114">Por ejemplo, el código siguiente realiza los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-114">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  <span data-ttu-id="7e6b7-115">Implemente el par de método `Begin/End` en su clase de servicio según las instrucciones de diseño asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-115">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="7e6b7-116">Por ejemplo, el siguiente ejemplo de código muestra una implementación en la que una cadena se escribe en la consola en porciones `Begin` y `End` de la operación de servicio asincrónica y el valor devuelto de la operación `End` se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-116">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="7e6b7-117">Para obtener el ejemplo de código completo, consulte la sección Ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-117">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="7e6b7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e6b7-118">Example</span></span>  
 <span data-ttu-id="7e6b7-119">Los siguientes ejemplos de código muestran:</span><span class="sxs-lookup"><span data-stu-id="7e6b7-119">The following code examples show:</span></span>  
  
1.  <span data-ttu-id="7e6b7-120">Una interfaz del contrato de servicio con:</span><span class="sxs-lookup"><span data-stu-id="7e6b7-120">A service contract interface with:</span></span>  
  
    1.  <span data-ttu-id="7e6b7-121">Una operación `SampleMethod` sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-121">A synchronous `SampleMethod` operation.</span></span>  
  
    2.  <span data-ttu-id="7e6b7-122">Una operación `BeginSampleMethod` asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-122">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3.  <span data-ttu-id="7e6b7-123">Una asincrónica `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` par de operaciones.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-123">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2.  <span data-ttu-id="7e6b7-124">Una implementación de servicio mediante un objeto <xref:System.IAsyncResult?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e6b7-124">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7e6b7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e6b7-125">See Also</span></span>  
 [<span data-ttu-id="7e6b7-126">Diseño de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="7e6b7-126">Designing Service Contracts</span></span>](../../../docs/framework/wcf/designing-service-contracts.md)  
 [<span data-ttu-id="7e6b7-127">Operaciones sincrónicas y asincrónicas</span><span class="sxs-lookup"><span data-stu-id="7e6b7-127">Synchronous and Asynchronous Operations</span></span>](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
