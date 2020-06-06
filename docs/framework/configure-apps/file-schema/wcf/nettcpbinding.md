---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: c43c141093c8287adb6d5a841a43ac893deefccd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139346"
---
# \<netTcpBinding>

<span data-ttu-id="49de7-101">Especifica un enlace seguro, confiable y optimizado, adecuado para la comunicación entre equipos.</span><span class="sxs-lookup"><span data-stu-id="49de7-101">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="49de7-102">De forma predeterminada, genera una pila de comunicación en tiempo de ejecución con Seguridad de Windows para la seguridad y autenticación de mensajes, TCP para la entrega de mensajes y codificación binaria de mensajes.</span><span class="sxs-lookup"><span data-stu-id="49de7-102">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="49de7-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49de7-103">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49de7-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="49de7-104">Attributes and elements</span></span>

<span data-ttu-id="49de7-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="49de7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49de7-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="49de7-106">Attributes</span></span>  
  
|<span data-ttu-id="49de7-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="49de7-107">Attribute</span></span>|<span data-ttu-id="49de7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="49de7-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="49de7-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="49de7-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="49de7-110">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="49de7-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="49de7-111">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="49de7-111">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="49de7-112">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="49de7-112">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="49de7-113">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="49de7-113">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="49de7-114">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="49de7-114">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="49de7-115">Un entero positivo que especifica el número máximo de canales que esperan ser aceptados en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="49de7-115">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="49de7-116">Conexiones que sobrepasen este límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="49de7-116">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="49de7-117">El atributo `connectionTimeout` limita el tiempo durante el cual el cliente espera a ser conectado antes de iniciar una excepción de conexión.</span><span class="sxs-lookup"><span data-stu-id="49de7-117">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="49de7-118">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="49de7-118">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="49de7-119">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-119">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="49de7-120">El valor predeterminado es 512 \* 1024 bytes.</span><span class="sxs-lookup"><span data-stu-id="49de7-120">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="49de7-121">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="49de7-121">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="49de7-122">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="49de7-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="49de7-123">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="49de7-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="49de7-124">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="49de7-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="49de7-125">Un entero positivo que especifica el tamaño máximo, en bytes, del búfer usado para almacenar los mensajes en memoria.</span><span class="sxs-lookup"><span data-stu-id="49de7-125">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="49de7-126">Si el atributo `transferMode` es igual a `Buffered`, este atributo debe ser igual al valor del atributo `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="49de7-126">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="49de7-127">Si el atributo `transferMode` es igual a `Streamed`, este atributo no puede ser superior al valor del atributo `maxReceivedMessageSize`, y debe tener, al menos, el tamaño de los encabezados.</span><span class="sxs-lookup"><span data-stu-id="49de7-127">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="49de7-128">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="49de7-128">The default is 65536.</span></span> <span data-ttu-id="49de7-129">Para obtener más información, vea <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="49de7-129">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="49de7-130">Un entero que especifica el número máximo de conexiones salientes y entrantes que el servicio creará/aceptará.</span><span class="sxs-lookup"><span data-stu-id="49de7-130">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="49de7-131">Las conexiones entrantes y salientes se cuentan con respecto a un límite independiente especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="49de7-131">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="49de7-132">Las conexiones entrantes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="49de7-132">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="49de7-133">Las conexiones salientes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="49de7-133">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="49de7-134">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="49de7-134">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="49de7-135">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-135">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="49de7-136">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="49de7-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="49de7-137">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="49de7-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="49de7-138">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="49de7-138">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="49de7-139">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="49de7-140">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="49de7-141">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="49de7-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="49de7-142">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="49de7-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="49de7-143">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="49de7-143">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="49de7-144">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="49de7-144">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="49de7-145">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="49de7-145">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="49de7-146">Valor de tipo booleano que especifica si el uso compartido de puerto TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="49de7-146">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="49de7-147">Si éste es `false`, cada enlace utiliza su propio puerto exclusivo.</span><span class="sxs-lookup"><span data-stu-id="49de7-147">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="49de7-148">Este valor sólo es relevante para los servicios, porque los clientes no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="49de7-148">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="49de7-149">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="49de7-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="49de7-150">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="49de7-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="49de7-151">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="49de7-151">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="49de7-152">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="49de7-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="49de7-153">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="49de7-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="49de7-154">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="49de7-154">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="49de7-155">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="49de7-155">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="49de7-156">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="49de7-156">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="49de7-157">Especifica el protocolo de transacción que se va a usar con este enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-157">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="49de7-158">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="49de7-158">Valid values are</span></span><br /><br /> <span data-ttu-id="49de7-159">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="49de7-159">-   OleTransactions</span></span><br /><span data-ttu-id="49de7-160">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="49de7-160">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="49de7-161">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="49de7-161">The default is OleTransactions.</span></span> <span data-ttu-id="49de7-162">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="49de7-162">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="49de7-163">Un valor <xref:System.ServiceModel.TransferMode> que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="49de7-163">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49de7-164">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="49de7-164">Child elements</span></span>  
  
|<span data-ttu-id="49de7-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="49de7-165">Element</span></span>|<span data-ttu-id="49de7-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="49de7-166">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="49de7-167">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-167">Defines the security settings for the binding.</span></span> <span data-ttu-id="49de7-168">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="49de7-168">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="49de7-169">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-169">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="49de7-170">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="49de7-170">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="49de7-171">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="49de7-171">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49de7-172">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="49de7-172">Parent elements</span></span>  
  
|<span data-ttu-id="49de7-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="49de7-173">Element</span></span>|<span data-ttu-id="49de7-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="49de7-174">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="49de7-175">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="49de7-175">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49de7-176">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49de7-176">Remarks</span></span>

<span data-ttu-id="49de7-177">De forma predeterminada, este enlace genera una pila de comunicación en tiempo de ejecución que usa la seguridad de transporte, TCP para la entrega del mensaje y una codificación de mensajes binaria.</span><span class="sxs-lookup"><span data-stu-id="49de7-177">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="49de7-178">Este enlace es una opción proporcionada por el sistema Windows Communication Foundation (WCF) adecuada para la comunicación a través de una intranet.</span><span class="sxs-lookup"><span data-stu-id="49de7-178">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="49de7-179">La configuración predeterminada de `netTcpBinding` es más rápida que la proporcionada por `wsHttpBinding` , pero está destinada únicamente a la comunicación de WCF.</span><span class="sxs-lookup"><span data-stu-id="49de7-179">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="49de7-180">El comportamiento de seguridad es configurable mediante el parámetro opcional `securityMode`.</span><span class="sxs-lookup"><span data-stu-id="49de7-180">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="49de7-181">El uso de WS-ReliableMessaging es configurable utilizando el atributo `reliableSessionEnabled` opcional.</span><span class="sxs-lookup"><span data-stu-id="49de7-181">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="49de7-182">Pero la mensajería de confianza está apagada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49de7-182">But reliable messaging is off by default.</span></span> <span data-ttu-id="49de7-183">Más generalmente, los enlaces proporcionados por el sistema HTTP como `wsHttpBinding` y `basicHttpBinding` se configuran para activar de forma predeterminada las cosas, mientras que el enlace `netTcpBinding` desactiva de forma predeterminada las cosas para que tenga que inscribirse para obtener compatibilidad, por ejemplo, para una de las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="49de7-183">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="49de7-184">Esto significa que la configuración predeterminada para TCP es más rápida en intercambiar los mensajes entre los puntos de conexión que la configurada de forma predeterminada para los enlaces HTTP.</span><span class="sxs-lookup"><span data-stu-id="49de7-184">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49de7-185">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49de7-185">Example</span></span>

<span data-ttu-id="49de7-186">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="49de7-186">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="49de7-187">El tipo de enlace se especifica en el atributo de `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="49de7-187">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="49de7-188">Si desea configurar el enlace netTcpBinding y cambiar parte de su configuración, es necesario definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-188">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="49de7-189">El extremo debe hacer referencia a la configuración de enlace con un atributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="49de7-189">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="49de7-190">En el siguiente ejemplo, se define una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="49de7-190">In the following example, a binding configuration is defined.</span></span>  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="49de7-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49de7-191">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="49de7-192">Enlaces</span><span class="sxs-lookup"><span data-stu-id="49de7-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="49de7-193">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="49de7-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="49de7-194">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="49de7-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
