---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 0f702788cf623651fd980b0443821b37acc7387c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204559"
---
# \<netPeerTcpBinding>

<span data-ttu-id="07e36-101">Define un enlace para la mensajería TCP concreta del canal del par.</span><span class="sxs-lookup"><span data-stu-id="07e36-101">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="07e36-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07e36-102">Syntax</span></span>  
  
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
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07e36-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="07e36-103">Attributes and Elements</span></span>  

 <span data-ttu-id="07e36-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="07e36-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07e36-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="07e36-105">Attributes</span></span>  
  
|<span data-ttu-id="07e36-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="07e36-106">Attribute</span></span>|<span data-ttu-id="07e36-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="07e36-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07e36-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="07e36-108">closeTimeout</span></span>|<span data-ttu-id="07e36-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e36-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="07e36-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e36-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e36-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07e36-111">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="07e36-112">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="07e36-112">listenIPAddress</span></span>|<span data-ttu-id="07e36-113">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="07e36-113">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="07e36-114">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="07e36-114">The default is `null`.</span></span>|  
|<span data-ttu-id="07e36-115">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="07e36-115">maxBufferPoolSize</span></span>|<span data-ttu-id="07e36-116">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="07e36-116">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="07e36-117">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="07e36-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="07e36-118">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="07e36-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="07e36-119">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="07e36-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="07e36-120">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="07e36-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="07e36-121">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="07e36-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="07e36-122">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="07e36-122">maxReceivedMessageSize</span></span>|<span data-ttu-id="07e36-123">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="07e36-123">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="07e36-124">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="07e36-124">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="07e36-125">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="07e36-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="07e36-126">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="07e36-126">The default is 65536.</span></span>|  
|<span data-ttu-id="07e36-127">name</span><span class="sxs-lookup"><span data-stu-id="07e36-127">name</span></span>|<span data-ttu-id="07e36-128">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="07e36-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="07e36-129">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="07e36-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="07e36-130">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="07e36-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="07e36-131">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="07e36-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="07e36-132">openTimeout</span><span class="sxs-lookup"><span data-stu-id="07e36-132">openTimeout</span></span>|<span data-ttu-id="07e36-133">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e36-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="07e36-134">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e36-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e36-135">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07e36-135">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="07e36-136">port</span><span class="sxs-lookup"><span data-stu-id="07e36-136">port</span></span>|<span data-ttu-id="07e36-137">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="07e36-137">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="07e36-138">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="07e36-138">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="07e36-139">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="07e36-139">The default is 0.</span></span>|  
|<span data-ttu-id="07e36-140">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="07e36-140">receiveTimeout</span></span>|<span data-ttu-id="07e36-141">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e36-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="07e36-142">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e36-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e36-143">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="07e36-143">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="07e36-144">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="07e36-144">sendTimeout</span></span>|<span data-ttu-id="07e36-145">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="07e36-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="07e36-146">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="07e36-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="07e36-147">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="07e36-147">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07e36-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="07e36-148">Child Elements</span></span>  
  
|<span data-ttu-id="07e36-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="07e36-149">Element</span></span>|<span data-ttu-id="07e36-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="07e36-150">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="07e36-151">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="07e36-151">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="07e36-152">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="07e36-152">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="07e36-153">Especifica una resolución del mismo nivel utilizada por este enlace para resolver un Id. de la malla del mismo nivel a las direcciones IP de extremos de nodos dentro de la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="07e36-153">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="07e36-154">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="07e36-154">Defines the security settings for the message.</span></span> <span data-ttu-id="07e36-155">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="07e36-155">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07e36-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="07e36-156">Parent Elements</span></span>  
  
|<span data-ttu-id="07e36-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="07e36-157">Element</span></span>|<span data-ttu-id="07e36-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="07e36-158">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="07e36-159">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="07e36-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07e36-160">Observaciones</span><span class="sxs-lookup"><span data-stu-id="07e36-160">Remarks</span></span>  

 <span data-ttu-id="07e36-161">Este enlace proporciona compatibilidad para la creación de aplicaciones punto a punto o de múltiples usuarios usando el transporte del mismo nivel a través de TCP.</span><span class="sxs-lookup"><span data-stu-id="07e36-161">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="07e36-162">Cada nodo del mismo nivel puede hospedar múltiples canales del mismo nivel definidos con este tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="07e36-162">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07e36-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07e36-163">Example</span></span>  

 <span data-ttu-id="07e36-164">El ejemplo siguiente muestra cómo utilizar el enlace NetPeerTcpBinding, que proporciona comunicación multipartidaria mediante un canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="07e36-164">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="07e36-165">Para ver un escenario detallado del uso de este enlace, vea [net peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="07e36-165">For a detailed scenario of using this binding, see [Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
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
  
## <a name="see-also"></a><span data-ttu-id="07e36-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07e36-166">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="07e36-167">Enlaces</span><span class="sxs-lookup"><span data-stu-id="07e36-167">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="07e36-168">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="07e36-168">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="07e36-169">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="07e36-169">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="07e36-170">[TCP del mismo nivel de red](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="07e36-170">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="07e36-171">Redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="07e36-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
