---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: 183ce624d22162c2d665b173d8c04e132457a3fb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257257"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="5933a-101">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5933a-101">\<netNamedPipeBinding></span></span>
<span data-ttu-id="5933a-102">Define un enlace que es seguro, confiable y optimizado para la comunicación del proceso cruzado en equipo.</span><span class="sxs-lookup"><span data-stu-id="5933a-102">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="5933a-103">De forma predeterminada, genera una pila de comunicación de tiempo de ejecución con WS-ReliableMessaging para la fiabilidad, seguridad de transporte para la seguridad de transferencia, canalizaciones con nombre para la entrega de mensajes y codificación binaria de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5933a-103">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
 <span data-ttu-id="5933a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5933a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5933a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5933a-105">\<bindings></span></span>  
<span data-ttu-id="5933a-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5933a-106">\<netNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5933a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5933a-107">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5933a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5933a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5933a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5933a-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5933a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5933a-110">Attributes</span></span>  
  
|<span data-ttu-id="5933a-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5933a-111">Attribute</span></span>|<span data-ttu-id="5933a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5933a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5933a-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="5933a-113">closeTimeout</span></span>|<span data-ttu-id="5933a-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="5933a-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5933a-115">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5933a-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5933a-116">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5933a-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5933a-117">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="5933a-117">hostnameComparisonMode</span></span>|<span data-ttu-id="5933a-118">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="5933a-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="5933a-119">Este atributo es del tipo `System.ServiceModel.HostnameComparisonMode`, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="5933a-119">This attribute is of type `System.ServiceModel.HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="5933a-120">El valor predeterminado es `StrongWildcard`, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="5933a-120">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="5933a-121">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5933a-121">maxBufferPoolSize</span></span>|<span data-ttu-id="5933a-122">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-122">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="5933a-123">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="5933a-123">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="5933a-124">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="5933a-124">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="5933a-125">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="5933a-125">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="5933a-126">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="5933a-126">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="5933a-127">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="5933a-127">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="5933a-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="5933a-128">maxBufferSize</span></span>|<span data-ttu-id="5933a-129">Un entero positivo que especifica el tamaño máximo, en bytes, del búfer usado para almacenar los mensajes en memoria.</span><span class="sxs-lookup"><span data-stu-id="5933a-129">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="5933a-130">Si el búfer está completo, los datos excedentes permanecen en el socket subyacente hasta que el búfer tenga de nuevo espacio.</span><span class="sxs-lookup"><span data-stu-id="5933a-130">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="5933a-131">Este valor no puede ser menor que el del atributo `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="5933a-131">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="5933a-132">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="5933a-132">The default is 65536.</span></span> <span data-ttu-id="5933a-133">Para obtener más información, consulta <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="5933a-133">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="5933a-134">maxConnections</span><span class="sxs-lookup"><span data-stu-id="5933a-134">maxConnections</span></span>|<span data-ttu-id="5933a-135">Un entero que especifica el número máximo de conexiones salientes y entrantes que el servicio creará/aceptará.</span><span class="sxs-lookup"><span data-stu-id="5933a-135">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="5933a-136">Las conexiones entrantes y salientes se cuentan con respecto a un límite independiente especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="5933a-136">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="5933a-137">Las conexiones entrantes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="5933a-137">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="5933a-138">Las conexiones salientes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="5933a-138">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="5933a-139">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="5933a-139">The default is 10.</span></span>|  
|<span data-ttu-id="5933a-140">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5933a-140">maxReceivedMessageSize</span></span>|<span data-ttu-id="5933a-141">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-141">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="5933a-142">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="5933a-142">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="5933a-143">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5933a-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5933a-144">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="5933a-144">The default is 65536.</span></span>|  
|<span data-ttu-id="5933a-145">name</span><span class="sxs-lookup"><span data-stu-id="5933a-145">name</span></span>|<span data-ttu-id="5933a-146">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5933a-147">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5933a-148">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="5933a-148">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5933a-149">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5933a-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="5933a-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="5933a-150">openTimeout</span></span>|<span data-ttu-id="5933a-151">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="5933a-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5933a-152">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5933a-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5933a-153">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5933a-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5933a-154">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="5933a-154">receiveTimeout</span></span>|<span data-ttu-id="5933a-155">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="5933a-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5933a-156">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5933a-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5933a-157">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="5933a-157">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="5933a-158">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="5933a-158">sendTimeout</span></span>|<span data-ttu-id="5933a-159">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="5933a-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5933a-160">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5933a-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5933a-161">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5933a-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5933a-162">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="5933a-162">transactionFlow</span></span>|<span data-ttu-id="5933a-163">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="5933a-163">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="5933a-164">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="5933a-164">The default is `false`.</span></span>|  
|<span data-ttu-id="5933a-165">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="5933a-165">transactionProtocol</span></span>|<span data-ttu-id="5933a-166">Especifica el protocolo de transacción que se va a usar con este enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-166">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="5933a-167">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="5933a-167">Valid values are</span></span><br /><br /> <span data-ttu-id="5933a-168">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="5933a-168">-   OleTransactions</span></span><br /><span data-ttu-id="5933a-169">-   WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="5933a-169">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="5933a-170">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="5933a-170">The default is OleTransactions.</span></span> <span data-ttu-id="5933a-171">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="5933a-171">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="5933a-172">transferMode</span><span class="sxs-lookup"><span data-stu-id="5933a-172">transferMode</span></span>|<span data-ttu-id="5933a-173">Un valor <xref:System.ServiceModel.TransferMode> que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="5933a-173">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5933a-174">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5933a-174">Child Elements</span></span>  
  
|<span data-ttu-id="5933a-175">Elemento</span><span class="sxs-lookup"><span data-stu-id="5933a-175">Element</span></span>|<span data-ttu-id="5933a-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="5933a-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5933a-177">\<security></span><span class="sxs-lookup"><span data-stu-id="5933a-177">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="5933a-178">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-178">Defines the security settings for the binding.</span></span> <span data-ttu-id="5933a-179">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="5933a-179">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|[<span data-ttu-id="5933a-180">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="5933a-180">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="5933a-181">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-181">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5933a-182">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="5933a-182">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5933a-183">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5933a-183">Parent Elements</span></span>  
  
|<span data-ttu-id="5933a-184">Elemento</span><span class="sxs-lookup"><span data-stu-id="5933a-184">Element</span></span>|<span data-ttu-id="5933a-185">Descripción</span><span class="sxs-lookup"><span data-stu-id="5933a-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5933a-186">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5933a-186">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="5933a-187">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="5933a-187">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5933a-188">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5933a-188">Remarks</span></span>  
 <span data-ttu-id="5933a-189">De forma predeterminada, `NetNamedPipeBinding` genera una pila de comunicaciones en tiempo de ejecución que usa la seguridad de transporte, las canalizaciones con nombre para la entrega de mensajes y una codificación de mensajes binaria.</span><span class="sxs-lookup"><span data-stu-id="5933a-189">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="5933a-190">Este enlace es una opción adecuada proporcionada por sistema de Windows Communication Foundation (WCF) para la comunicación en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5933a-190">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="5933a-191">También admite transacciones.</span><span class="sxs-lookup"><span data-stu-id="5933a-191">It also supports transactions.</span></span>  
  
 <span data-ttu-id="5933a-192">La configuración predeterminada para `NetNamedPipeBinding` es similar a la configuración proporcionada por `NetTcpBinding`, pero es más simple, porque la implementación de WCF sólo está destinada a su uso en el equipo y, por consiguiente, hay menos características expuestas.</span><span class="sxs-lookup"><span data-stu-id="5933a-192">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="5933a-193">La diferencia más notable es que el valor `securityMode` sólo proporciona las opciones `None` y `Transport`.</span><span class="sxs-lookup"><span data-stu-id="5933a-193">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="5933a-194">La compatibilidad de seguridad SOAP no es una opción incluida.</span><span class="sxs-lookup"><span data-stu-id="5933a-194">SOAP security support is not an included option.</span></span> <span data-ttu-id="5933a-195">El comportamiento de seguridad es configurable mediante el parámetro opcional `securityMode`.</span><span class="sxs-lookup"><span data-stu-id="5933a-195">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5933a-196">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5933a-196">Example</span></span>  
 <span data-ttu-id="5933a-197">El ejemplo siguiente muestra el enlace netNamedPipeBinding, que proporciona la comunicación entre procesos del mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="5933a-197">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="5933a-198">Las canalizaciones con nombre no funcionan entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5933a-198">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="5933a-199">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="5933a-199">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="5933a-200">El tipo de enlace se especifica en el atributo de `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="5933a-200">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="5933a-201">Si desea configurar el enlace netNamedPipeBinding y cambiar algunos de sus valores, debe definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="5933a-201">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="5933a-202">El extremo debe hacer referencia a la configuración de enlace por el nombre con un atributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="5933a-202">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="5933a-203">En este ejemplo, la configuración de enlace se denomina Binding1.</span><span class="sxs-lookup"><span data-stu-id="5933a-203">In this example, the binding configuration is named Binding1.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="5933a-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="5933a-204">See also</span></span>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [<span data-ttu-id="5933a-205">\<binding></span><span class="sxs-lookup"><span data-stu-id="5933a-205">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="5933a-206">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5933a-206">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5933a-207">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5933a-207">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5933a-208">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5933a-208">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
