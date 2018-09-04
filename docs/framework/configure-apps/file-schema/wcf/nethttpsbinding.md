---
title: '&lt;netHttpsBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: 2dbcdbe7fff758bab0e932817feddab398ed9ed1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526509"
---
# <a name="ltnethttpsbindinggt"></a><span data-ttu-id="aff17-102">&lt;netHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="aff17-102">&lt;netHttpsBinding&gt;</span></span>
<span data-ttu-id="aff17-103">Representa un enlace que puede usar un servicio de Windows Communication Foundation (WCF) para configurar y exponer extremos que pueden comunicarse a través de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="aff17-103">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="aff17-104">Cuando se usa con un contrato dúplex, se usará WebSockets; si no, se usará HTTPS.</span><span class="sxs-lookup"><span data-stu-id="aff17-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="aff17-105">Elemento raíz</span><span class="sxs-lookup"><span data-stu-id="aff17-105">Root Element</span></span>  
<span data-ttu-id="aff17-106">Siguiente elemento</span><span class="sxs-lookup"><span data-stu-id="aff17-106">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff17-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aff17-107">Syntax</span></span>  

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
               clientCredentialType="UserName/Certificate"/>  
    </security>  
    <readerQuotas maxArrayLength="Integer" 
                  maxBytesPerRead="Integer" 
                  maxDepth="Integer" 
                  maxNameTableCharCount="Integer" 
                  maxStringContentLength="Integer" />  
  </binding>  
</netHttpsBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="aff17-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="aff17-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aff17-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aff17-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aff17-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aff17-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aff17-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="aff17-111">Attributes</span></span>  
  
|<span data-ttu-id="aff17-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="aff17-112">Attribute</span></span>|<span data-ttu-id="aff17-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff17-113">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="aff17-114">Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="aff17-114">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="aff17-115">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="aff17-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="aff17-116">Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies.</span><span class="sxs-lookup"><span data-stu-id="aff17-116">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="aff17-117">De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="aff17-117">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="aff17-118">Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="aff17-118">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="aff17-119">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="aff17-119">The default is `false`.</span></span><br /><br /> <span data-ttu-id="aff17-120">Un recurso de Internet es local si tiene una dirección local.</span><span class="sxs-lookup"><span data-stu-id="aff17-120">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="aff17-121">Una dirección local es aquella que se encuentra en el mismo equipo, la LAN local o intranet y se identifica, sintácticamente, por la ausencia de un punto (.) como en los URI "http://webserver/" y "http://localhost/".</span><span class="sxs-lookup"><span data-stu-id="aff17-121">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="aff17-122">Al establecer este atributo se determina si los puntos de conexión configurados con BasicHttpBinding utilizan el servidor proxy al obtener acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="aff17-122">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="aff17-123">Si este atributo es `true`, las solicitudes que se realicen en recursos locales de Internet no usarán el servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="aff17-123">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="aff17-124">Utilice el nombre de host (en lugar del host local) si desea que los clientes pasen por un proxy al hablar con los servicios del mismo equipo cuando este atributo está establecido como `true`.</span><span class="sxs-lookup"><span data-stu-id="aff17-124">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="aff17-125">Cuando este atributo es `false`, todas las solicitudes de Internet se realizan a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="aff17-125">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="aff17-126">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="aff17-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="aff17-127">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="aff17-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="aff17-128">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="aff17-128">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="aff17-129">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="aff17-129">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="aff17-130">Este atributo es del tipo `HostnameComparisonMode`, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="aff17-130">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="aff17-131">El valor predeterminado es `StrongWildcard`, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="aff17-131">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="aff17-132">Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal.</span><span class="sxs-lookup"><span data-stu-id="aff17-132">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="aff17-133">El valor predeterminado es 524288 (0x80000) bytes.</span><span class="sxs-lookup"><span data-stu-id="aff17-133">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="aff17-134">El administrador de búfer reduce el coste de utilizar los búferes con un grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="aff17-134">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="aff17-135">Es necesario que los búferes procesen los mensajes del servicio cuando salen del canal.</span><span class="sxs-lookup"><span data-stu-id="aff17-135">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="aff17-136">Si no hay memoria suficiente en el grupo de búferes para procesar la carga de mensajes, el administrador de búfer debe asignar memoria adicional del montón CLR, que aumenta la carga de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="aff17-136">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="aff17-137">La amplia asignación del montón de elementos no utilizados de CLR es una indicación de que el tamaño del grupo de búferes es demasiado pequeño y de que el rendimiento podría mejorar con una asignación mayor aumentando el límite especificado por este atributo.</span><span class="sxs-lookup"><span data-stu-id="aff17-137">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="aff17-138">Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-138">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="aff17-139">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="aff17-139">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="aff17-140">Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-140">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="aff17-141">El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor.</span><span class="sxs-lookup"><span data-stu-id="aff17-141">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="aff17-142">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="aff17-142">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="aff17-143">El valor predeterminado es 65.536 bytes.</span><span class="sxs-lookup"><span data-stu-id="aff17-143">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="aff17-144">Define el codificador utilizado para codificar el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="aff17-144">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="aff17-145">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aff17-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="aff17-146">-Text: Utiliza un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="aff17-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="aff17-147">-Mtom: Usa un codificador Message Transmission organización Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="aff17-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="aff17-148">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="aff17-148">The default is Text.</span></span> <span data-ttu-id="aff17-149">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="aff17-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="aff17-150">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="aff17-151">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="aff17-152">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="aff17-152">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="aff17-153">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="aff17-153">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="aff17-154">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="aff17-154">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="aff17-155">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="aff17-155">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="aff17-156">Especifica el espacio de nombres XML del enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-156">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="aff17-157">El valor predeterminado es " http://tempuri.org/Bindings ".</span><span class="sxs-lookup"><span data-stu-id="aff17-157">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="aff17-158">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="aff17-158">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="aff17-159">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="aff17-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="aff17-160">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="aff17-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="aff17-161">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="aff17-161">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="aff17-162">Un URI que contiene la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="aff17-162">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="aff17-163">Si `useSystemWebProxy` se establece como `true`, esta configuración debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="aff17-163">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="aff17-164">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="aff17-164">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="aff17-165">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="aff17-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="aff17-166">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="aff17-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="aff17-167">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="aff17-167">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="aff17-168">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="aff17-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="aff17-169">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="aff17-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="aff17-170">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="aff17-170">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="aff17-171">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-171">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="aff17-172">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aff17-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="aff17-173">-BigEndianUnicode: Codificación Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="aff17-173">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="aff17-174">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="aff17-174">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="aff17-175">-UTF8: codificación de 8 bits</span><span class="sxs-lookup"><span data-stu-id="aff17-175">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="aff17-176">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="aff17-176">The default is UTF8.</span></span> <span data-ttu-id="aff17-177">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="aff17-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="aff17-178">Un valor <xref:System.ServiceModel.TransferMode> válido que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="aff17-178">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="aff17-179">Valor de tipo booleano que especifica si se debería utilizar el proxy HTTP configurado automáticamente del sistema, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="aff17-179">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="aff17-180">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="aff17-180">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="aff17-181">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aff17-181">Child Elements</span></span>  
  
|<span data-ttu-id="aff17-182">Elemento</span><span class="sxs-lookup"><span data-stu-id="aff17-182">Element</span></span>|<span data-ttu-id="aff17-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff17-183">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff17-184">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="aff17-184">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="aff17-185">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-185">Defines the security settings for the binding.</span></span> <span data-ttu-id="aff17-186">Este elemento es del tipo <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="aff17-186">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[<span data-ttu-id="aff17-187">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="aff17-187">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="aff17-188">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-188">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="aff17-189">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="aff17-189">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aff17-190">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aff17-190">Parent Elements</span></span>  
  
|<span data-ttu-id="aff17-191">Elemento</span><span class="sxs-lookup"><span data-stu-id="aff17-191">Element</span></span>|<span data-ttu-id="aff17-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff17-192">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff17-193">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="aff17-193">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="aff17-194">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="aff17-194">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aff17-195">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aff17-195">Remarks</span></span>  
 <span data-ttu-id="aff17-196">NetHttpBinding usa HTTPS como transporte para enviar mensajes.</span><span class="sxs-lookup"><span data-stu-id="aff17-196">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="aff17-197">Cuando se usa con un contrato dúplex, se usará WebSockets.</span><span class="sxs-lookup"><span data-stu-id="aff17-197">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="aff17-198">Cuando se usa con un contrato de solicitud-respuesta, NetHttpsBinding se comportará como un BasicHttpsBinding con un codificador binario.</span><span class="sxs-lookup"><span data-stu-id="aff17-198">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="aff17-199">Seguridad está desactivada de forma predeterminada, pero se puede agregar estableciendo el atributo de modo de la [ \<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) elemento secundario a un valor distinto de `None`.</span><span class="sxs-lookup"><span data-stu-id="aff17-199">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="aff17-200">De forma predeterminada, usa una codificación de mensajes "Text" y codificación de texto UTF-8.</span><span class="sxs-lookup"><span data-stu-id="aff17-200">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff17-201">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aff17-201">Example</span></span>  
 <span data-ttu-id="aff17-202">En el ejemplo siguiente se muestra el uso de la clase <xref:System.ServiceModel.NetHttpBinding> que proporciona comunicación HTTPS e interoperabilidad máxima a los servicios Web de primera y segunda generación.</span><span class="sxs-lookup"><span data-stu-id="aff17-202">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="aff17-203">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="aff17-203">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="aff17-204">El tipo de enlace se especifica en el atributo `binding` del elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="aff17-204">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="aff17-205">Si desea configurar el enlace básico  y cambiar algunos de sus valores, es necesario definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-205">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="aff17-206">El extremo debe hacer referencia a la configuración de enlace por nombre utilizando el atributo `bindingConfiguration` del elemento `<endpoint>`, como se muestra en el siguiente código de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="aff17-206">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="aff17-207">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aff17-207">Example</span></span>  
 <span data-ttu-id="aff17-208">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="aff17-208">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="aff17-209">La funcionalidad del ejemplo anterior se puede llevar a cabo quitando bindingConfiguration de la dirección del punto de conexión y el nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="aff17-209">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpsBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpsBinding>  
        <binding   
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
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="aff17-210">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="aff17-210">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff17-211">Vea también</span><span class="sxs-lookup"><span data-stu-id="aff17-211">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="aff17-212">Enlaces</span><span class="sxs-lookup"><span data-stu-id="aff17-212">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="aff17-213">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="aff17-213">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="aff17-214">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="aff17-214">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="aff17-215">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="aff17-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
