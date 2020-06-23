---
title: <netTcpBinding>
description: Representa un enlace seguro, confiable y optimizado diseñado únicamente para la comunicación entre equipos de WCF mediante TCP. La mensajería de confianza está desactivada de forma predeterminada.
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: 95c2c691bf328050f3d189c790d111d2fdeb1bb0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244002"
---
# \<netTcpBinding>

<span data-ttu-id="34c4c-103">Especifica un enlace seguro, confiable y optimizado, adecuado para la comunicación entre equipos.</span><span class="sxs-lookup"><span data-stu-id="34c4c-103">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="34c4c-104">De forma predeterminada, genera una pila de comunicación en tiempo de ejecución con Seguridad de Windows para la seguridad y autenticación de mensajes, TCP para la entrega de mensajes y codificación binaria de mensajes.</span><span class="sxs-lookup"><span data-stu-id="34c4c-104">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="34c4c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34c4c-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34c4c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="34c4c-106">Attributes and elements</span></span>

<span data-ttu-id="34c4c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="34c4c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34c4c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="34c4c-108">Attributes</span></span>  
  
|<span data-ttu-id="34c4c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="34c4c-109">Attribute</span></span>|<span data-ttu-id="34c4c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="34c4c-110">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="34c4c-111">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="34c4c-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="34c4c-112">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="34c4c-113">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="34c4c-113">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="34c4c-114">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="34c4c-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="34c4c-115">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="34c4c-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="34c4c-116">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="34c4c-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="34c4c-117">Un entero positivo que especifica el número máximo de canales que esperan ser aceptados en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="34c4c-117">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="34c4c-118">Conexiones que sobrepasen este límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="34c4c-118">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="34c4c-119">El atributo `connectionTimeout` limita el tiempo durante el cual el cliente espera a ser conectado antes de iniciar una excepción de conexión.</span><span class="sxs-lookup"><span data-stu-id="34c4c-119">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="34c4c-120">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="34c4c-120">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="34c4c-121">Entero que especifica el tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="34c4c-122">El valor predeterminado es 512 \* 1024 bytes.</span><span class="sxs-lookup"><span data-stu-id="34c4c-122">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="34c4c-123">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="34c4c-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="34c4c-124">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="34c4c-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="34c4c-125">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="34c4c-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="34c4c-126">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="34c4c-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="34c4c-127">Un entero positivo que especifica el tamaño máximo, en bytes, del búfer usado para almacenar los mensajes en memoria.</span><span class="sxs-lookup"><span data-stu-id="34c4c-127">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="34c4c-128">Si el atributo `transferMode` es igual a `Buffered`, este atributo debe ser igual al valor del atributo `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="34c4c-128">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="34c4c-129">Si el atributo `transferMode` es igual a `Streamed`, este atributo no puede ser superior al valor del atributo `maxReceivedMessageSize`, y debe tener, al menos, el tamaño de los encabezados.</span><span class="sxs-lookup"><span data-stu-id="34c4c-129">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="34c4c-130">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="34c4c-130">The default is 65536.</span></span> <span data-ttu-id="34c4c-131">Para obtener más información, vea <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-131">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="34c4c-132">Un entero que especifica el número máximo de conexiones salientes y entrantes que el servicio creará/aceptará.</span><span class="sxs-lookup"><span data-stu-id="34c4c-132">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="34c4c-133">Las conexiones entrantes y salientes se cuentan con respecto a un límite independiente especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="34c4c-133">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="34c4c-134">Las conexiones entrantes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="34c4c-134">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="34c4c-135">Las conexiones salientes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.</span><span class="sxs-lookup"><span data-stu-id="34c4c-135">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="34c4c-136">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="34c4c-136">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="34c4c-137">Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="34c4c-138">El remitente de un mensaje que supere este límite recibirá un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="34c4c-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="34c4c-139">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34c4c-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="34c4c-140">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="34c4c-140">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="34c4c-141">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-141">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="34c4c-142">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="34c4c-143">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="34c4c-143">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="34c4c-144">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="34c4c-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="34c4c-145">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="34c4c-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="34c4c-146">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="34c4c-147">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="34c4c-147">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="34c4c-148">Valor de tipo booleano que especifica si el uso compartido de puerto TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="34c4c-148">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="34c4c-149">Si éste es `false`, cada enlace utiliza su propio puerto exclusivo.</span><span class="sxs-lookup"><span data-stu-id="34c4c-149">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="34c4c-150">Este valor sólo es relevante para los servicios, porque los clientes no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="34c4c-150">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="34c4c-151">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="34c4c-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="34c4c-152">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="34c4c-153">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="34c4c-153">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="34c4c-154">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="34c4c-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="34c4c-155">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="34c4c-156">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="34c4c-156">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="34c4c-157">Valor booleano que especifica si el enlace admite las transacciones WS del flujo.</span><span class="sxs-lookup"><span data-stu-id="34c4c-157">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="34c4c-158">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="34c4c-158">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="34c4c-159">Especifica el protocolo de transacción que se va a usar con este enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-159">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="34c4c-160">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="34c4c-160">Valid values are</span></span><br /><br /> <span data-ttu-id="34c4c-161">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="34c4c-161">-   OleTransactions</span></span><br /><span data-ttu-id="34c4c-162">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="34c4c-162">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="34c4c-163">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="34c4c-163">The default is OleTransactions.</span></span> <span data-ttu-id="34c4c-164">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-164">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="34c4c-165">Un valor <xref:System.ServiceModel.TransferMode> que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="34c4c-165">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34c4c-166">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="34c4c-166">Child elements</span></span>  
  
|<span data-ttu-id="34c4c-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="34c4c-167">Element</span></span>|<span data-ttu-id="34c4c-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="34c4c-168">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="34c4c-169">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-169">Defines the security settings for the binding.</span></span> <span data-ttu-id="34c4c-170">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-170">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="34c4c-171">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-171">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="34c4c-172">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="34c4c-172">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="34c4c-173">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="34c4c-173">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34c4c-174">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="34c4c-174">Parent elements</span></span>  
  
|<span data-ttu-id="34c4c-175">Elemento</span><span class="sxs-lookup"><span data-stu-id="34c4c-175">Element</span></span>|<span data-ttu-id="34c4c-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="34c4c-176">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="34c4c-177">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="34c4c-177">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34c4c-178">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34c4c-178">Remarks</span></span>

<span data-ttu-id="34c4c-179">De forma predeterminada, este enlace genera una pila de comunicación en tiempo de ejecución que usa la seguridad de transporte, TCP para la entrega del mensaje y una codificación de mensajes binaria.</span><span class="sxs-lookup"><span data-stu-id="34c4c-179">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="34c4c-180">Este enlace es una opción proporcionada por el sistema Windows Communication Foundation (WCF) adecuada para la comunicación a través de una intranet.</span><span class="sxs-lookup"><span data-stu-id="34c4c-180">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="34c4c-181">La configuración predeterminada de `netTcpBinding` es más rápida que la proporcionada por `wsHttpBinding` , pero está destinada únicamente a la comunicación de WCF.</span><span class="sxs-lookup"><span data-stu-id="34c4c-181">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="34c4c-182">El comportamiento de seguridad es configurable mediante el parámetro opcional `securityMode`.</span><span class="sxs-lookup"><span data-stu-id="34c4c-182">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="34c4c-183">El uso de WS-ReliableMessaging es configurable utilizando el atributo `reliableSessionEnabled` opcional.</span><span class="sxs-lookup"><span data-stu-id="34c4c-183">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="34c4c-184">Pero la mensajería de confianza está apagada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34c4c-184">But reliable messaging is off by default.</span></span> <span data-ttu-id="34c4c-185">Más generalmente, los enlaces proporcionados por el sistema HTTP como `wsHttpBinding` y `basicHttpBinding` se configuran para activar de forma predeterminada las cosas, mientras que el enlace `netTcpBinding` desactiva de forma predeterminada las cosas para que tenga que inscribirse para obtener compatibilidad, por ejemplo, para una de las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="34c4c-185">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="34c4c-186">Esto significa que la configuración predeterminada para TCP es más rápida en intercambiar los mensajes entre los puntos de conexión que la configurada de forma predeterminada para los enlaces HTTP.</span><span class="sxs-lookup"><span data-stu-id="34c4c-186">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34c4c-187">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34c4c-187">Example</span></span>

<span data-ttu-id="34c4c-188">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="34c4c-188">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="34c4c-189">El tipo de enlace se especifica en el atributo de `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="34c4c-189">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="34c4c-190">Si desea configurar el enlace netTcpBinding y cambiar parte de su configuración, es necesario definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-190">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="34c4c-191">El extremo debe hacer referencia a la configuración de enlace con un atributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="34c4c-191">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="34c4c-192">En el siguiente ejemplo, se define una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="34c4c-192">In the following example, a binding configuration is defined.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34c4c-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="34c4c-193">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="34c4c-194">Enlaces</span><span class="sxs-lookup"><span data-stu-id="34c4c-194">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="34c4c-195">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="34c4c-195">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="34c4c-196">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="34c4c-196">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
