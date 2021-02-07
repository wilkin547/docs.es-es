---
description: 'Más información acerca de: <netHttpBinding>'
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: ef7484367f84aadc741e1c1e515036531378c858
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684053"
---
# \<netHttpBinding>

<span data-ttu-id="a1d29-102">Representa un enlace que un servicio de Windows Communication Foundation (WCF) puede usar para configurar y exponer extremos que pueden comunicarse a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1d29-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="a1d29-103">Cuando se usa con un contrato dúplex, se usará WebSockets; si no, se usará HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1d29-103">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="a1d29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1d29-104">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="String"
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
</netHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="a1d29-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="a1d29-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1d29-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a1d29-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a1d29-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a1d29-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1d29-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a1d29-108">Attributes</span></span>  
  
|<span data-ttu-id="a1d29-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a1d29-109">Attribute</span></span>|<span data-ttu-id="a1d29-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1d29-110">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="a1d29-111">Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="a1d29-111">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="a1d29-112">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="a1d29-113">Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies.</span><span class="sxs-lookup"><span data-stu-id="a1d29-113">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="a1d29-114">De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="a1d29-114">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="a1d29-115">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="a1d29-115">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="a1d29-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="a1d29-117">Un recurso de Internet es local si tiene una dirección local.</span><span class="sxs-lookup"><span data-stu-id="a1d29-117">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="a1d29-118">Una dirección local es aquella que se encuentra en el mismo equipo, en la LAN local o en la intranet y se identifica, sintácticamente, por la falta de un punto (.) como en los URI `http://webserver/` y `http://localhost/` .</span><span class="sxs-lookup"><span data-stu-id="a1d29-118">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs `http://webserver/` and `http://localhost/`.</span></span><br /><br /> <span data-ttu-id="a1d29-119">Al establecer este atributo se determina si los extremos configurados con BasicHttpBinding utilizan el servidor proxy al obtener acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="a1d29-119">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="a1d29-120">Si este atributo es `true`, las solicitudes que se realicen en recursos locales de Internet no usarán el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="a1d29-120">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="a1d29-121">Utilice el nombre de host (en lugar del host local) si desea que los clientes pasen por un proxy al hablar con los servicios del mismo equipo cuando este atributo está establecido como `true`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-121">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="a1d29-122">Cuando este atributo es `false`, todas las solicitudes de Internet se realizan a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="a1d29-122">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="a1d29-123">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="a1d29-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a1d29-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a1d29-125">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a1d29-125">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="a1d29-126">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="a1d29-126">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="a1d29-127">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="a1d29-127">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="a1d29-128">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="a1d29-128">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="a1d29-129">Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="a1d29-129">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="a1d29-130">El valor predeterminado es 524288 (0x80000) bytes.</span><span class="sxs-lookup"><span data-stu-id="a1d29-130">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="a1d29-131">El administrador de búfer reduce el coste de utilizar los búferes con un grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="a1d29-131">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="a1d29-132">Es necesario que los búferes procesen los mensajes del servicio cuando salen del canal.</span><span class="sxs-lookup"><span data-stu-id="a1d29-132">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="a1d29-133">Si no hay memoria suficiente en el grupo de búferes para procesar la carga de mensajes, el administrador de búfer debe asignar memoria adicional del montón CLR, que aumenta la carga de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a1d29-133">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="a1d29-134">La amplia asignación del montón de elementos no utilizados de CLR es una indicación de que el tamaño del grupo de búferes es demasiado pequeño y de que el rendimiento podría mejorar con una asignación mayor aumentando el límite especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="a1d29-134">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="a1d29-135">Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-135">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="a1d29-136">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="a1d29-136">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="a1d29-137">Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-137">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="a1d29-138">El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="a1d29-138">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="a1d29-139">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a1d29-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="a1d29-140">The default is 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="a1d29-140">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="a1d29-141">Define el codificador utilizado para codificar el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="a1d29-141">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="a1d29-142">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1d29-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1d29-143">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="a1d29-143">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="a1d29-144">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="a1d29-144">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="a1d29-145">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="a1d29-145">The default is Text.</span></span> <span data-ttu-id="a1d29-146">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-146">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="a1d29-147">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-147">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a1d29-148">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-148">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a1d29-149">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="a1d29-149">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a1d29-150">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a1d29-150">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a1d29-151">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="a1d29-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a1d29-152">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a1d29-153">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a1d29-153">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="a1d29-154">Un URI que contiene la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1d29-154">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="a1d29-155">Si `useSystemWebProxy` se establece como `true`, esta configuración debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-155">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="a1d29-156">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-156">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a1d29-157">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="a1d29-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a1d29-158">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a1d29-159">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a1d29-159">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a1d29-160">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="a1d29-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a1d29-161">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a1d29-162">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a1d29-162">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="a1d29-163">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-163">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="a1d29-164">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1d29-164">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1d29-165">-BigEndianUnicode: codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="a1d29-165">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="a1d29-166">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="a1d29-166">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="a1d29-167">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="a1d29-167">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="a1d29-168">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="a1d29-168">The default is UTF8.</span></span> <span data-ttu-id="a1d29-169">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-169">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="a1d29-170">Un valor <xref:System.ServiceModel.TransferMode> válido que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="a1d29-170">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="a1d29-171">Valor de tipo booleano que especifica si se debería utilizar el proxy HTTP configurado automáticamente del sistema, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="a1d29-171">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="a1d29-172">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-172">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="a1d29-173">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a1d29-173">Child Elements</span></span>  
  
|<span data-ttu-id="a1d29-174">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1d29-174">Element</span></span>|<span data-ttu-id="a1d29-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1d29-175">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="a1d29-176">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-176">Defines the security settings for the binding.</span></span> <span data-ttu-id="a1d29-177">Este elemento es del tipo <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-177">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="a1d29-178">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-178">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a1d29-179">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a1d29-179">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1d29-180">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a1d29-180">Parent Elements</span></span>  
  
|<span data-ttu-id="a1d29-181">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1d29-181">Element</span></span>|<span data-ttu-id="a1d29-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1d29-182">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="a1d29-183">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="a1d29-183">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1d29-184">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a1d29-184">Remarks</span></span>  

 <span data-ttu-id="a1d29-185">NetHttpBinding usa HTTP como transporte para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1d29-185">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="a1d29-186">Cuando se usa con un contrato dúplex, se usará WebSockets.</span><span class="sxs-lookup"><span data-stu-id="a1d29-186">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="a1d29-187">Cuando se usa con un contrato de solicitud-respuesta, NetHttpBinding se comportará como un BasicHttpBinding con un codificador binario.</span><span class="sxs-lookup"><span data-stu-id="a1d29-187">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="a1d29-188">La seguridad está desactivada de forma predeterminada, pero se puede Agregar estableciendo el atributo de modo del [\<security>](security-of-basichttpbinding.md) elemento secundario en un valor distinto de `None` .</span><span class="sxs-lookup"><span data-stu-id="a1d29-188">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="a1d29-189">De forma predeterminada, usa una codificación de mensajes "Text" y codificación de texto UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a1d29-189">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1d29-190">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1d29-190">Example</span></span>  

 <span data-ttu-id="a1d29-191">En el ejemplo siguiente se muestra el uso de la clase <xref:System.ServiceModel.NetHttpBinding> que proporciona comunicación HTTP e interoperabilidad máxima a los servicios Web de primera y segunda generación.</span><span class="sxs-lookup"><span data-stu-id="a1d29-191">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="a1d29-192">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="a1d29-192">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="a1d29-193">El tipo de enlace se especifica en el atributo `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="a1d29-193">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="a1d29-194">Si desea configurar el enlace básico y cambiar algunos de sus valores, es necesario definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-194">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="a1d29-195">El extremo debe hacer referencia a la configuración de enlace por nombre utilizando el atributo `bindingConfiguration` del elemento `<endpoint>`, como se muestra en el siguiente código de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="a1d29-195">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="a1d29-196">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1d29-196">Example</span></span>  

 <span data-ttu-id="a1d29-197">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="a1d29-197">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a1d29-198">La funcionalidad del ejemplo anterior se puede llevar a cabo quitando bindingConfiguration de la dirección del punto de conexión y el nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="a1d29-198">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="a1d29-199">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a1d29-199">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d29-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1d29-200">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="a1d29-201">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a1d29-201">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a1d29-202">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a1d29-202">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a1d29-203">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a1d29-203">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
