---
title: Correlación entre solicitud y respuesta
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: 34a41a149e740faf0f3816bba2c9bd9b47d4996e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184546"
---
# <a name="request-reply-correlation"></a><span data-ttu-id="7c38d-102">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="7c38d-102">Request-Reply Correlation</span></span>
<span data-ttu-id="7c38d-103">La correlación solicitud-respuesta <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> se usa con un par para implementar <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> una operación bidireccional en un servicio de flujo de trabajo y con un par que invoca una operación bidireccional en otro servicio web.</span><span class="sxs-lookup"><span data-stu-id="7c38d-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="7c38d-104">Al invocar una operación bidireccional en un servicio WCF, el servicio puede ser un servicio tradicional de Windows Communication Foundation (WCF) basado en código imperativo o puede ser un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7c38d-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="7c38d-105">Para utilizar la correlación de solicitud-respuesta, debe usarse un enlace bidireccional, como <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="7c38d-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="7c38d-106">Ya invoque o implemente una operación bidireccional, los pasos de inicialización de la correlación son similares y se cubren en esta sección.</span><span class="sxs-lookup"><span data-stu-id="7c38d-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="7c38d-107">Utilizar correlación en una operación bidireccional con Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="7c38d-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="7c38d-108"><xref:System.ServiceModel.Activities.Receive> / Un <xref:System.ServiceModel.Activities.SendReply> par se usa para implementar una operación bidireccional en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7c38d-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="7c38d-109">El tiempo de ejecución usa una correlación de solicitud-respuesta para asegurarse de que la respuesta se envía al autor de la llamada correcto.</span><span class="sxs-lookup"><span data-stu-id="7c38d-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="7c38d-110">Cuando un flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, como es el caso de los servicios de flujo de trabajo, es suficiente la inicialización de correlación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7c38d-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="7c38d-111">En este escenario, un flujo de trabajo utiliza un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par y no se requiere ninguna configuración de correlación específica.</span><span class="sxs-lookup"><span data-stu-id="7c38d-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="7c38d-112">Inicializar explícitamente una correlación de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="7c38d-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="7c38d-113">Si se producen otras operaciones bidireccionales en paralelo, la correlación se debería configurar de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="7c38d-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="7c38d-114">Esto se puede hacer <xref:System.ServiceModel.Activities.CorrelationHandle> especificando <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>a y <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> , <xref:System.ServiceModel.Activities.CorrelationScope>o colocando el interior de un archivo .</span><span class="sxs-lookup"><span data-stu-id="7c38d-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="7c38d-115">En este ejemplo, la correlación <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> solicitud-respuesta se configura en un par.</span><span class="sxs-lookup"><span data-stu-id="7c38d-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="7c38d-116">En lugar de configurar explícitamente la correlación, se puede usar una actividad <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="7c38d-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="7c38d-117"><xref:System.ServiceModel.Activities.CorrelationScope> proporciona un <xref:System.ServiceModel.Activities.CorrelationHandle> implícito para las actividades de mensajería que contiene.</span><span class="sxs-lookup"><span data-stu-id="7c38d-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="7c38d-118">En este ejemplo, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par <xref:System.ServiceModel.Activities.CorrelationScope>se encuentra dentro de un archivo .</span><span class="sxs-lookup"><span data-stu-id="7c38d-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="7c38d-119">No se requiere ninguna configuración de correlación explícita.</span><span class="sxs-lookup"><span data-stu-id="7c38d-119">No explicit correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 <span data-ttu-id="7c38d-120">Si se requieren correlaciones adicionales, se pueden configurar mediante la propiedad <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> de las actividades de mensajería respectivas utilizando los tipos `CorrelationInitializer` deseados.</span><span class="sxs-lookup"><span data-stu-id="7c38d-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="7c38d-121">Utilizar correlación en una operación bidireccional con Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="7c38d-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="7c38d-122">Aunque <xref:System.ServiceModel.Activities.Receive> la actividad solo se puede usar <xref:System.ServiceModel.Activities.WorkflowServiceHost> <xref:System.ServiceModel.Activities.Send> en <xref:System.ServiceModel.Activities.Send> / un servicio de flujo de trabajo hospedado por , y el <xref:System.ServiceModel.Activities.ReceiveReply> par se puede usar en cualquier flujo de trabajo que debe invocar un método en un servicio web.</span><span class="sxs-lookup"><span data-stu-id="7c38d-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="7c38d-123">Si el flujo de trabajo se hospeda utilizando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se aplica la correlación predeterminada descrita en la sección anterior; si no es así, hay que configurar la correlación utilizando explícitamente las clases <xref:System.ServiceModel.Activities.CorrelationInitializer> y <xref:System.ServiceModel.Activities.CorrelationHandle> deseadas, o utilizando la administración de control implícita de <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="7c38d-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="7c38d-124">Cuando se usa **Agregar referencia** de servicio en un servicio con <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> operaciones bidireccionales, se generan actividades que ajustan una actividad de par internamente con la correlación Solicitud/Respuesta especificada explícitamente.</span><span class="sxs-lookup"><span data-stu-id="7c38d-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
