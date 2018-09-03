---
title: Correlación de intercambio de contexto
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: d9de111fa08b4a398bba52bc903ea1fec8c7f298
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483702"
---
# <a name="context-exchange-correlation"></a><span data-ttu-id="d17c7-102">Correlación de intercambio de contexto</span><span class="sxs-lookup"><span data-stu-id="d17c7-102">Context Exchange Correlation</span></span>
<span data-ttu-id="d17c7-103">Correlación de contexto se basa en el mecanismo de intercambio de contexto descrito en la [especificación de protocolo de intercambio de contexto de .NET](https://go.microsoft.com/fwlink/?LinkId=166059).</span><span class="sxs-lookup"><span data-stu-id="d17c7-103">Context correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](https://go.microsoft.com/fwlink/?LinkId=166059).</span></span> <span data-ttu-id="d17c7-104">La correlación del contexto utiliza una cookie o un encabezado de contexto conocidos para relacionar los mensajes con la instancia correcta.</span><span class="sxs-lookup"><span data-stu-id="d17c7-104">Context correlation uses a well-known context header or cookie to relate messages to the correct instance.</span></span> <span data-ttu-id="d17c7-105">Para utilizar la correlación del contexto, debe usarse un enlace basado en contexto como <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> o <xref:System.ServiceModel.NetTcpContextBinding> en el extremo de <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d17c7-105">To use context correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint provided to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="d17c7-106">En este tema, se explica cómo utilizar la correlación del contexto con actividades de mensajería en un servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d17c7-106">This topic explains how to use context correlation with messaging activities in a workflow service.</span></span>  
  
## <a name="using-context-correlation"></a><span data-ttu-id="d17c7-107">Usar correlación del contexto</span><span class="sxs-lookup"><span data-stu-id="d17c7-107">Using Context Correlation</span></span>  
 <span data-ttu-id="d17c7-108">Se utiliza la correlación del contexto cuando un cliente debe realizar llamadas repetidas en un servicio del flujo de trabajo y el servicio se hospeda mediante uno de los enlaces del contexto.</span><span class="sxs-lookup"><span data-stu-id="d17c7-108">Context correlation is used when a client must make repeated calls into a workflow service and the service is hosted using one of the context bindings.</span></span> <span data-ttu-id="d17c7-109">Este tipo de correlación se inicializa mediante un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par en el servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d17c7-109">This type of correlation is initialized by a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair in the workflow service.</span></span> <span data-ttu-id="d17c7-110">El contexto se devuelve al cliente junto con la respuesta y, a continuación, el cliente adjunta dicho contexto en las llamadas al servicio posteriores.</span><span class="sxs-lookup"><span data-stu-id="d17c7-110">The context is sent back to the client together with the reply, and then the client attaches this context on subsequent calls to the service.</span></span>  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a><span data-ttu-id="d17c7-111">Configurar la correlación del contexto en un servicio del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d17c7-111">Configuring Context Correlation in a Workflow Service</span></span>  
 <span data-ttu-id="d17c7-112">La correlación del contexto se inicializa mediante una clase <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, que está asociada a la actividad <xref:System.ServiceModel.Activities.SendReply> que responde al mensaje entrante inicial.</span><span class="sxs-lookup"><span data-stu-id="d17c7-112">Context correlation is initialized by using a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> that is associated with the <xref:System.ServiceModel.Activities.SendReply> activity that replies to the initial incoming message.</span></span> <span data-ttu-id="d17c7-113">En el siguiente ejemplo, la clase <xref:System.ServiceModel.Activities.SendReply> se configura para inicializar una correlación del contexto.</span><span class="sxs-lookup"><span data-stu-id="d17c7-113">In the following example, the <xref:System.ServiceModel.Activities.SendReply> is configured to initialize a context correlation.</span></span>  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  <span data-ttu-id="d17c7-114">En este ejemplo se usan realmente dos tipos de correlación: la de contexto y la de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="d17c7-114">In this example, there are actually two types of correlation being used: context correlation and request-reply correlation.</span></span> <span data-ttu-id="d17c7-115">La correlación de contexto se usa para que las llamadas de los clientes se enruten a la instancia correcta.</span><span class="sxs-lookup"><span data-stu-id="d17c7-115">The context correlation is used so that calls from clients are routed to the correct instance.</span></span> <span data-ttu-id="d17c7-116">La correlación de solicitud-respuesta se usa en las actividades de <xref:System.ServiceModel.Activities.Receive> y de <xref:System.ServiceModel.Activities.SendReply> conjuntamente para implementar la operación bidireccional modelada por estas actividades.</span><span class="sxs-lookup"><span data-stu-id="d17c7-116">The request-reply correlation is used by the <xref:System.ServiceModel.Activities.Receive> and the <xref:System.ServiceModel.Activities.SendReply> activities together to implement the two-way operation modeled by these activities.</span></span> <span data-ttu-id="d17c7-117">En este ejemplo, solo la correlación del contexto se configura explícitamente y el <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par es mediante la correlación de solicitud-respuesta predeterminada proporcionada por implícito <xref:System.ServiceModel.Activities.CorrelationHandle> administración de <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d17c7-117">In this example, only the context correlation is explicitly configured, and the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is using the default request-reply correlation that is provided by the implicit <xref:System.ServiceModel.Activities.CorrelationHandle> management of <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="d17c7-118">Cuando se usa el **ReceiveAndSendReply** plantilla de actividad en el diseñador, la correlación de solicitud-respuesta flujo de trabajo se configura explícitamente.</span><span class="sxs-lookup"><span data-stu-id="d17c7-118">When using the **ReceiveAndSendReply** activity template in the workflow designer, request-reply correlation is explicitly configured.</span></span> <span data-ttu-id="d17c7-119">Para obtener más información sobre la correlación de solicitud-respuesta y administración de identificador de correlación implícita, vea [solicitud-respuesta](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) y [información general de correlación](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d17c7-119">For more information about request-reply correlation and implicit correlation handle management, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) and [Correlation Overview](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span></span> <span data-ttu-id="d17c7-120">Para obtener más información sobre la **ReceiveAndSendReply** plantilla de actividad, consulte [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span><span class="sxs-lookup"><span data-stu-id="d17c7-120">For more information about the **ReceiveAndSendReply** activity template, see [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span></span>  
  
 <span data-ttu-id="d17c7-121">Las actividades de <xref:System.ServiceModel.Activities.Receive> subsiguientes en el servicio del flujo de trabajo pueden hacer referencia a la clase <xref:System.ServiceModel.Activities.CorrelationHandle> inicializada por <xref:System.ServiceModel.Activities.SendReply> en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d17c7-121">Subsequent <xref:System.ServiceModel.Activities.Receive> activities in the workflow service can reference the <xref:System.ServiceModel.Activities.CorrelationHandle> that was initialized by the <xref:System.ServiceModel.Activities.SendReply> in the previous example.</span></span>  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 <span data-ttu-id="d17c7-122">A continuación, el extremo se configura en <xref:System.ServiceModel.Activities.WorkflowServiceHost> para utilizar un enlace basado en el contexto, como <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="d17c7-122">The endpoint is then configured on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> to use a context-based binding, such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span>  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a><span data-ttu-id="d17c7-123">Configurar la correlación del contexto en un cliente del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d17c7-123">Configuring Context Correlation in a Workflow Client</span></span>  
 <span data-ttu-id="d17c7-124">Cuando el cliente es otro flujo de trabajo, la correlación del contexto también se debe configurar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d17c7-124">When the client is another workflow, context correlation must be configured on the client as well.</span></span> <span data-ttu-id="d17c7-125">En el flujo de trabajo cliente, el <xref:System.ServiceModel.Activities.ReceiveReply> de la <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par que realiza la llamada inicial al servicio de flujo de trabajo debe configurarse con un <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="d17c7-125">On the client workflow, the <xref:System.ServiceModel.Activities.ReceiveReply> of the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that makes the initial call to the workflow service must be configured with a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 <span data-ttu-id="d17c7-126">Una vez inicializada la correlación, las actividades <xref:System.ServiceModel.Activities.Send> subsiguientes pueden utilizar <xref:System.ServiceModel.Activities.CorrelationHandle> para invocar métodos en la misma instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="d17c7-126">After the correlation is initialized, subsequent <xref:System.ServiceModel.Activities.Send> activities can use the <xref:System.ServiceModel.Activities.CorrelationHandle> to invoke methods on the same service instance.</span></span>  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 <span data-ttu-id="d17c7-127">Tenga en cuenta que, en estos ejemplos, la correlación del contexto se ha configurado explícitamente.</span><span class="sxs-lookup"><span data-stu-id="d17c7-127">Note that in these examples, the context correlation has been explicitly configured.</span></span> <span data-ttu-id="d17c7-128">Si el flujo de trabajo del cliente no se hospeda también en <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se debe configurar la correlación explícitamente, a menos que las actividades se incluyan en una actividad <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="d17c7-128">If the client workflow is not also hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, then correlation must be explicitly configured, unless the activities are contained within a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> <span data-ttu-id="d17c7-129">Para obtener más información sobre la correlación de contexto, vea el [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d17c7-129">For more information about context correlation, see the [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) sample.</span></span>  
  
 <span data-ttu-id="d17c7-130">Si el cliente que está realizando las llamadas al servicio del flujo de trabajo no es un flujo de trabajo, seguirá pudiendo realizar las llamadas repetidas, siempre y cuando pase explícitamente el contexto devuelto de la primera llamada al servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d17c7-130">If the client that is making calls to the workflow service is not a workflow, then it can still make repeated calls as long as it explicitly passes back the context that is returned from the first call to the workflow service.</span></span> <span data-ttu-id="d17c7-131">Los servidores proxy generados mediante la adición de una referencia del servicio en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] almacenan y pasan este contexto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d17c7-131">Proxies generated by adding a service reference in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] store and pass this context by default.</span></span>
