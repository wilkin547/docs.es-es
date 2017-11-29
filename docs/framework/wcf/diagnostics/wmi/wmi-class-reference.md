---
title: Referencia de clases WMI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee03f0c567f2b154eaf2e7fdf608b093cfbe2d1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="wmi-class-reference"></a><span data-ttu-id="1250a-102">Referencia de clases WMI</span><span class="sxs-lookup"><span data-stu-id="1250a-102">WMI Class Reference</span></span>
<span data-ttu-id="1250a-103">En esta sección se detallan todas las clases WMI expuestas por el proveedor de WMI [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1250a-103">This section lists all the WMI classes exposed by the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="1250a-104">Tener acceso a las instancias de WMI</span><span class="sxs-lookup"><span data-stu-id="1250a-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="1250a-105">No se puede crear directamente una instancia de todas las clases enumeradas en la Referencia de objeto WMI, excepto para Service, AppDomain, Contrat, ServiceAppDomain, ServiceToEndpointAssociation y Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1250a-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="1250a-106">Para tener acceso a otras instancias, puede tener acceso a las propiedades de las clases de nivel superior mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1250a-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="1250a-107">Por ejemplo, puede obtener acceso a la instancia TransportBindingElement desde la instancia Endpoint -> Binding -> BindingElements.</span><span class="sxs-lookup"><span data-stu-id="1250a-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1250a-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1250a-108">In This Section</span></span>  
 [<span data-ttu-id="1250a-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="1250a-109">ActivityTransfer</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/activitytransfer.md)  
  
 [<span data-ttu-id="1250a-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="1250a-110">AppDomainInfo</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md)  
  
 [<span data-ttu-id="1250a-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="1250a-111">AspNetCompatibilityRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="1250a-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-112">AsymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="1250a-113">"Clase behavior"</span><span class="sxs-lookup"><span data-stu-id="1250a-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="1250a-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-114">BinaryMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="1250a-115">Enlace</span><span class="sxs-lookup"><span data-stu-id="1250a-115">Binding</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/binding.md)  
  
 [<span data-ttu-id="1250a-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-116">BindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/bindingelement.md)  
  
 [<span data-ttu-id="1250a-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-117">CallbackBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/callbackbehavior.md)  
  
 [<span data-ttu-id="1250a-118">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="1250a-118">Channel class</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channel-class.md)  
  
 [<span data-ttu-id="1250a-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1250a-119">ChannelPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/channelpoolsettings.md)  
  
 [<span data-ttu-id="1250a-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="1250a-120">ClientCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientcredentials.md)  
  
 [<span data-ttu-id="1250a-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-121">ClientViaBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md)  
  
 [<span data-ttu-id="1250a-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-122">CompositeDuplexBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="1250a-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-123">ConnectionOrientedTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-124">Contrato</span><span class="sxs-lookup"><span data-stu-id="1250a-124">Contract</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/contract.md)  
  
 [<span data-ttu-id="1250a-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-125">CustomBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/custombindingelement.md)  
  
 [<span data-ttu-id="1250a-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="1250a-126">DeliveryRequirementsAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="1250a-127">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1250a-127">Endpoint</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)  
  
 [<span data-ttu-id="1250a-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-128">HttpsTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httpstransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-129">HttpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/httptransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1250a-130">LocalServiceSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/localservicesecuritysettings.md)  
  
 [<span data-ttu-id="1250a-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-131">MatchAllEndpointBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/matchallendpointbehavior.md)  
  
 [<span data-ttu-id="1250a-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-132">MessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/messageencodingbindingelement.md)  
  
 [<span data-ttu-id="1250a-133">Tracelistenerargument</span><span class="sxs-lookup"><span data-stu-id="1250a-133">MsmqBindingElementBase</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqbindingelementbase.md)  
  
 [<span data-ttu-id="1250a-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-134">MsmqIntegrationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="1250a-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-135">MsmqTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-136">MtomMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="1250a-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-137">MustUnderstandBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/mustunderstandbehavior.md)  
  
 [<span data-ttu-id="1250a-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1250a-138">NamedPipeConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="1250a-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-139">NamedPipeTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-140">OneWayBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/onewaybindingelement.md)  
  
 <span data-ttu-id="1250a-141">"Operation (clase)"</span><span class="sxs-lookup"><span data-stu-id="1250a-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="1250a-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="1250a-142">OperationBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/operationbehaviorattribute.md)  
  
 [<span data-ttu-id="1250a-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-143">PeerCustomResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="1250a-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-144">PeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peerresolverbindingelement.md)  
  
 [<span data-ttu-id="1250a-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1250a-145">PeerSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peersecuritysettings.md)  
  
 [<span data-ttu-id="1250a-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-146">PeerTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="1250a-147">PeerTransportSecuritySettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="1250a-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-148">PnrpPeerResolverBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="1250a-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-149">PrivacyNoticeBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/privacynoticebindingelement.md)  
  
 [<span data-ttu-id="1250a-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-150">ReliableSessionBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="1250a-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-151">SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md)  
  
 [<span data-ttu-id="1250a-152">Servicio</span><span class="sxs-lookup"><span data-stu-id="1250a-152">Service</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)  
  
 [<span data-ttu-id="1250a-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="1250a-153">ServiceAppDomain</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceappdomain.md)  
  
 [<span data-ttu-id="1250a-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-154">ServiceAuthorizationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="1250a-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="1250a-155">ServiceBehaviorAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicebehaviorattribute.md)  
  
 [<span data-ttu-id="1250a-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="1250a-156">ServiceCredentials</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicecredentials.md)  
  
 [<span data-ttu-id="1250a-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-157">ServiceDebugBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicedebugbehavior.md)  
  
 [<span data-ttu-id="1250a-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-158">ServiceMetadataBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicemetadatabehavior.md)  
  
 [<span data-ttu-id="1250a-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-159">ServiceSecurityAuditBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="1250a-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-160">ServiceThrottlingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="1250a-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-161">ServiceTimeoutsBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="1250a-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="1250a-162">ServiceToEndpointAssociation</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/servicetoendpointassociation.md)  
  
 [<span data-ttu-id="1250a-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-163">SslStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="1250a-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-164">SymmetricSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="1250a-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-165">SynchronousReceiveBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="1250a-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1250a-166">TcpConnectionPoolSettings</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="1250a-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-167">TcpTransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tcptransportbindingelement.md)  
  
 [<span data-ttu-id="1250a-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-168">TextMessageEncodingBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="1250a-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="1250a-169">TraceListener</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistener.md)  
  
 [<span data-ttu-id="1250a-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="1250a-170">TraceListenerArgument</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/tracelistenerargument.md)  
  
 [<span data-ttu-id="1250a-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-171">TransactedBatchingBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="1250a-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="1250a-172">TransactionFlowAttribute</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowattribute.md)  
  
 [<span data-ttu-id="1250a-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-173">TransactionFlowBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transactionflowbindingelement.md)  
  
 [<span data-ttu-id="1250a-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-174">TransportBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportbindingelement.md)  
  
 [<span data-ttu-id="1250a-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-175">TransportSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="1250a-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-176">UseManagedPresentationBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="1250a-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1250a-177">WindowsStreamSecurityBindingElement</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="1250a-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="1250a-178">WSAT_TraceEvent</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceevent.md)  
  
 [<span data-ttu-id="1250a-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="1250a-179">WSAT_TraceProvider</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-traceprovider.md)  
  
 [<span data-ttu-id="1250a-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="1250a-180">WSAT_TraceRecord</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/wsat-tracerecord.md)  
  
 [<span data-ttu-id="1250a-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="1250a-181">XmlDictionaryReaderQuotas</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="1250a-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="1250a-182">XmlSerializerOperationBehavior</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/xmlserializeroperationbehavior.md)
