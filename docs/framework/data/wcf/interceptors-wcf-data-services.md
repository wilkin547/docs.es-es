---
description: 'Más información sobre: interceptores (Servicios de datos de WCF)'
title: Interceptores (Servicios de datos de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: f73ee498d0419df9e083248802ea52ed050a914b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765079"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="d1410-103">Interceptores (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="d1410-103">Interceptors (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="d1410-104">Servicios de datos de WCF permite que una aplicación intercepte los mensajes de solicitud para que pueda agregar lógica personalizada a una operación.</span><span class="sxs-lookup"><span data-stu-id="d1410-104">WCF Data Services enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="d1410-105">Puede utilizar esta lógica personalizada para validar los datos de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="d1410-105">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="d1410-106">También puede utilizarla como restricción adicional del ámbito de una solicitud de consulta, por ejemplo, para insertar una directiva de autorización personalizada por solicitud.</span><span class="sxs-lookup"><span data-stu-id="d1410-106">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="d1410-107">Métodos con atributos especiales realizan la interceptación en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="d1410-107">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="d1410-108">Servicios de datos de WCF llama a estos métodos en el punto adecuado en el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d1410-108">These methods are called by WCF Data Services at the appropriate point in message processing.</span></span> <span data-ttu-id="d1410-109">Los interceptores se definen por entidad. Los métodos de interceptor no pueden aceptar los parámetros de la solicitud, como sí pueden las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="d1410-109">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="d1410-110">Los métodos de interceptor de consulta, a los que se llama al procesar una solicitud GET de HTTP, deben devolver una expresión lambda que determina si los resultados de la consulta deben devolver una instancia del conjunto de entidades del interceptor.</span><span class="sxs-lookup"><span data-stu-id="d1410-110">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="d1410-111">El servicio de datos utiliza esta expresión para perfeccionar más la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="d1410-111">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="d1410-112">El ejemplo siguiente muestra una definición de un interceptor de consulta.</span><span class="sxs-lookup"><span data-stu-id="d1410-112">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="d1410-113">Para obtener más información, consulte [Cómo: Interceptar mensajes del servicio de datos](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1410-113">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d1410-114">Los interceptores de cambio, a los que se llama al procesar las operaciones que no son de consulta, deben devolver `void` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d1410-114">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="d1410-115">Los métodos de interceptor de cambio deben aceptar los dos siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="d1410-115">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="d1410-116">Un parámetro de un tipo que es compatible con el tipo de entidad del conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="d1410-116">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="d1410-117">Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la información de la entidad que envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d1410-117">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="d1410-118">Un parámetro de tipo <xref:System.Data.Services.UpdateOperations>.</span><span class="sxs-lookup"><span data-stu-id="d1410-118">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="d1410-119">Cuando el servicio de datos llama al interceptor de cambio, el valor de este parámetro refleja la operación que la solicitud intenta realizar.</span><span class="sxs-lookup"><span data-stu-id="d1410-119">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="d1410-120">El ejemplo siguiente muestra una definición de un interceptor de cambio.</span><span class="sxs-lookup"><span data-stu-id="d1410-120">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="d1410-121">Para obtener más información, consulte [Cómo: Interceptar mensajes del servicio de datos](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1410-121">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d1410-122">La interceptación admite los siguientes atributos.</span><span class="sxs-lookup"><span data-stu-id="d1410-122">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="d1410-123">**[QueryInterceptor (** *entitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="d1410-123">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="d1410-124">Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.QueryInterceptorAttribute> cuando se recibe una solicitud GET de HTTP para el recurso de conjunto de entidades concreto.</span><span class="sxs-lookup"><span data-stu-id="d1410-124">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="d1410-125">Estos métodos siempre deben devolver una expresión lambda en el formulario de `Expression<Func<T,bool>>`.</span><span class="sxs-lookup"><span data-stu-id="d1410-125">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="d1410-126">**[ChangeInterceptor (** *entitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="d1410-126">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="d1410-127">Se llama a los métodos que tienen aplicado el atributo <xref:System.Data.Services.ChangeInterceptorAttribute> cuando se recibe una solicitud HTTP distinta de GET para el recurso de conjunto de entidades concreto.</span><span class="sxs-lookup"><span data-stu-id="d1410-127">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="d1410-128">Estos métodos siempre deben devolver `void` (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d1410-128">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="d1410-129">Para obtener más información, consulte [Cómo: Interceptar mensajes del servicio de datos](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1410-129">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1410-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1410-130">See also</span></span>

- [<span data-ttu-id="d1410-131">Operaciones del servicio</span><span class="sxs-lookup"><span data-stu-id="d1410-131">Service Operations</span></span>](service-operations-wcf-data-services.md)
