---
title: Referencia de clases WMI
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 9830fbf50e8df625e3d3077a66c66e0370204acb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262260"
---
# <a name="wmi-class-reference"></a><span data-ttu-id="9f921-102">Referencia de clases WMI</span><span class="sxs-lookup"><span data-stu-id="9f921-102">WMI Class Reference</span></span>

<span data-ttu-id="9f921-103">En esta sección se enumeran todas las clases WMI expuestas por el proveedor WMI de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9f921-103">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="9f921-104">Tener acceso a las instancias de WMI</span><span class="sxs-lookup"><span data-stu-id="9f921-104">Accessing WMI Instances</span></span>  

 <span data-ttu-id="9f921-105">No se puede crear directamente una instancia de todas las clases enumeradas en la Referencia de objeto WMI, excepto para Service, AppDomain, Contrat, ServiceAppDomain, ServiceToEndpointAssociation y Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9f921-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="9f921-106">Para tener acceso a otras instancias, puede tener acceso a las propiedades de las clases de nivel superior mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9f921-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="9f921-107">Por ejemplo, puede tener acceso a la instancia de TransportBindingElement desde la instancia del punto de conexión-> Binding-> BindingElements.</span><span class="sxs-lookup"><span data-stu-id="9f921-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f921-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9f921-108">In This Section</span></span>  

 [<span data-ttu-id="9f921-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="9f921-109">ActivityTransfer</span></span>](activitytransfer.md)  
  
 [<span data-ttu-id="9f921-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="9f921-110">AppDomainInfo</span></span>](appdomaininfo.md)  
  
 [<span data-ttu-id="9f921-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="9f921-111">AspNetCompatibilityRequirementsAttribute</span></span>](aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="9f921-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-112">AsymmetricSecurityBindingElement</span></span>](asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="9f921-113">"Clase de comportamiento"</span><span class="sxs-lookup"><span data-stu-id="9f921-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="9f921-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-114">BinaryMessageEncodingBindingElement</span></span>](binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="9f921-115">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9f921-115">Binding</span></span>](binding.md)  
  
 [<span data-ttu-id="9f921-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-116">BindingElement</span></span>](bindingelement.md)  
  
 [<span data-ttu-id="9f921-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-117">CallbackBehavior</span></span>](callbackbehavior.md)  
  
 [<span data-ttu-id="9f921-118">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="9f921-118">Channel class</span></span>](channel-class.md)  
  
 [<span data-ttu-id="9f921-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9f921-119">ChannelPoolSettings</span></span>](channelpoolsettings.md)  
  
 [<span data-ttu-id="9f921-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="9f921-120">ClientCredentials</span></span>](clientcredentials.md)  
  
 [<span data-ttu-id="9f921-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-121">ClientViaBehavior</span></span>](clientviabehavior.md)  
  
 [<span data-ttu-id="9f921-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-122">CompositeDuplexBindingElement</span></span>](compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="9f921-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-123">ConnectionOrientedTransportBindingElement</span></span>](connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-124">DataContract</span><span class="sxs-lookup"><span data-stu-id="9f921-124">Contract</span></span>](contract.md)  
  
 [<span data-ttu-id="9f921-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-125">CustomBindingElement</span></span>](custombindingelement.md)  
  
 [<span data-ttu-id="9f921-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="9f921-126">DeliveryRequirementsAttribute</span></span>](deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="9f921-127">Punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9f921-127">Endpoint</span></span>](endpoint.md)  
  
 [<span data-ttu-id="9f921-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-128">HttpsTransportBindingElement</span></span>](httpstransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-129">HttpTransportBindingElement</span></span>](httptransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9f921-130">LocalServiceSecuritySettings</span></span>](localservicesecuritysettings.md)  
  
 [<span data-ttu-id="9f921-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-131">MatchAllEndpointBehavior</span></span>](matchallendpointbehavior.md)  
  
 [<span data-ttu-id="9f921-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-132">MessageEncodingBindingElement</span></span>](messageencodingbindingelement.md)  
  
 [<span data-ttu-id="9f921-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="9f921-133">MsmqBindingElementBase</span></span>](msmqbindingelementbase.md)  
  
 [<span data-ttu-id="9f921-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-134">MsmqIntegrationBindingElement</span></span>](msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="9f921-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-135">MsmqTransportBindingElement</span></span>](msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-136">MtomMessageEncodingBindingElement</span></span>](mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="9f921-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-137">MustUnderstandBehavior</span></span>](mustunderstandbehavior.md)  
  
 [<span data-ttu-id="9f921-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9f921-138">NamedPipeConnectionPoolSettings</span></span>](namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="9f921-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-139">NamedPipeTransportBindingElement</span></span>](namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-140">OneWayBindingElement</span></span>](onewaybindingelement.md)  
  
 <span data-ttu-id="9f921-141">"Clase de operación"</span><span class="sxs-lookup"><span data-stu-id="9f921-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="9f921-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="9f921-142">OperationBehaviorAttribute</span></span>](operationbehaviorattribute.md)  
  
 [<span data-ttu-id="9f921-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-143">PeerCustomResolverBindingElement</span></span>](peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="9f921-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-144">PeerResolverBindingElement</span></span>](peerresolverbindingelement.md)  
  
 [<span data-ttu-id="9f921-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9f921-145">PeerSecuritySettings</span></span>](peersecuritysettings.md)  
  
 [<span data-ttu-id="9f921-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-146">PeerTransportBindingElement</span></span>](peertransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9f921-147">PeerTransportSecuritySettings</span></span>](peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="9f921-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-148">PnrpPeerResolverBindingElement</span></span>](pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="9f921-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-149">PrivacyNoticeBindingElement</span></span>](privacynoticebindingelement.md)  
  
 [<span data-ttu-id="9f921-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-150">ReliableSessionBindingElement</span></span>](reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="9f921-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-151">SecurityBindingElement</span></span>](securitybindingelement.md)  
  
 [<span data-ttu-id="9f921-152">Servicio</span><span class="sxs-lookup"><span data-stu-id="9f921-152">Service</span></span>](service.md)  
  
 [<span data-ttu-id="9f921-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f921-153">ServiceAppDomain</span></span>](serviceappdomain.md)  
  
 [<span data-ttu-id="9f921-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-154">ServiceAuthorizationBehavior</span></span>](serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="9f921-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="9f921-155">ServiceBehaviorAttribute</span></span>](servicebehaviorattribute.md)  
  
 [<span data-ttu-id="9f921-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="9f921-156">ServiceCredentials</span></span>](servicecredentials.md)  
  
 [<span data-ttu-id="9f921-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-157">ServiceDebugBehavior</span></span>](servicedebugbehavior.md)  
  
 [<span data-ttu-id="9f921-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-158">ServiceMetadataBehavior</span></span>](servicemetadatabehavior.md)  
  
 [<span data-ttu-id="9f921-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-159">ServiceSecurityAuditBehavior</span></span>](servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="9f921-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-160">ServiceThrottlingBehavior</span></span>](servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="9f921-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-161">ServiceTimeoutsBehavior</span></span>](servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="9f921-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="9f921-162">ServiceToEndpointAssociation</span></span>](servicetoendpointassociation.md)  
  
 [<span data-ttu-id="9f921-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-163">SslStreamSecurityBindingElement</span></span>](sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="9f921-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-164">SymmetricSecurityBindingElement</span></span>](symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="9f921-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-165">SynchronousReceiveBehavior</span></span>](synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="9f921-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9f921-166">TcpConnectionPoolSettings</span></span>](tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="9f921-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-167">TcpTransportBindingElement</span></span>](tcptransportbindingelement.md)  
  
 [<span data-ttu-id="9f921-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-168">TextMessageEncodingBindingElement</span></span>](textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="9f921-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="9f921-169">TraceListener</span></span>](tracelistener.md)  
  
 [<span data-ttu-id="9f921-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="9f921-170">TraceListenerArgument</span></span>](tracelistenerargument.md)  
  
 [<span data-ttu-id="9f921-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-171">TransactedBatchingBehavior</span></span>](transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="9f921-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="9f921-172">TransactionFlowAttribute</span></span>](transactionflowattribute.md)  
  
 [<span data-ttu-id="9f921-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-173">TransactionFlowBindingElement</span></span>](transactionflowbindingelement.md)  
  
 [<span data-ttu-id="9f921-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-174">TransportBindingElement</span></span>](transportbindingelement.md)  
  
 [<span data-ttu-id="9f921-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-175">TransportSecurityBindingElement</span></span>](transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="9f921-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-176">UseManagedPresentationBindingElement</span></span>](usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="9f921-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f921-177">WindowsStreamSecurityBindingElement</span></span>](windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="9f921-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="9f921-178">WSAT_TraceEvent</span></span>](wsat-traceevent.md)  
  
 [<span data-ttu-id="9f921-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="9f921-179">WSAT_TraceProvider</span></span>](wsat-traceprovider.md)  
  
 [<span data-ttu-id="9f921-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="9f921-180">WSAT_TraceRecord</span></span>](wsat-tracerecord.md)  
  
 [<span data-ttu-id="9f921-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="9f921-181">XmlDictionaryReaderQuotas</span></span>](xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="9f921-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="9f921-182">XmlSerializerOperationBehavior</span></span>](xmlserializeroperationbehavior.md)
