---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 20ba643fddbac8a488e5457f0195cc253d4d23f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139316"
---
# \<ws2007FederationHttpBinding>

<span data-ttu-id="dece9-101">Un enlace seguro e interoperable que deriva de [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) y admite la seguridad federada.</span><span class="sxs-lookup"><span data-stu-id="dece9-101">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="dece9-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dece9-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="dece9-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dece9-103">Attributes and Elements</span></span>

<span data-ttu-id="dece9-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dece9-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="dece9-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="dece9-105">Attributes</span></span>

|<span data-ttu-id="dece9-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="dece9-106">Attribute</span></span>|<span data-ttu-id="dece9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dece9-107">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="dece9-108">Un valor que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="dece9-108">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="dece9-109">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="dece9-109">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="dece9-110">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="dece9-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="dece9-111">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dece9-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dece9-112">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="dece9-112">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="dece9-113">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="dece9-113">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="dece9-114">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="dece9-114">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="dece9-115">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="dece9-115">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="dece9-116">El tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="dece9-116">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="dece9-117">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="dece9-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="dece9-118">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="dece9-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="dece9-119">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="dece9-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="dece9-120">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="dece9-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="dece9-121">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="dece9-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="dece9-122">El tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="dece9-122">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="dece9-123">El remitente de un mensaje que supera este límite recibe un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="dece9-123">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="dece9-124">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dece9-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="dece9-125">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="dece9-125">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="dece9-126">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dece9-126">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="dece9-127">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dece9-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dece9-128">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="dece9-128">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="dece9-129">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="dece9-129">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="dece9-130">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="dece9-130">The default is Text.</span></span><br /><br /> <span data-ttu-id="dece9-131">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="dece9-131">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="dece9-132">Nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="dece9-132">The configuration name of the binding.</span></span> <span data-ttu-id="dece9-133">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="dece9-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="dece9-134">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="dece9-134">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="dece9-135">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="dece9-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="dece9-136">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="dece9-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="dece9-137">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dece9-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dece9-138">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="dece9-138">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="dece9-139">URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="dece9-139">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="dece9-140">El número de versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="dece9-140">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="dece9-141">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="dece9-141">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="dece9-142">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="dece9-142">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="dece9-143">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="dece9-143">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="dece9-144">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="dece9-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="dece9-145">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dece9-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dece9-146">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="dece9-146">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="dece9-147">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="dece9-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="dece9-148">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dece9-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dece9-149">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="dece9-149">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="dece9-150">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="dece9-150">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="dece9-151">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dece9-151">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dece9-152">-BigEndianUnicode: codificación Big Endian de Unicode.</span><span class="sxs-lookup"><span data-stu-id="dece9-152">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="dece9-153">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="dece9-153">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="dece9-154">-UTF8: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="dece9-154">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="dece9-155">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="dece9-155">The default is UTF8.</span></span> <span data-ttu-id="dece9-156">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="dece9-156">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="dece9-157">Valor que especifica si el enlace admite el flujo de transacciones de WS.</span><span class="sxs-lookup"><span data-stu-id="dece9-157">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="dece9-158">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="dece9-158">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="dece9-159">Un valor que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dece9-159">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="dece9-160">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="dece9-160">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="dece9-161">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="dece9-161">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="dece9-162">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dece9-162">Child Elements</span></span>

|<span data-ttu-id="dece9-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="dece9-163">Element</span></span>|<span data-ttu-id="dece9-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="dece9-164">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="dece9-165">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="dece9-165">Defines the security settings for the message.</span></span> <span data-ttu-id="dece9-166">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="dece9-166">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="dece9-167">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="dece9-167">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="dece9-168">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="dece9-168">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="dece9-169">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="dece9-169">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dece9-170">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dece9-170">Parent Elements</span></span>

|<span data-ttu-id="dece9-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="dece9-171">Element</span></span>|<span data-ttu-id="dece9-172">Descripción</span><span class="sxs-lookup"><span data-stu-id="dece9-172">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="dece9-173">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="dece9-173">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dece9-174">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dece9-174">Remarks</span></span>

<span data-ttu-id="dece9-175">La federación es la capacidad de compartir identidades en varias empresas o dominios de confianza para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="dece9-175">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="dece9-176">Utiliza el protocolo WS-Trust para asignar la representación de identidad de un dominio de confianza a otro.</span><span class="sxs-lookup"><span data-stu-id="dece9-176">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="dece9-177">El enlace HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="dece9-177">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="dece9-178">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="dece9-178">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="dece9-179">Para obtener más información, vea [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dece9-179">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="dece9-180">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dece9-180">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="dece9-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dece9-181">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [<span data-ttu-id="dece9-182">Enlaces</span><span class="sxs-lookup"><span data-stu-id="dece9-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dece9-183">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="dece9-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dece9-184">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="dece9-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
