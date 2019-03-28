---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 01b8f20607de1cdd9c6b1ad9fc030c1d050ed749
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410646"
---
# <a name="ws2007httpbinding"></a><span data-ttu-id="ba682-101">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="ba682-101">\<ws2007HttpBinding></span></span>
<span data-ttu-id="ba682-102">Define un enlace interoperable que proporciona compatibilidad para las versiones correctas de los elementos de enlace <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, y <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba682-102">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="ba682-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba682-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ba682-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ba682-104">\<bindings></span></span>  
<span data-ttu-id="ba682-105">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="ba682-105">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba682-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba682-106">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
        <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"
                 negotiateServiceCredential="Boolean"
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
                 establishSecurityContext="Boolean"
                 negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba682-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba682-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ba682-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba682-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba682-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba682-109">Attributes</span></span>  
  
|<span data-ttu-id="ba682-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ba682-110">Attribute</span></span>|<span data-ttu-id="ba682-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba682-111">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="ba682-112">Un valor que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="ba682-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="ba682-113">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ba682-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="ba682-114">Puede utilizar esta propiedad al interactuar con los servicios Web ASP.NET (ASMX) que utilizan cookies.</span><span class="sxs-lookup"><span data-stu-id="ba682-114">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="ba682-115">Esto garantiza que las cookies que el servidor devuelve se copian automáticamente en todas las solicitudes futuras de cliente para ese servicio.</span><span class="sxs-lookup"><span data-stu-id="ba682-115">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="ba682-116">Un valor que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="ba682-116">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="ba682-117">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ba682-117">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="ba682-118">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba682-118">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="ba682-119">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba682-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba682-120">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba682-120">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="ba682-121">Especifica el modo de comparación del nombre del host HTTP usado para analizar los URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="ba682-121">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="ba682-122">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="ba682-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="ba682-123">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ba682-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="ba682-124">El tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-124">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="ba682-125">El valor predeterminado es 524.288 bytes (512 × 1.024).</span><span class="sxs-lookup"><span data-stu-id="ba682-125">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="ba682-126">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="ba682-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="ba682-127">Crear y destruir búferes cada vez que se usan es caro, como lo es la recolección de elementos no utilizados para los búferes.</span><span class="sxs-lookup"><span data-stu-id="ba682-127">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="ba682-128">Con los grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="ba682-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="ba682-129">Esto evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="ba682-129">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="ba682-130">El tamaño máximo del mensaje, en bytes, incluidos los encabezados, que puede recibir un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-130">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="ba682-131">El remitente de un mensaje que supere este límite recibe un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="ba682-131">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="ba682-132">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba682-132">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ba682-133">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="ba682-133">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="ba682-134">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ba682-134">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="ba682-135">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba682-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ba682-136">-   `Text`: Usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="ba682-136">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="ba682-137">-   `Mtom`: Usar un codificador Message Transmission organización Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="ba682-137">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="ba682-138">De manera predeterminada, es `Text`.</span><span class="sxs-lookup"><span data-stu-id="ba682-138">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="ba682-139">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="ba682-139">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="ba682-140">Nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-140">The configuration name of the binding.</span></span> <span data-ttu-id="ba682-141">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ba682-142">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="ba682-142">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ba682-143">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba682-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ba682-144">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba682-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ba682-145">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba682-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba682-146">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba682-146">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="ba682-147">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba682-147">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="ba682-148">Si `useSystemWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="ba682-148">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="ba682-149">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="ba682-149">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ba682-150">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba682-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ba682-151">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba682-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba682-152">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba682-152">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ba682-153">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="ba682-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ba682-154">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba682-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba682-155">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba682-155">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="ba682-156">Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-156">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="ba682-157">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba682-157">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ba682-158">-   `UnicodeFffeTextEncoding`: Big-Endian codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="ba682-158">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="ba682-159">-   `Utf16TextEncoding`: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="ba682-159">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="ba682-160">-   `Utf8TextEncoding`: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="ba682-160">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="ba682-161">De manera predeterminada, es `Utf8TextEncoding`.</span><span class="sxs-lookup"><span data-stu-id="ba682-161">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="ba682-162">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="ba682-162">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="ba682-163">Valor que especifica si el enlace admite el flujo de transacciones de WS.</span><span class="sxs-lookup"><span data-stu-id="ba682-163">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="ba682-164">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="ba682-164">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="ba682-165">Un valor que especifica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ba682-165">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="ba682-166">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="ba682-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba682-167">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba682-167">Child Elements</span></span>  
  
|<span data-ttu-id="ba682-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba682-168">Element</span></span>|<span data-ttu-id="ba682-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba682-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba682-170">\<security></span><span class="sxs-lookup"><span data-stu-id="ba682-170">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="ba682-171">Define la configuración de seguridad del enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-171">Defines the security settings for the binding.</span></span> <span data-ttu-id="ba682-172">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ba682-172">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="ba682-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ba682-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="ba682-174">Obtiene las restricciones de la complejidad de los mensajes SOAP que pueden procesar los extremos configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-174">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="ba682-175">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="ba682-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="ba682-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ba682-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="ba682-177">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="ba682-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba682-178">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba682-178">Parent Elements</span></span>  
  
|<span data-ttu-id="ba682-179">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba682-179">Element</span></span>|<span data-ttu-id="ba682-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba682-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba682-181">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ba682-181">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="ba682-182">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="ba682-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba682-183">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba682-183">Remarks</span></span>  
 <span data-ttu-id="ba682-184">`WS2007HttpBinding` agrega el enlace proporcionado por un sistema similar a `WSHttpBinding` pero usa las versiones estándar de la Organización para el avance de estándares de información estructurada (OASIS, Organization for the Advancement of Structured Information Standards) de los protocolos ReliableSession, Security y TransactionFlow.</span><span class="sxs-lookup"><span data-stu-id="ba682-184">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="ba682-185">Se requiere ningún cambio en el modelo de objetos o la configuración predeterminada cuando se utilice este enlace.</span><span class="sxs-lookup"><span data-stu-id="ba682-185">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba682-186">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba682-186">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007HttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </ws2007HttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="ba682-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba682-187">See also</span></span>
- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="ba682-188">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ba682-188">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ba682-189">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="ba682-189">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ba682-190">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ba682-190">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ba682-191">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba682-191">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
