---
description: 'Más información acerca de cómo: Interceptar mensajes del servicio de datos (Servicios de datos de WCF)'
title: 'Cómo: Interceptar mensajes de Data Services (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 6768fa9f0c7ca9a5a6ed6faa318675f2c2c51543
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765287"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="dc957-103">Cómo: Interceptar mensajes de Data Services (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="dc957-103">How to: Intercept Data Service Messages (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="dc957-104">Con Servicios de datos de WCF, puede interceptar mensajes de solicitud para que pueda agregar lógica personalizada a una operación.</span><span class="sxs-lookup"><span data-stu-id="dc957-104">With WCF Data Services, you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="dc957-105">Para interceptar un mensaje, se usan métodos con atributos especiales con el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="dc957-105">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="dc957-106">Para obtener más información, vea [interceptores](interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc957-106">For more information, see [Interceptors](interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="dc957-107">En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="dc957-107">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="dc957-108">Este servicio se crea cuando se completa la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc957-108">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="dc957-109">Para definir un interceptor de consultas para el conjunto de entidades Orders</span><span class="sxs-lookup"><span data-stu-id="dc957-109">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="dc957-110">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="dc957-110">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="dc957-111">En la página de codigos de la clase `Northwind`, agregue la instrucción `using` siguiente (`Imports` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dc957-111">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="dc957-112">En la clase `Northwind`, defina un método de operación de servicio denominado `OnQueryOrders` como sigue:</span><span class="sxs-lookup"><span data-stu-id="dc957-112">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="dc957-113">Para definir un interceptor de cambios para el conjunto de entidades Products</span><span class="sxs-lookup"><span data-stu-id="dc957-113">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="dc957-114">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="dc957-114">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="dc957-115">En la clase `Northwind`, defina un método de operación de servicio denominado `OnChangeProducts` como sigue:</span><span class="sxs-lookup"><span data-stu-id="dc957-115">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="dc957-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc957-116">Example</span></span>  

 <span data-ttu-id="dc957-117">En este ejemplo se define un método de interceptor de consultas para el conjunto de entidades `Orders` que devuelve una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="dc957-117">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="dc957-118">Esta expresión contiene un delegado que filtra los pedidos (`Orders`) solicitados basándose en los clientes (`Customers`) relacionados que tienen un nombre de contacto concreto.</span><span class="sxs-lookup"><span data-stu-id="dc957-118">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="dc957-119">El nombre se determina a su vez en función del usuario que realiza la solicitud.</span><span class="sxs-lookup"><span data-stu-id="dc957-119">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="dc957-120">En este ejemplo se supone que el servicio de datos se hospeda dentro de una aplicación web ASP.NET que usa WCF, y que la autenticación está habilitada.</span><span class="sxs-lookup"><span data-stu-id="dc957-120">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="dc957-121">La clase <xref:System.Web.HttpContext> se usa para recuperar el principio de la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="dc957-121">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="dc957-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc957-122">Example</span></span>  

 <span data-ttu-id="dc957-123">En este ejemplo se define un método interceptor de cambios para el conjunto de entidades `Products`.</span><span class="sxs-lookup"><span data-stu-id="dc957-123">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="dc957-124">Este método valida la entrada al servicio para una operación <xref:System.Data.Services.UpdateOperations.Add> o <xref:System.Data.Services.UpdateOperations.Change> y produce una excepción si se hace un cambio en un producto que ya no se fabrica.</span><span class="sxs-lookup"><span data-stu-id="dc957-124">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="dc957-125">También bloquea la eliminación de productos como una operación no admitida.</span><span class="sxs-lookup"><span data-stu-id="dc957-125">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="dc957-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc957-126">See also</span></span>

- [<span data-ttu-id="dc957-127">Procedimiento para definir una operación de servicio</span><span class="sxs-lookup"><span data-stu-id="dc957-127">How to: Define a Service Operation</span></span>](how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="dc957-128">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="dc957-128">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
