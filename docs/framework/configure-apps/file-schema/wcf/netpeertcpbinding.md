---
title: '&lt;netPeerTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d20faaee94363a1f54cf398d72955f376087b36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetpeertcpbindinggt"></a><span data-ttu-id="e8aa7-102">&lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e8aa7-102">&lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="e8aa7-103">Define un enlace para la mensajería TCP concreta del canal del par.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-103">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="e8aa7-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8aa7-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-105">\<bindings></span></span>  
<span data-ttu-id="e8aa7-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-106">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8aa7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8aa7-107">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding name="string"  
         closeTimeout="TimeSpan"  
         openTimeout="TimeSpan"   
         receiveTimeout="TimeSpan"  
         sendTimeout="TimeSpan"  
         listenIPAddress="String"  
          maxBufferPoolSize="integer"  
         maxReceiveMessageSize="Integer"   
         port="Integer"  
         <security mode="None/Transport/Message/TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8aa7-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e8aa7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e8aa7-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8aa7-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8aa7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8aa7-110">Attributes</span></span>  
  
|<span data-ttu-id="e8aa7-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e8aa7-111">Attribute</span></span>|<span data-ttu-id="e8aa7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8aa7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8aa7-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="e8aa7-113">closeTimeout</span></span>|<span data-ttu-id="e8aa7-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e8aa7-115">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e8aa7-116">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="e8aa7-117">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="e8aa7-117">listenIPAddress</span></span>|<span data-ttu-id="e8aa7-118">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="e8aa7-119">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-119">The default is `null`.</span></span>|  
|<span data-ttu-id="e8aa7-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="e8aa7-120">maxBufferPoolSize</span></span>|<span data-ttu-id="e8aa7-121">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="e8aa7-122">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="e8aa7-122">The default is 524,288 bytes (512 * 1024).</span></span> <span data-ttu-id="e8aa7-123">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="e8aa7-124">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="e8aa7-125">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="e8aa7-126">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="e8aa7-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="e8aa7-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="e8aa7-128">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="e8aa7-129">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="e8aa7-130">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="e8aa7-131">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-131">The default is 65536.</span></span>|  
|<span data-ttu-id="e8aa7-132">name</span><span class="sxs-lookup"><span data-stu-id="e8aa7-132">name</span></span>|<span data-ttu-id="e8aa7-133">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e8aa7-134">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e8aa7-135">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e8aa7-136">Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e8aa7-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="e8aa7-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="e8aa7-137">openTimeout</span></span>|<span data-ttu-id="e8aa7-138">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e8aa7-139">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e8aa7-140">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="e8aa7-141">puerto</span><span class="sxs-lookup"><span data-stu-id="e8aa7-141">port</span></span>|<span data-ttu-id="e8aa7-142">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="e8aa7-143">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="e8aa7-144">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-144">The default is 0.</span></span>|  
|<span data-ttu-id="e8aa7-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e8aa7-145">receiveTimeout</span></span>|<span data-ttu-id="e8aa7-146">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e8aa7-147">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e8aa7-148">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="e8aa7-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="e8aa7-149">sendTimeout</span></span>|<span data-ttu-id="e8aa7-150">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e8aa7-151">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e8aa7-152">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8aa7-153">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e8aa7-153">Child Elements</span></span>  
  
|<span data-ttu-id="e8aa7-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8aa7-154">Element</span></span>|<span data-ttu-id="e8aa7-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8aa7-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8aa7-156">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-156">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="e8aa7-157">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e8aa7-158">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="e8aa7-159">\<resolución ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-159">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="e8aa7-160">Especifica una resolución del mismo nivel utilizada por este enlace para resolver un Id. de la malla del mismo nivel a las direcciones IP de puntos de conexión de nodos dentro de la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="e8aa7-161">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="e8aa7-162">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-162">Defines the security settings for the message.</span></span> <span data-ttu-id="e8aa7-163">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8aa7-164">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8aa7-164">Parent Elements</span></span>  
  
|<span data-ttu-id="e8aa7-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8aa7-165">Element</span></span>|<span data-ttu-id="e8aa7-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8aa7-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8aa7-167">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-167">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="e8aa7-168">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8aa7-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8aa7-169">Remarks</span></span>  
 <span data-ttu-id="e8aa7-170">Este enlace proporciona compatibilidad para la creación de aplicaciones punto a punto o de múltiples usuarios usando el transporte del mismo nivel a través de TCP.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="e8aa7-171">Cada nodo del mismo nivel puede hospedar múltiples canales del mismo nivel definidos con este tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8aa7-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8aa7-172">Example</span></span>  
 <span data-ttu-id="e8aa7-173">El ejemplo siguiente muestra cómo utilizar el enlace NetPeerTcpBinding, que proporciona comunicación multipartidaria mediante un canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e8aa7-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="e8aa7-174">Para un escenario detallado del uso de este enlace, vea [Net TCP del mismo nivel](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae).</span><span class="sxs-lookup"><span data-stu-id="e8aa7-174">For a detailed scenario of using this binding, see [Net Peer TCP](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<netPeerBinding>  
    <binding   
         closeTimeout="00:00:10"  
         openTimeout="00:00:20"   
         receiveTimeout="00:00:30"  
         sendTimeout="00:00:40"  
         maxBufferSize="1001"  
         maxConnections="123"   
         maxReceiveMessageSize="1000">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00"  
            enabled="true" />  
        <security mode="TransportWithMessageCredential">  
            <message clientCredentialType="CardSpace" />  
        </security>  
    </binding>  
</netPeerBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8aa7-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8aa7-175">See Also</span></span>  
 <xref:System.ServiceModel.NetPeerTcpBinding>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>  
 [<span data-ttu-id="e8aa7-176">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e8aa7-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e8aa7-177">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e8aa7-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e8aa7-178">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e8aa7-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e8aa7-179">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e8aa7-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="e8aa7-180">NET TCP del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e8aa7-180">Net Peer TCP</span></span>](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae)  
 [<span data-ttu-id="e8aa7-181">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="e8aa7-181">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
