---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 77b1383c1fcd3e867e6cef0ae5507b3a2ff8a80d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371390"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="574a0-101">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="574a0-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="574a0-102">Un enlace seguro e interoperable que deriva de [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) y admite seguridad federada.</span><span class="sxs-lookup"><span data-stu-id="574a0-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>

<span data-ttu-id="574a0-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="574a0-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="574a0-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="574a0-104">\<bindings>\\</span></span>
<span data-ttu-id="574a0-105">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="574a0-105">\<ws2007FederationHttpBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="574a0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="574a0-106">Syntax</span></span>

```xml
<ws2007FederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="574a0-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="574a0-107">Attributes and Elements</span></span>

<span data-ttu-id="574a0-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="574a0-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="574a0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="574a0-109">Attributes</span></span>

|<span data-ttu-id="574a0-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="574a0-110">Attribute</span></span>|<span data-ttu-id="574a0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="574a0-111">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="574a0-112">Un valor que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="574a0-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="574a0-113">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="574a0-113">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="574a0-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="574a0-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="574a0-115">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="574a0-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="574a0-116">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="574a0-116">The default is 00:01:00.</span></span>|
|`hostnameComparisonMode`|<span data-ttu-id="574a0-117">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="574a0-117">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="574a0-118">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="574a0-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="574a0-119">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="574a0-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="574a0-120">El tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="574a0-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="574a0-121">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="574a0-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="574a0-122">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="574a0-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="574a0-123">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="574a0-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="574a0-124">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="574a0-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="574a0-125">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="574a0-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="574a0-126">El tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="574a0-126">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="574a0-127">El remitente de un mensaje que supera este límite recibe un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="574a0-127">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="574a0-128">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="574a0-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="574a0-129">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="574a0-129">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="574a0-130">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="574a0-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="574a0-131">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="574a0-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="574a0-132">-Texto: Usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="574a0-132">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="574a0-133">-Mtom: Usar un codificador Message Transmission organización Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="574a0-133">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="574a0-134">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="574a0-134">The default is Text.</span></span><br /><br /> <span data-ttu-id="574a0-135">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="574a0-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="574a0-136">Nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="574a0-136">The configuration name of the binding.</span></span> <span data-ttu-id="574a0-137">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="574a0-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="574a0-138">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="574a0-138">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="574a0-139">Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="574a0-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="574a0-140">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="574a0-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="574a0-141">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="574a0-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="574a0-142">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="574a0-142">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="574a0-143">URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="574a0-143">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="574a0-144">El número de versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="574a0-144">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="574a0-145">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="574a0-145">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="574a0-146">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="574a0-146">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="574a0-147">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="574a0-147">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="574a0-148">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="574a0-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="574a0-149">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="574a0-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="574a0-150">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="574a0-150">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="574a0-151">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="574a0-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="574a0-152">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="574a0-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="574a0-153">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="574a0-153">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="574a0-154">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="574a0-154">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="574a0-155">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="574a0-155">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="574a0-156">-   BigEndianUnicode: Big-Endian codificación Unicode.</span><span class="sxs-lookup"><span data-stu-id="574a0-156">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="574a0-157">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="574a0-157">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="574a0-158">-   UTF8: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="574a0-158">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="574a0-159">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="574a0-159">The default is UTF8.</span></span> <span data-ttu-id="574a0-160">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="574a0-160">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="574a0-161">Valor que especifica si el enlace admite el flujo de transacciones de WS.</span><span class="sxs-lookup"><span data-stu-id="574a0-161">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="574a0-162">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="574a0-162">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="574a0-163">Un valor que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="574a0-163">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="574a0-164">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="574a0-164">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="574a0-165">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="574a0-165">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="574a0-166">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="574a0-166">Child Elements</span></span>

|<span data-ttu-id="574a0-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="574a0-167">Element</span></span>|<span data-ttu-id="574a0-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="574a0-168">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="574a0-169">\<security></span><span class="sxs-lookup"><span data-stu-id="574a0-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="574a0-170">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="574a0-170">Defines the security settings for the message.</span></span> <span data-ttu-id="574a0-171">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="574a0-171">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="574a0-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="574a0-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="574a0-173">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="574a0-173">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="574a0-174">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="574a0-174">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="574a0-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="574a0-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="574a0-176">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="574a0-176">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="574a0-177">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="574a0-177">Parent Elements</span></span>

|<span data-ttu-id="574a0-178">Elemento</span><span class="sxs-lookup"><span data-stu-id="574a0-178">Element</span></span>|<span data-ttu-id="574a0-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="574a0-179">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="574a0-180">\<bindings></span><span class="sxs-lookup"><span data-stu-id="574a0-180">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="574a0-181">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="574a0-181">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="574a0-182">Comentarios</span><span class="sxs-lookup"><span data-stu-id="574a0-182">Remarks</span></span>

<span data-ttu-id="574a0-183">La federación es la capacidad de compartir identidades en varias empresas o dominios de confianza para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="574a0-183">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="574a0-184">Utiliza el protocolo WS-Trust para asignar la representación de identidad de un dominio de confianza a otro.</span><span class="sxs-lookup"><span data-stu-id="574a0-184">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="574a0-185">El enlace HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="574a0-185">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="574a0-186">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="574a0-186">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="574a0-187">Para obtener más información, consulte [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="574a0-187">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="574a0-188">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="574a0-188">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="574a0-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="574a0-189">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="574a0-190">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="574a0-190">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="574a0-191">Enlaces</span><span class="sxs-lookup"><span data-stu-id="574a0-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="574a0-192">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="574a0-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="574a0-193">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="574a0-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="574a0-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="574a0-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
