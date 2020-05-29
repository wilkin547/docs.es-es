---
title: <netHttpsBinding>
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: 842f2acb3be03be8171bcf7312f230fc06754511
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201041"
---
# \<netHttpsBinding>
<span data-ttu-id="93bb6-101">Representa un enlace que un servicio de Windows Communication Foundation (WCF) puede usar para configurar y exponer extremos que pueden comunicarse a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="93bb6-101">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="93bb6-102">Cuando se usa con un contrato dúplex, se usará WebSockets; si no, se usará HTTPS.</span><span class="sxs-lookup"><span data-stu-id="93bb6-102">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpsBinding>**  

## <a name="syntax"></a><span data-ttu-id="93bb6-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93bb6-103">Syntax</span></span>  
  
```xml  
<netHttpsBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpsBinding>
```  
  
## <a name="type"></a><span data-ttu-id="93bb6-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="93bb6-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93bb6-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93bb6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="93bb6-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93bb6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93bb6-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="93bb6-107">Attributes</span></span>  
  
|<span data-ttu-id="93bb6-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="93bb6-108">Attribute</span></span>|<span data-ttu-id="93bb6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="93bb6-109">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="93bb6-110">Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="93bb6-110">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="93bb6-111">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-111">The default is `false`.</span></span><br /><br /> <span data-ttu-id="93bb6-112">Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies.</span><span class="sxs-lookup"><span data-stu-id="93bb6-112">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="93bb6-113">De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="93bb6-113">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="93bb6-114">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="93bb6-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="93bb6-115">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="93bb6-116">Un recurso de Internet es local si tiene una dirección local.</span><span class="sxs-lookup"><span data-stu-id="93bb6-116">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="93bb6-117">Una dirección local es aquella que se encuentra en el mismo equipo, en la LAN local o en la intranet y se identifica, sintácticamente, por la falta de un punto (.) como en los URI `http://webserver/` y `http://localhost/` .</span><span class="sxs-lookup"><span data-stu-id="93bb6-117">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs `http://webserver/` and `http://localhost/`.</span></span><br /><br /> <span data-ttu-id="93bb6-118">Al establecer este atributo se determina si los extremos configurados con BasicHttpBinding utilizan el servidor proxy al obtener acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="93bb6-118">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="93bb6-119">Si este atributo es `true`, las solicitudes que se realicen en recursos locales de Internet no usarán el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="93bb6-119">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="93bb6-120">Utilice el nombre de host (en lugar del host local) si desea que los clientes pasen por un proxy al hablar con los servicios del mismo equipo cuando este atributo está establecido como `true`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-120">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="93bb6-121">Cuando este atributo es `false`, todas las solicitudes de Internet se realizan a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="93bb6-121">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="93bb6-122">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="93bb6-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="93bb6-123">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93bb6-124">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="93bb6-124">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="93bb6-125">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="93bb6-125">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="93bb6-126">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="93bb6-126">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="93bb6-127">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="93bb6-127">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="93bb6-128">Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="93bb6-128">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="93bb6-129">El valor predeterminado es 524288 (0x80000) bytes.</span><span class="sxs-lookup"><span data-stu-id="93bb6-129">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="93bb6-130">El administrador de búfer reduce el coste de utilizar los búferes con un grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="93bb6-130">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="93bb6-131">Es necesario que los búferes procesen los mensajes del servicio cuando salen del canal.</span><span class="sxs-lookup"><span data-stu-id="93bb6-131">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="93bb6-132">Si no hay memoria suficiente en el grupo de búferes para procesar la carga de mensajes, el administrador de búfer debe asignar memoria adicional del montón CLR, que aumenta la carga de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="93bb6-132">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="93bb6-133">La amplia asignación del montón de elementos no utilizados de CLR es una indicación de que el tamaño del grupo de búferes es demasiado pequeño y de que el rendimiento podría mejorar con una asignación mayor aumentando el límite especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="93bb6-133">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="93bb6-134">Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-134">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="93bb6-135">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="93bb6-135">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="93bb6-136">Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-136">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="93bb6-137">El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="93bb6-137">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="93bb6-138">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="93bb6-138">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="93bb6-139">The default is 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="93bb6-139">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="93bb6-140">Define el codificador utilizado para codificar el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="93bb6-140">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="93bb6-141">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="93bb6-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="93bb6-142">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="93bb6-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="93bb6-143">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="93bb6-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="93bb6-144">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="93bb6-144">The default is Text.</span></span> <span data-ttu-id="93bb6-145">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="93bb6-146">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="93bb6-147">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="93bb6-148">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="93bb6-148">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="93bb6-149">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="93bb6-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="93bb6-150">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="93bb6-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="93bb6-151">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93bb6-152">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="93bb6-152">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="93bb6-153">Un URI que contiene la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="93bb6-153">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="93bb6-154">Si `useSystemWebProxy` se establece como `true`, esta configuración debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-154">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="93bb6-155">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-155">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="93bb6-156">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="93bb6-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="93bb6-157">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93bb6-158">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="93bb6-158">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="93bb6-159">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="93bb6-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="93bb6-160">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="93bb6-161">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="93bb6-161">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="93bb6-162">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-162">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="93bb6-163">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="93bb6-163">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="93bb6-164">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="93bb6-164">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="93bb6-165">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="93bb6-165">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="93bb6-166">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="93bb6-166">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="93bb6-167">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="93bb6-167">The default is UTF8.</span></span> <span data-ttu-id="93bb6-168">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-168">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="93bb6-169">Un valor <xref:System.ServiceModel.TransferMode> válido que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="93bb6-169">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="93bb6-170">Valor de tipo booleano que especifica si se debería utilizar el proxy HTTP configurado automáticamente del sistema, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="93bb6-170">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="93bb6-171">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-171">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="93bb6-172">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93bb6-172">Child Elements</span></span>  
  
|<span data-ttu-id="93bb6-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="93bb6-173">Element</span></span>|<span data-ttu-id="93bb6-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="93bb6-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="93bb6-175">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-175">Defines the security settings for the binding.</span></span> <span data-ttu-id="93bb6-176">Este elemento es del tipo <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-176">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="93bb6-177">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-177">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="93bb6-178">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="93bb6-178">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93bb6-179">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93bb6-179">Parent Elements</span></span>  
  
|<span data-ttu-id="93bb6-180">Elemento</span><span class="sxs-lookup"><span data-stu-id="93bb6-180">Element</span></span>|<span data-ttu-id="93bb6-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="93bb6-181">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="93bb6-182">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="93bb6-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93bb6-183">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93bb6-183">Remarks</span></span>  
 <span data-ttu-id="93bb6-184">NetHttpBinding usa HTTPS como transporte para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="93bb6-184">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="93bb6-185">Cuando se usa con un contrato dúplex, se usará WebSockets.</span><span class="sxs-lookup"><span data-stu-id="93bb6-185">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="93bb6-186">Cuando se usa con un contrato de solicitud-respuesta, NetHttpsBinding se comportará como un BasicHttpsBinding con un codificador binario.</span><span class="sxs-lookup"><span data-stu-id="93bb6-186">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="93bb6-187">La seguridad está desactivada de forma predeterminada, pero se puede Agregar estableciendo el atributo de modo del [\<security>](security-of-basichttpbinding.md) elemento secundario en un valor distinto de `None` .</span><span class="sxs-lookup"><span data-stu-id="93bb6-187">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="93bb6-188">De forma predeterminada, usa una codificación de mensajes "Text" y codificación de texto UTF-8.</span><span class="sxs-lookup"><span data-stu-id="93bb6-188">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93bb6-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93bb6-189">Example</span></span>  
 <span data-ttu-id="93bb6-190">En el ejemplo siguiente se muestra el uso de la clase <xref:System.ServiceModel.NetHttpBinding> que proporciona comunicación HTTPS e interoperabilidad máxima a los servicios Web de primera y segunda generación.</span><span class="sxs-lookup"><span data-stu-id="93bb6-190">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="93bb6-191">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="93bb6-191">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="93bb6-192">El tipo de enlace se especifica en el atributo `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="93bb6-192">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="93bb6-193">Si desea configurar el enlace básico y cambiar algunos de sus valores, es necesario definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-193">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="93bb6-194">El extremo debe hacer referencia a la configuración de enlace por nombre utilizando el atributo `bindingConfiguration` del elemento `<endpoint>`, como se muestra en el siguiente código de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="93bb6-194">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding name="Binding1"
               hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpsBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="93bb6-195">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93bb6-195">Example</span></span>  
 <span data-ttu-id="93bb6-196">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="93bb6-196">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="93bb6-197">La funcionalidad del ejemplo anterior se puede llevar a cabo quitando bindingConfiguration de la dirección del punto de conexión y el nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="93bb6-197">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpsBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="93bb6-198">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="93bb6-198">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93bb6-199">Consulta también</span><span class="sxs-lookup"><span data-stu-id="93bb6-199">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="93bb6-200">Enlaces</span><span class="sxs-lookup"><span data-stu-id="93bb6-200">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="93bb6-201">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="93bb6-201">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="93bb6-202">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="93bb6-202">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
