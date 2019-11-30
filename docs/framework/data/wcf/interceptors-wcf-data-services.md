---
title: Interceptores (Servicios de datos de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: c9799037ae0ea8b29b5e989859aff29c310593d4
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568979"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="835e6-102">Interceptores (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="835e6-102">Interceptors (WCF Data Services)</span></span>
<span data-ttu-id="835e6-103">WCF Data Services permite que una aplicación intercepte los mensajes de solicitud para que pueda agregar lógica personalizada a una operación.</span><span class="sxs-lookup"><span data-stu-id="835e6-103">WCF Data Services enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="835e6-104">Puede usar esta lógica personalizada para validar datos en los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="835e6-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="835e6-105">También puede utilizarla como restricción adicional del ámbito de una solicitud de consulta, por ejemplo, para insertar una directiva de autorización personalizada por solicitud.</span><span class="sxs-lookup"><span data-stu-id="835e6-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="835e6-106">Métodos con atributos especiales realizan la interceptación en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="835e6-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="835e6-107">WCF Data Services llama a estos métodos en el punto adecuado en el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="835e6-107">These methods are called by WCF Data Services at the appropriate point in message processing.</span></span> <span data-ttu-id="835e6-108">Los interceptores se definen en cada conjunto de entidades, y los métodos de interceptor no pueden aceptar parámetros de la solicitud, como las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="835e6-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="835e6-109">Los métodos de interceptor de consulta, a los que se llama al procesar una solicitud HTTP GET, deben devolver una expresión lambda que determine si los resultados de la consulta deben devolver una instancia del conjunto de entidades del interceptor.</span><span class="sxs-lookup"><span data-stu-id="835e6-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="835e6-110">El servicio de datos utiliza esta expresión para perfeccionar más la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="835e6-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="835e6-111">El ejemplo siguiente muestra una definición de un interceptor de consulta.</span><span class="sxs-lookup"><span data-stu-id="835e6-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="835e6-112">Para obtener más información, consulte [Cómo: Interceptar mensajes del servicio de datos](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="835e6-112">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="835e6-113">Los interceptores de cambio, a los que se llama al procesar las operaciones que no son de consulta, deben devolver `void` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="835e6-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="835e6-114">Los métodos de interceptor de cambio deben aceptar los dos siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="835e6-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="835e6-115">Un parámetro de un tipo que es compatible con el tipo de entidad del conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="835e6-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="835e6-116">Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la información de la entidad que envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="835e6-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="835e6-117">Un parámetro de tipo <xref:System.Data.Services.UpdateOperations>.</span><span class="sxs-lookup"><span data-stu-id="835e6-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="835e6-118">Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la operación que la solicitud intenta realizar.</span><span class="sxs-lookup"><span data-stu-id="835e6-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="835e6-119">El ejemplo siguiente muestra una definición de un interceptor de cambio.</span><span class="sxs-lookup"><span data-stu-id="835e6-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="835e6-120">Para obtener más información, consulte [Cómo: Interceptar mensajes del servicio de datos](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="835e6-120">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="835e6-121">La interceptación admite los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="835e6-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="835e6-122">**[QueryInterceptor (** *entitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="835e6-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="835e6-123">Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.QueryInterceptorAttribute> cuando se recibe una solicitud GET de HTTP para el recurso de conjunto de entidades concreto.</span><span class="sxs-lookup"><span data-stu-id="835e6-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="835e6-124">Estos métodos siempre deben devolver una expresión lambda en el formulario de `Expression<Func<T,bool>>`.</span><span class="sxs-lookup"><span data-stu-id="835e6-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="835e6-125">**[ChangeInterceptor (** *entitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="835e6-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="835e6-126">Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.ChangeInterceptorAttribute> cuando se recibe una solicitud HTTP distinta de GET para el recurso de conjunto de entidades concreto.</span><span class="sxs-lookup"><span data-stu-id="835e6-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="835e6-127">Estos métodos siempre deben devolver `void` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="835e6-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="835e6-128">Para obtener más información, consulte [Cómo: Interceptar mensajes del servicio de datos](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="835e6-128">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835e6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="835e6-129">See also</span></span>

- [<span data-ttu-id="835e6-130">Operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="835e6-130">Service Operations</span></span>](service-operations-wcf-data-services.md)
