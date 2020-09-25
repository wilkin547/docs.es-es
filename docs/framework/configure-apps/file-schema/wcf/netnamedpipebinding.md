---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: f1ec6091d72c1d1c6d75c44dd1f98d6d4e10ea12
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204572"
---
# \<netNamedPipeBinding>

<span data-ttu-id="d67dd-101">Define un enlace que es seguro, confiable y optimizado para la comunicación del proceso cruzado en equipo.</span><span class="sxs-lookup"><span data-stu-id="d67dd-101">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="d67dd-102">De forma predeterminada, genera una pila de comunicación de tiempo de ejecución con WS-ReliableMessaging para la fiabilidad, seguridad de transporte para la seguridad de transferencia, canalizaciones con nombre para la entrega de mensajes y codificación binaria de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d67dd-102">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="d67dd-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d67dd-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d67dd-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d67dd-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d67dd-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d67dd-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d67dd-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d67dd-106">Attributes</span></span>  
  
|<span data-ttu-id="d67dd-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="d67dd-107">Attribute</span></span>|<span data-ttu-id="d67dd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d67dd-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d67dd-109">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="d67dd-109">closeTimeout</span></span>|<span data-ttu-id="d67dd-110">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="d67dd-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d67dd-111">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d67dd-112">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d67dd-112">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d67dd-113">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="d67dd-113">hostNameComparisonMode</span></span>|<span data-ttu-id="d67dd-114">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="d67dd-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="d67dd-115">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="d67dd-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="d67dd-116">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="d67dd-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="d67dd-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="d67dd-117">maxBufferPoolSize</span></span>|<span data-ttu-id="d67dd-118">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-118">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="d67dd-119">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="d67dd-119">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="d67dd-120">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="d67dd-120">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="d67dd-121">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="d67dd-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="d67dd-122">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="d67dd-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="d67dd-123">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="d67dd-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="d67dd-124">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="d67dd-124">maxBufferSize</span></span>|<span data-ttu-id="d67dd-125">Un entero positivo que especifica el tamaño máximo, en bytes, del búfer usado para almacenar los mensajes en memoria.</span><span class="sxs-lookup"><span data-stu-id="d67dd-125">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="d67dd-126">Si el búfer está completo, los datos excedentes permanecen en el socket subyacente hasta que el búfer tenga de nuevo espacio.</span><span class="sxs-lookup"><span data-stu-id="d67dd-126">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="d67dd-127">Este valor no puede ser menor que el del atributo `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="d67dd-127">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="d67dd-128">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="d67dd-128">The default is 65536.</span></span> <span data-ttu-id="d67dd-129">Para obtener más información, vea <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-129">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="d67dd-130">maxConnections</span><span class="sxs-lookup"><span data-stu-id="d67dd-130">maxConnections</span></span>|<span data-ttu-id="d67dd-131">Un entero que especifica el número máximo de conexiones salientes y entrantes que el servicio creará/aceptará.</span><span class="sxs-lookup"><span data-stu-id="d67dd-131">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="d67dd-132">Las conexiones entrantes y salientes se cuentan con respecto a un límite independiente especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="d67dd-132">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="d67dd-133">Las conexiones entrantes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="d67dd-133">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="d67dd-134">Las conexiones salientes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="d67dd-134">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="d67dd-135">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="d67dd-135">The default is 10.</span></span>|  
|<span data-ttu-id="d67dd-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d67dd-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="d67dd-137">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="d67dd-138">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="d67dd-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="d67dd-139">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d67dd-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="d67dd-140">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="d67dd-140">The default is 65536.</span></span>|  
|<span data-ttu-id="d67dd-141">name</span><span class="sxs-lookup"><span data-stu-id="d67dd-141">name</span></span>|<span data-ttu-id="d67dd-142">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-142">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d67dd-143">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-143">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d67dd-144">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="d67dd-144">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d67dd-145">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d67dd-145">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="d67dd-146">openTimeout</span><span class="sxs-lookup"><span data-stu-id="d67dd-146">openTimeout</span></span>|<span data-ttu-id="d67dd-147">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="d67dd-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d67dd-148">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d67dd-149">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d67dd-149">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d67dd-150">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="d67dd-150">receiveTimeout</span></span>|<span data-ttu-id="d67dd-151">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="d67dd-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d67dd-152">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d67dd-153">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d67dd-153">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="d67dd-154">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="d67dd-154">sendTimeout</span></span>|<span data-ttu-id="d67dd-155">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="d67dd-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d67dd-156">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d67dd-157">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d67dd-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="d67dd-158">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="d67dd-158">transactionFlow</span></span>|<span data-ttu-id="d67dd-159">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="d67dd-159">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="d67dd-160">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="d67dd-160">The default is `false`.</span></span>|  
|<span data-ttu-id="d67dd-161">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="d67dd-161">transactionProtocol</span></span>|<span data-ttu-id="d67dd-162">Especifica el protocolo de transacción que se va a usar con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-162">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="d67dd-163">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="d67dd-163">Valid values are</span></span><br /><br /> <span data-ttu-id="d67dd-164">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="d67dd-164">-   OleTransactions</span></span><br /><span data-ttu-id="d67dd-165">-WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="d67dd-165">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="d67dd-166">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="d67dd-166">The default is OleTransactions.</span></span> <span data-ttu-id="d67dd-167">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-167">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="d67dd-168">transferMode</span><span class="sxs-lookup"><span data-stu-id="d67dd-168">transferMode</span></span>|<span data-ttu-id="d67dd-169">Un valor <xref:System.ServiceModel.TransferMode> que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="d67dd-169">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d67dd-170">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d67dd-170">Child Elements</span></span>  
  
|<span data-ttu-id="d67dd-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="d67dd-171">Element</span></span>|<span data-ttu-id="d67dd-172">Descripción</span><span class="sxs-lookup"><span data-stu-id="d67dd-172">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="d67dd-173">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-173">Defines the security settings for the binding.</span></span> <span data-ttu-id="d67dd-174">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-174">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d67dd-175">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-175">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d67dd-176">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d67dd-176">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d67dd-177">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d67dd-177">Parent Elements</span></span>  
  
|<span data-ttu-id="d67dd-178">Elemento</span><span class="sxs-lookup"><span data-stu-id="d67dd-178">Element</span></span>|<span data-ttu-id="d67dd-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="d67dd-179">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="d67dd-180">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="d67dd-180">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d67dd-181">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d67dd-181">Remarks</span></span>  

 <span data-ttu-id="d67dd-182">De forma predeterminada, `NetNamedPipeBinding` genera una pila de comunicaciones en tiempo de ejecución que usa la seguridad de transporte, las canalizaciones con nombre para la entrega de mensajes y una codificación de mensajes binaria.</span><span class="sxs-lookup"><span data-stu-id="d67dd-182">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="d67dd-183">Este enlace es una opción adecuada proporcionada por sistema de Windows Communication Foundation (WCF) para la comunicación en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d67dd-183">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="d67dd-184">También admite transacciones.</span><span class="sxs-lookup"><span data-stu-id="d67dd-184">It also supports transactions.</span></span>  
  
 <span data-ttu-id="d67dd-185">La configuración predeterminada para `NetNamedPipeBinding` es similar a la configuración proporcionada por `NetTcpBinding`, pero es más simple, porque la implementación de WCF sólo está destinada a su uso en el equipo y, por consiguiente, hay menos características expuestas.</span><span class="sxs-lookup"><span data-stu-id="d67dd-185">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="d67dd-186">La diferencia más notable es que el valor `securityMode` sólo proporciona las opciones `None` y `Transport`.</span><span class="sxs-lookup"><span data-stu-id="d67dd-186">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="d67dd-187">La compatibilidad de seguridad SOAP no es una opción incluida.</span><span class="sxs-lookup"><span data-stu-id="d67dd-187">SOAP security support is not an included option.</span></span> <span data-ttu-id="d67dd-188">El comportamiento de seguridad es configurable mediante el parámetro opcional `securityMode`.</span><span class="sxs-lookup"><span data-stu-id="d67dd-188">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d67dd-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d67dd-189">Example</span></span>  

 <span data-ttu-id="d67dd-190">El ejemplo siguiente muestra el enlace netNamedPipeBinding, que proporciona la comunicación entre procesos del mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="d67dd-190">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="d67dd-191">Las canalizaciones con nombre no funcionan entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d67dd-191">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="d67dd-192">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="d67dd-192">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="d67dd-193">El tipo de enlace se especifica en el atributo de `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="d67dd-193">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="d67dd-194">Si desea configurar el enlace netNamedPipeBinding y cambiar algunos de sus valores, debe definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="d67dd-194">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="d67dd-195">El extremo debe hacer referencia a la configuración de enlace por el nombre con un atributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="d67dd-195">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="d67dd-196">En este ejemplo, la configuración de enlace se denomina Binding1.</span><span class="sxs-lookup"><span data-stu-id="d67dd-196">In this example, the binding configuration is named Binding1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d67dd-197">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d67dd-197">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="d67dd-198">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d67dd-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d67dd-199">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d67dd-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d67dd-200">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d67dd-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
