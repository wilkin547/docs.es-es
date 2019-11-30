---
title: 'Cómo: Interceptar mensajes de Data Services (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 4f2d6cf34c820c60181d5287298898af5eb8d038
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569045"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="67f91-102">Cómo: Interceptar mensajes de Data Services (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="67f91-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="67f91-103">Con WCF Data Services, puede interceptar mensajes de solicitud para que pueda agregar lógica personalizada a una operación.</span><span class="sxs-lookup"><span data-stu-id="67f91-103">With WCF Data Services, you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="67f91-104">Para interceptar un mensaje, se usan métodos especialmente atribuidos en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="67f91-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="67f91-105">Para obtener más información, vea [interceptores](interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="67f91-105">For more information, see [Interceptors](interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="67f91-106">En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="67f91-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="67f91-107">Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="67f91-107">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="67f91-108">Para definir un interceptor de consultas para el conjunto de entidades Orders</span><span class="sxs-lookup"><span data-stu-id="67f91-108">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="67f91-109">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="67f91-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="67f91-110">En la página de codigos de la clase `Northwind`, agregue la instrucción `using` siguiente (`Imports` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="67f91-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="67f91-111">En la clase `Northwind`, defina un método de operación de servicio denominado `OnQueryOrders` como sigue:</span><span class="sxs-lookup"><span data-stu-id="67f91-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="67f91-112">Para definir un interceptor de cambios para el conjunto de entidades Products</span><span class="sxs-lookup"><span data-stu-id="67f91-112">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="67f91-113">En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="67f91-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="67f91-114">En la clase `Northwind`, defina un método de operación de servicio denominado `OnChangeProducts` como sigue:</span><span class="sxs-lookup"><span data-stu-id="67f91-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="67f91-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67f91-115">Example</span></span>  
 <span data-ttu-id="67f91-116">En este ejemplo se define un método de interceptor de consultas para el conjunto de entidades `Orders` que devuelve una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="67f91-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="67f91-117">Esta expresión contiene un delegado que filtra los pedidos (`Orders`) solicitados basándose en los clientes (`Customers`) relacionados que tienen un nombre de contacto concreto.</span><span class="sxs-lookup"><span data-stu-id="67f91-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="67f91-118">El nombre se determina a su vez en función del usuario que realiza la solicitud.</span><span class="sxs-lookup"><span data-stu-id="67f91-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="67f91-119">En este ejemplo se supone que el servicio de datos se hospeda dentro de una aplicación web ASP.NET que usa WCF, y que la autenticación está habilitada.</span><span class="sxs-lookup"><span data-stu-id="67f91-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="67f91-120">La clase <xref:System.Web.HttpContext> se usa para recuperar el principio de la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="67f91-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="67f91-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67f91-121">Example</span></span>  
 <span data-ttu-id="67f91-122">En este ejemplo se define un método interceptor de cambios para el conjunto de entidades `Products`.</span><span class="sxs-lookup"><span data-stu-id="67f91-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="67f91-123">Este método valida la entrada al servicio para una operación <xref:System.Data.Services.UpdateOperations.Add> o <xref:System.Data.Services.UpdateOperations.Change> y produce una excepción si se hace un cambio en un producto que ya no se fabrica.</span><span class="sxs-lookup"><span data-stu-id="67f91-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="67f91-124">También bloquea la eliminación de productos como una operación no admitida.</span><span class="sxs-lookup"><span data-stu-id="67f91-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="67f91-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="67f91-125">See also</span></span>

- [<span data-ttu-id="67f91-126">Definición de una operación de servicio</span><span class="sxs-lookup"><span data-stu-id="67f91-126">How to: Define a Service Operation</span></span>](how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="67f91-127">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="67f91-127">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
