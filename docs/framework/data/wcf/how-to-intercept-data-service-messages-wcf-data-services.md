---
title: "Cómo: Interceptar mensajes de Data Services (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c18664eaa154fbc048c77cb359d0926f04b7e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="efa78-102">Cómo: Interceptar mensajes de Data Services (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="efa78-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="efa78-103">Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede interceptar mensajes de solicitud, lo que le permitirá agregar lógica personalizada a una operación.</span><span class="sxs-lookup"><span data-stu-id="efa78-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="efa78-104">Para interceptar un mensaje, se utilizan métodos con atributos especiales en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="efa78-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="efa78-105">Para obtener más información, consulte [interceptores](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efa78-105">For more information, see [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="efa78-106">En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="efa78-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="efa78-107">Este servicio se crea al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="efa78-107">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="efa78-108">Para definir un interceptor de consultas para el conjunto de entidades Orders</span><span class="sxs-lookup"><span data-stu-id="efa78-108">To define a query interceptor for the Orders entity set</span></span>  
  
1.  <span data-ttu-id="efa78-109">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="efa78-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="efa78-110">En la página de codigos de la clase `Northwind`, agregue la instrucción `using` siguiente (`Imports` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="efa78-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  <span data-ttu-id="efa78-111">En la clase `Northwind`, defina un método de operación de servicio denominado `OnQueryOrders` como sigue:</span><span class="sxs-lookup"><span data-stu-id="efa78-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="efa78-112">Para definir un interceptor de cambios para el conjunto de entidades Products</span><span class="sxs-lookup"><span data-stu-id="efa78-112">To define a change interceptor for the Products entity set</span></span>  
  
1.  <span data-ttu-id="efa78-113">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="efa78-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="efa78-114">En la clase `Northwind`, defina un método de operación de servicio denominado `OnChangeProducts` como sigue:</span><span class="sxs-lookup"><span data-stu-id="efa78-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="efa78-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efa78-115">Example</span></span>  
 <span data-ttu-id="efa78-116">En este ejemplo se define un método de interceptor de consultas para el conjunto de entidades `Orders` que devuelve una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="efa78-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="efa78-117">Esta expresión contiene un delegado que filtra los pedidos (`Orders`) solicitados basándose en los clientes (`Customers`) relacionados que tienen un nombre de contacto concreto.</span><span class="sxs-lookup"><span data-stu-id="efa78-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="efa78-118">El nombre se determina a su vez en función del usuario que realiza la solicitud.</span><span class="sxs-lookup"><span data-stu-id="efa78-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="efa78-119">En este ejemplo se supone que el servicio de datos se hospeda dentro de una aplicación web ASP.NET que usa WCF, y que la autenticación está habilitada.</span><span class="sxs-lookup"><span data-stu-id="efa78-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="efa78-120">La clase <xref:System.Web.HttpContext> se usa para recuperar el principio de la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="efa78-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="efa78-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efa78-121">Example</span></span>  
 <span data-ttu-id="efa78-122">En este ejemplo se define un método interceptor de cambios para el conjunto de entidades `Products`.</span><span class="sxs-lookup"><span data-stu-id="efa78-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="efa78-123">Este método valida la entrada al servicio para una operación <xref:System.Data.Services.UpdateOperations.Add> o <xref:System.Data.Services.UpdateOperations.Change> y produce una excepción si se hace un cambio en un producto que ya no se fabrica.</span><span class="sxs-lookup"><span data-stu-id="efa78-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="efa78-124">También bloquea la eliminación de productos como una operación no admitida.</span><span class="sxs-lookup"><span data-stu-id="efa78-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="efa78-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa78-125">See Also</span></span>  
 [<span data-ttu-id="efa78-126">Cómo: definir una operación de servicio</span><span class="sxs-lookup"><span data-stu-id="efa78-126">How to: Define a Service Operation</span></span>](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)  
 [<span data-ttu-id="efa78-127">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="efa78-127">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
