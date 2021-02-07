---
description: 'Más información acerca de: <netPeerTcpBinding>'
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 11f1618236c7219143225e2535e272254af6b81d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683910"
---
# \<netPeerTcpBinding>

<span data-ttu-id="d82e3-102">Define un enlace para la mensajería TCP concreta del canal del par.</span><span class="sxs-lookup"><span data-stu-id="d82e3-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="d82e3-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d82e3-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d82e3-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d82e3-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d82e3-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d82e3-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d82e3-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d82e3-106">Attributes</span></span>  
  
|<span data-ttu-id="d82e3-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="d82e3-107">Attribute</span></span>|<span data-ttu-id="d82e3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d82e3-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d82e3-109">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="d82e3-109">closeTimeout</span></span>|<span data-ttu-id="d82e3-110">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="d82e3-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d82e3-111">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d82e3-112">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d82e3-112">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d82e3-113">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="d82e3-113">listenIPAddress</span></span>|<span data-ttu-id="d82e3-114">Una cadena que especifica una dirección IP en la que el nodo entre pares realizará escuchas para los mensajes del TCP.</span><span class="sxs-lookup"><span data-stu-id="d82e3-114">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="d82e3-115">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="d82e3-115">The default is `null`.</span></span>|  
|<span data-ttu-id="d82e3-116">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="d82e3-116">maxBufferPoolSize</span></span>|<span data-ttu-id="d82e3-117">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="d82e3-117">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="d82e3-118">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="d82e3-118">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="d82e3-119">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="d82e3-119">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="d82e3-120">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="d82e3-120">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="d82e3-121">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="d82e3-121">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="d82e3-122">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="d82e3-122">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="d82e3-123">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d82e3-123">maxReceivedMessageSize</span></span>|<span data-ttu-id="d82e3-124">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d82e3-124">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="d82e3-125">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="d82e3-125">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="d82e3-126">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d82e3-126">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="d82e3-127">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="d82e3-127">The default is 65536.</span></span>|  
|<span data-ttu-id="d82e3-128">name</span><span class="sxs-lookup"><span data-stu-id="d82e3-128">name</span></span>|<span data-ttu-id="d82e3-129">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="d82e3-129">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d82e3-130">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="d82e3-130">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d82e3-131">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="d82e3-131">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d82e3-132">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d82e3-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="d82e3-133">openTimeout</span><span class="sxs-lookup"><span data-stu-id="d82e3-133">openTimeout</span></span>|<span data-ttu-id="d82e3-134">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="d82e3-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d82e3-135">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d82e3-136">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d82e3-136">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d82e3-137">port</span><span class="sxs-lookup"><span data-stu-id="d82e3-137">port</span></span>|<span data-ttu-id="d82e3-138">Un entero que especifica el puerto de la interfaz de red en el que este enlace procesará los mensajes de TCP de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d82e3-138">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="d82e3-139">Dicho valor debe encontrarse entre <xref:System.Net.IPEndPoint.MinPort> y <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-139">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="d82e3-140">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="d82e3-140">The default is 0.</span></span>|  
|<span data-ttu-id="d82e3-141">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="d82e3-141">receiveTimeout</span></span>|<span data-ttu-id="d82e3-142">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="d82e3-142">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d82e3-143">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-143">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d82e3-144">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d82e3-144">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="d82e3-145">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="d82e3-145">sendTimeout</span></span>|<span data-ttu-id="d82e3-146">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="d82e3-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d82e3-147">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d82e3-148">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d82e3-148">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d82e3-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d82e3-149">Child Elements</span></span>  
  
|<span data-ttu-id="d82e3-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="d82e3-150">Element</span></span>|<span data-ttu-id="d82e3-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="d82e3-151">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d82e3-152">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d82e3-152">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d82e3-153">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-153">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="d82e3-154">Especifica una resolución del mismo nivel utilizada por este enlace para resolver un Id. de la malla del mismo nivel a las direcciones IP de extremos de nodos dentro de la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d82e3-154">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="d82e3-155">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d82e3-155">Defines the security settings for the message.</span></span> <span data-ttu-id="d82e3-156">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d82e3-156">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d82e3-157">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d82e3-157">Parent Elements</span></span>  
  
|<span data-ttu-id="d82e3-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="d82e3-158">Element</span></span>|<span data-ttu-id="d82e3-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="d82e3-159">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="d82e3-160">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="d82e3-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d82e3-161">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d82e3-161">Remarks</span></span>  

 <span data-ttu-id="d82e3-162">Este enlace proporciona compatibilidad para la creación de aplicaciones punto a punto o de múltiples usuarios usando el transporte del mismo nivel a través de TCP.</span><span class="sxs-lookup"><span data-stu-id="d82e3-162">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="d82e3-163">Cada nodo del mismo nivel puede hospedar múltiples canales del mismo nivel definidos con este tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="d82e3-163">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d82e3-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d82e3-164">Example</span></span>  

 <span data-ttu-id="d82e3-165">El ejemplo siguiente muestra cómo utilizar el enlace NetPeerTcpBinding, que proporciona comunicación multipartidaria mediante un canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d82e3-165">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="d82e3-166">Para ver un escenario detallado del uso de este enlace, vea [net peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="d82e3-166">For a detailed scenario of using this binding, see [Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d82e3-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="d82e3-167">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="d82e3-168">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d82e3-168">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d82e3-169">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d82e3-169">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d82e3-170">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d82e3-170">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="d82e3-171">[TCP del mismo nivel de red](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d82e3-171">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="d82e3-172">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="d82e3-172">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
