---
description: 'Más información acerca de: <ws2007FederationHttpBinding>'
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 90635805573e5bee64d8adf0f79de827733f178b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682194"
---
# \<ws2007FederationHttpBinding>

<span data-ttu-id="4b050-102">Un enlace seguro e interoperable que deriva de [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) y admite la seguridad federada.</span><span class="sxs-lookup"><span data-stu-id="4b050-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="4b050-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b050-103">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="4b050-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4b050-104">Attributes and Elements</span></span>

<span data-ttu-id="4b050-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4b050-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b050-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="4b050-106">Attributes</span></span>

|<span data-ttu-id="4b050-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="4b050-107">Attribute</span></span>|<span data-ttu-id="4b050-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b050-108">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="4b050-109">Un valor que indica si se omitirá el servidor proxy para las direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="4b050-109">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="4b050-110">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="4b050-110">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="4b050-111">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="4b050-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="4b050-112">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b050-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b050-113">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4b050-113">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="4b050-114">Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI.</span><span class="sxs-lookup"><span data-stu-id="4b050-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="4b050-115">Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI.</span><span class="sxs-lookup"><span data-stu-id="4b050-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="4b050-116">El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="4b050-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="4b050-117">El tamaño máximo del grupo de búferes para este enlace.</span><span class="sxs-lookup"><span data-stu-id="4b050-117">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="4b050-118">El valor predeterminado es 524.288 bytes (512x1024).</span><span class="sxs-lookup"><span data-stu-id="4b050-118">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="4b050-119">En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes.</span><span class="sxs-lookup"><span data-stu-id="4b050-119">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="4b050-120">Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara.</span><span class="sxs-lookup"><span data-stu-id="4b050-120">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="4b050-121">Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado.</span><span class="sxs-lookup"><span data-stu-id="4b050-121">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="4b050-122">Así se evita la sobrecarga al crear y destruir búferes.</span><span class="sxs-lookup"><span data-stu-id="4b050-122">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="4b050-123">El tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace.</span><span class="sxs-lookup"><span data-stu-id="4b050-123">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="4b050-124">El remitente de un mensaje que supera este límite recibe un error SOAP.</span><span class="sxs-lookup"><span data-stu-id="4b050-124">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="4b050-125">El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4b050-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="4b050-126">El valor predeterminado es 65536.</span><span class="sxs-lookup"><span data-stu-id="4b050-126">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="4b050-127">Define el codificador utilizado para codificar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4b050-127">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="4b050-128">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b050-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4b050-129">-Text: usar un codificador de mensajes de texto.</span><span class="sxs-lookup"><span data-stu-id="4b050-129">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="4b050-130">-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="4b050-130">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="4b050-131">El valor predeterminado es Text.</span><span class="sxs-lookup"><span data-stu-id="4b050-131">The default is Text.</span></span><br /><br /> <span data-ttu-id="4b050-132">Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="4b050-132">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="4b050-133">Nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="4b050-133">The configuration name of the binding.</span></span> <span data-ttu-id="4b050-134">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="4b050-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="4b050-135">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="4b050-135">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4b050-136">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b050-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="4b050-137">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="4b050-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="4b050-138">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b050-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b050-139">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4b050-139">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="4b050-140">URI en el que se encuentra el aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="4b050-140">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="4b050-141">El número de versión del aviso de privacidad actual.</span><span class="sxs-lookup"><span data-stu-id="4b050-141">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="4b050-142">Un URI que especifica la dirección del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="4b050-142">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="4b050-143">Si `useDefaultWebProxy` es `true`, este valor debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="4b050-143">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="4b050-144">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="4b050-144">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="4b050-145">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="4b050-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="4b050-146">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b050-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b050-147">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="4b050-147">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="4b050-148">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="4b050-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="4b050-149">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b050-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b050-150">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4b050-150">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="4b050-151">Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="4b050-151">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4b050-152">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b050-152">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4b050-153">-BigEndianUnicode: codificación Big Endian de Unicode.</span><span class="sxs-lookup"><span data-stu-id="4b050-153">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="4b050-154">-Unicode: codificación de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="4b050-154">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="4b050-155">-UTF8: codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="4b050-155">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="4b050-156">El valor predeterminado es UTF8.</span><span class="sxs-lookup"><span data-stu-id="4b050-156">The default is UTF8.</span></span> <span data-ttu-id="4b050-157">Este atributo es del tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4b050-157">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="4b050-158">Valor que especifica si el enlace admite el flujo de transacciones de WS.</span><span class="sxs-lookup"><span data-stu-id="4b050-158">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="4b050-159">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="4b050-159">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="4b050-160">Un valor que indica si se utiliza el proxy HTTP del sistema configurado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4b050-160">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="4b050-161">La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`.</span><span class="sxs-lookup"><span data-stu-id="4b050-161">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="4b050-162">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="4b050-162">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4b050-163">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4b050-163">Child Elements</span></span>

|<span data-ttu-id="4b050-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b050-164">Element</span></span>|<span data-ttu-id="4b050-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b050-165">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="4b050-166">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4b050-166">Defines the security settings for the message.</span></span> <span data-ttu-id="4b050-167">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="4b050-167">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="4b050-168">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="4b050-168">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4b050-169">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4b050-169">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="4b050-170">Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.</span><span class="sxs-lookup"><span data-stu-id="4b050-170">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4b050-171">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4b050-171">Parent Elements</span></span>

|<span data-ttu-id="4b050-172">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b050-172">Element</span></span>|<span data-ttu-id="4b050-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b050-173">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="4b050-174">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="4b050-174">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b050-175">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b050-175">Remarks</span></span>

<span data-ttu-id="4b050-176">La federación es la capacidad de compartir identidades en varias empresas o dominios de confianza para la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="4b050-176">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="4b050-177">Utiliza el protocolo WS-Trust para asignar la representación de identidad de un dominio de confianza a otro.</span><span class="sxs-lookup"><span data-stu-id="4b050-177">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="4b050-178">El enlace HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="4b050-178">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="4b050-179">Los servicios configurados con este enlace deben utilizar el transporte de HTTP.</span><span class="sxs-lookup"><span data-stu-id="4b050-179">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="4b050-180">Para obtener más información, vea [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4b050-180">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="4b050-181">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b050-181">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4b050-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b050-182">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [<span data-ttu-id="4b050-183">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4b050-183">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4b050-184">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="4b050-184">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4b050-185">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4b050-185">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
