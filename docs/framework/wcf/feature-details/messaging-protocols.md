---
title: Protocolos de mensajería
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 70972f6a211d60d9fd330277040428ef783e9668
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631521"
---
# <a name="messaging-protocols"></a><span data-ttu-id="6ac92-102">Protocolos de mensajería</span><span class="sxs-lookup"><span data-stu-id="6ac92-102">Messaging Protocols</span></span>

<span data-ttu-id="6ac92-103">La pila de canales de Windows Communication Foundation (WCF) emplea codificación y canales de transporte para transformar la representación interna de mensajes en su formato de conexión y enviarla utilizando un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="6ac92-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="6ac92-104">El transporte más común utilizado para la interoperabilidad de servicios Web es HTTP y las codificaciones más comunes utilizadas por los servicios Web son las basadas en XML, SOAP 1.1, SOAP 1.2 y el Mecanismo de optimización de transmisión de mensajes (MTOM).</span><span class="sxs-lookup"><span data-stu-id="6ac92-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>

<span data-ttu-id="6ac92-105">En este tema se trata los detalles de implementación de WCF para los siguientes protocolos empleados por <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6ac92-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>

<span data-ttu-id="6ac92-106">Documento de especificaciones /:</span><span class="sxs-lookup"><span data-stu-id="6ac92-106">Specification/document:</span></span>

- [<span data-ttu-id="6ac92-107">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="6ac92-107">HTTP 1.1</span></span>](https://www.ietf.org/rfc/rfc2616.txt)
- <span data-ttu-id="6ac92-108">[Enlace SOAP 1.1 HTTP](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), sección 7</span><span class="sxs-lookup"><span data-stu-id="6ac92-108">[SOAP 1.1 HTTP Binding](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Section 7</span></span>
- <span data-ttu-id="6ac92-109">[Enlace HTTP 1.2 de SOAP](https://www.w3.org/TR/soap12-part2) sección 7</span><span class="sxs-lookup"><span data-stu-id="6ac92-109">[SOAP 1.2 HTTP Binding](https://www.w3.org/TR/soap12-part2) Section 7</span></span>

<span data-ttu-id="6ac92-110">En este tema cubre los detalles de implementación de WCF para los siguientes protocolos <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> emplear.</span><span class="sxs-lookup"><span data-stu-id="6ac92-110">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>

<span data-ttu-id="6ac92-111">Documento de especificaciones /:</span><span class="sxs-lookup"><span data-stu-id="6ac92-111">Specification/Document:</span></span>

- [<span data-ttu-id="6ac92-112">XML</span><span class="sxs-lookup"><span data-stu-id="6ac92-112">XML</span></span>](https://www.w3.org/TR/REC-xml)
- [<span data-ttu-id="6ac92-113">SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="6ac92-113">SOAP 1.1</span></span>](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [<span data-ttu-id="6ac92-114">Núcleo de SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="6ac92-114">SOAP 1.2 Core</span></span>](https://www.w3.org/TR/soap12-part1/)
- [<span data-ttu-id="6ac92-115">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="6ac92-115">WS-Addressing 2004/08</span></span>](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [<span data-ttu-id="6ac92-116">W3C Web Services Addressing 1.0 - núcleo</span><span class="sxs-lookup"><span data-stu-id="6ac92-116">W3C Web Services Addressing 1.0 - Core</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [<span data-ttu-id="6ac92-117">W3C Web Services Addressing 1.0 - enlace SOAP</span><span class="sxs-lookup"><span data-stu-id="6ac92-117">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [<span data-ttu-id="6ac92-118">W3C Web Services Addressing 1.0 – enlace WSDL</span><span class="sxs-lookup"><span data-stu-id="6ac92-118">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [<span data-ttu-id="6ac92-119">W3C Web Services Addressing 1.0 - metadatos</span><span class="sxs-lookup"><span data-stu-id="6ac92-119">W3C Web Services Addressing 1.0 - Metadata</span></span>](https://www.w3.org/TR/ws-addr-metadata/)
- [<span data-ttu-id="6ac92-120">Enlace SOAP 1.1 de WSDL</span><span class="sxs-lookup"><span data-stu-id="6ac92-120">WSDL SOAP1.1 Binding</span></span>](https://www.w3.org/TR/wsdl/)
- [<span data-ttu-id="6ac92-121">Enlace SOAP 1.2 de WSDL</span><span class="sxs-lookup"><span data-stu-id="6ac92-121">WSDL SOAP1.2 Binding</span></span>](https://www.w3.org/Submission/wsdl11soap12/)

<span data-ttu-id="6ac92-122">En este tema cubre los detalles de implementación de WCF para los siguientes protocolos <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> emplea.</span><span class="sxs-lookup"><span data-stu-id="6ac92-122">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>

<span data-ttu-id="6ac92-123">Documento de especificaciones /:</span><span class="sxs-lookup"><span data-stu-id="6ac92-123">Specification/document:</span></span>

- [<span data-ttu-id="6ac92-124">XOP</span><span class="sxs-lookup"><span data-stu-id="6ac92-124">XOP</span></span>](https://www.w3.org/TR/xop10/)
- [<span data-ttu-id="6ac92-125">SOAP 1.2 + MTOM enlace</span><span class="sxs-lookup"><span data-stu-id="6ac92-125">MTOM + SOAP 1.2 Binding</span></span>](https://www.w3.org/TR/soap12-mtom/)
- [<span data-ttu-id="6ac92-126">MTOM enlace SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="6ac92-126">MTOM SOAP 1.1 Binding</span></span>](https://www.w3.org/Submission/soap11mtom10/)
- [<span data-ttu-id="6ac92-127">Aserción de directiva WS MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-127">MTOM WS-Policy Assertion</span></span>](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

<span data-ttu-id="6ac92-128">Los siguientes espacios de nombres XML y prefijos asociados se usan a lo largo de este tema:</span><span class="sxs-lookup"><span data-stu-id="6ac92-128">The following XML namespaces and associated prefixes are used throughout this topic:</span></span>

| <span data-ttu-id="6ac92-129">Prefijo</span><span class="sxs-lookup"><span data-stu-id="6ac92-129">Prefix</span></span> | <span data-ttu-id="6ac92-130">Espacio de nombres de identificador uniforme de recursos (URI)</span><span class="sxs-lookup"><span data-stu-id="6ac92-130">Namespace Uniform Resource Identifier (URI)</span></span> |
|------------|---------------------------------------------------|
| <span data-ttu-id="6ac92-131">s11</span><span class="sxs-lookup"><span data-stu-id="6ac92-131">s11</span></span> | `http://schemas.xmlsoap.org/soap/envelope` |
| <span data-ttu-id="6ac92-132">s12</span><span class="sxs-lookup"><span data-stu-id="6ac92-132">s12</span></span> |`http://www.w3.org/2003/05/soap-envelope` |
| <span data-ttu-id="6ac92-133">wsa</span><span class="sxs-lookup"><span data-stu-id="6ac92-133">wsa</span></span> |`http://www.w3.org/2004/08/addressing` |
| <span data-ttu-id="6ac92-134">wsam</span><span class="sxs-lookup"><span data-stu-id="6ac92-134">wsam</span></span> |`http://www.w3.org/2007/05/addressing/metadata` |
| <span data-ttu-id="6ac92-135">wsap</span><span class="sxs-lookup"><span data-stu-id="6ac92-135">wsap</span></span> |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| <span data-ttu-id="6ac92-136">wsa10</span><span class="sxs-lookup"><span data-stu-id="6ac92-136">wsa10</span></span> |`http://www.w3.org/2005/08/addressing` |
| <span data-ttu-id="6ac92-137">wsaw10</span><span class="sxs-lookup"><span data-stu-id="6ac92-137">wsaw10</span></span> |`http://www.w3.org/2006/05/addressing/wsdl` |
| <span data-ttu-id="6ac92-138">xop</span><span class="sxs-lookup"><span data-stu-id="6ac92-138">xop</span></span> |`http://www.w3.org/2004/08/xop/include` |
| <span data-ttu-id="6ac92-139">xmime</span><span class="sxs-lookup"><span data-stu-id="6ac92-139">xmime</span></span> |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| <span data-ttu-id="6ac92-140">dp</span><span class="sxs-lookup"><span data-stu-id="6ac92-140">dp</span></span> |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a><span data-ttu-id="6ac92-141">SOAP 1.1 y SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="6ac92-141">SOAP 1.1 and SOAP 1.2</span></span>

### <a name="envelope-and-processing-model"></a><span data-ttu-id="6ac92-142">Modelo de procesado y envoltura</span><span class="sxs-lookup"><span data-stu-id="6ac92-142">Envelope and Processing Model</span></span>
<span data-ttu-id="6ac92-143">WCF implementa el procesado de envoltura SOAP 1.1 siguiendo perfil básico 1.1 (BP11) y Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="6ac92-143">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="6ac92-144">El procesamiento de envoltura SOAP 1.2 se implementa siguiendo SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="6ac92-144">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>

<span data-ttu-id="6ac92-145">En esta sección se explica ciertas opciones de implementación tomadas por WCF con respecto a BP11 y SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="6ac92-145">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>

#### <a name="mandatory-header-processing"></a><span data-ttu-id="6ac92-146">Procesamiento del encabezado obligatorio</span><span class="sxs-lookup"><span data-stu-id="6ac92-146">Mandatory Header Processing</span></span>
<span data-ttu-id="6ac92-147">WCF sigue las reglas para procesar encabezados marcados `mustUnderstand` descritos en las especificaciones SOAP 1.1 y SOAP 1.2, con las siguientes variaciones.</span><span class="sxs-lookup"><span data-stu-id="6ac92-147">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>

<span data-ttu-id="6ac92-148">Canales individuales configurados por elementos de enlace asociada, por ejemplo, codificación de mensajes de texto, seguridad, mensajería confiable y transacciones procesa un mensaje que entra en la pila de canales WCF.</span><span class="sxs-lookup"><span data-stu-id="6ac92-148">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="6ac92-149">Cada canal reconoce los encabezados del espacio de nombres asociado y los marca como comprendidos.</span><span class="sxs-lookup"><span data-stu-id="6ac92-149">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="6ac92-150">Cuando un mensaje escribe el distribuidor, el formateador de operaciones lee encabezados esperados por el contrato de operación/mensaje correspondiente y los marca como comprendidos.</span><span class="sxs-lookup"><span data-stu-id="6ac92-150">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="6ac92-151">A continuación, el distribuidor comprueba si algún encabezado restante no se entiende pero está marcado como `mustUnderstand` y produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="6ac92-151">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="6ac92-152">Los mensajes que contienen encabezados `mustUnderstand` que tienen como destino el destinatario no son procesados por el código de aplicación de destinatario.</span><span class="sxs-lookup"><span data-stu-id="6ac92-152">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>

<span data-ttu-id="6ac92-153">Tal procesamiento superpuesto permite la separación entre las capas de la infraestructura y las capas de la aplicación del nodo SOAP:</span><span class="sxs-lookup"><span data-stu-id="6ac92-153">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>

- <span data-ttu-id="6ac92-154">B1111: Se detectan encabezados que no se entienden una vez que el mensaje es procesado por la pila de canales de infraestructura WCF, pero antes de procesarse por aplicación</span><span class="sxs-lookup"><span data-stu-id="6ac92-154">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>

     <span data-ttu-id="6ac92-155">El valor de encabezado `mustUnderstand` difiere entre SOAP 1.1 y SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="6ac92-155">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="6ac92-156">Basic Profile 1.1 requiere que el valor `mustUnderstand` sea 0 o 1 para los mensajes SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="6ac92-156">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="6ac92-157">SOAP 1.2 permite 0, 1, `false` y `true` como valores, pero recomienda emitir una representación canónica de valores (`xs:boolean`, `false`) `true`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-157">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>

- <span data-ttu-id="6ac92-158">B1112: Emite WCF `mustUnderstand` valores 0 y 1 para las versiones de SOAP 1.1 y SOAP 1.2 de la envoltura SOAP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-158">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="6ac92-159">WCF acepta el espacio de valor completo de `xs:boolean` para el `mustUnderstand` encabezado (0, 1, `false`, `true`)</span><span class="sxs-lookup"><span data-stu-id="6ac92-159">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>

#### <a name="soap-faults"></a><span data-ttu-id="6ac92-160">Errores SOAP</span><span class="sxs-lookup"><span data-stu-id="6ac92-160">SOAP Faults</span></span>
<span data-ttu-id="6ac92-161">La siguiente es una lista de implementaciones de errores de SOAP de WCF específico.</span><span class="sxs-lookup"><span data-stu-id="6ac92-161">The following is a list of WCF-specific SOAP fault implementations.</span></span>

- <span data-ttu-id="6ac92-162">B2121: WCF devuelve los siguientes códigos de error de SOAP 1.1: `s11:mustUnderstand`, `s11:Client`, y `s11:Server`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-162">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>

- <span data-ttu-id="6ac92-163">B2122: WCF devuelve los siguientes códigos de error de SOAP 1.2: `s12:MustUnderstand`, `s12:Sender`, y `s12:Receiver`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-163">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>

### <a name="http-binding"></a><span data-ttu-id="6ac92-164">Enlace HTTP</span><span class="sxs-lookup"><span data-stu-id="6ac92-164">HTTP Binding</span></span>

#### <a name="soap-11-http-binding"></a><span data-ttu-id="6ac92-165">Enlace HTTP de SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="6ac92-165">SOAP 1.1 HTTP Binding</span></span>
<span data-ttu-id="6ac92-166">WCF implementa enlace HTTP de SOAP1.1 siguiendo la sección 3.4 siguientes aclaraciones de especificación de Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="6ac92-166">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>

- <span data-ttu-id="6ac92-167">B2211: Servicio de WCF no implementa la redirección de solicitudes HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="6ac92-167">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>

- <span data-ttu-id="6ac92-168">B2212: Los clientes de WCF admiten Cookies HTTP de acuerdo con 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="6ac92-168">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>

#### <a name="soap-12-http-binding"></a><span data-ttu-id="6ac92-169">Enlace HTTP de SOAP 1,2</span><span class="sxs-lookup"><span data-stu-id="6ac92-169">SOAP 1.2 HTTP Binding</span></span>
<span data-ttu-id="6ac92-170">WCF implementa enlace HTTP de SOAP 1.2 tal y como se describe en SOAP 1.2-parte 2 (SOAP12Part2) especificación con las siguientes aclaraciones.</span><span class="sxs-lookup"><span data-stu-id="6ac92-170">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>

<span data-ttu-id="6ac92-171">SOAP 1.2 introdujo un parámetro de acción opcional para el tipo de medio `application/soap+xml`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-171">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="6ac92-172">Este parámetro es útil para optimizar la distribución de mensajes sin requerir que se analice el cuerpo del mensaje SOAP cuando no se utiliza WS-Addresing.</span><span class="sxs-lookup"><span data-stu-id="6ac92-172">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>

- <span data-ttu-id="6ac92-173">R2221: El `application/soap+xml` parámetro action, cuando está presente en una solicitud SOAP 1.2, debe coincidir con el `soapAction` atributo el `wsoap12:operation` elemento de enlace WSDL correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6ac92-173">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>

- <span data-ttu-id="6ac92-174">R2222: El `application/soap+xml` parámetro action, cuando está presente en un mensaje SOAP 1.2, debe coincidir con `wsa:Action` cuando se usan WS-Addressing 2004/08 o WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="6ac92-174">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="6ac92-175">Cuando WS-Addressing está deshabilitado y una solicitud entrante no contiene ningún parámetro de acción, `Action` del mensaje se considera como no especificada.</span><span class="sxs-lookup"><span data-stu-id="6ac92-175">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>

## <a name="ws-addressing"></a><span data-ttu-id="6ac92-176">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="6ac92-176">WS-Addressing</span></span>
<span data-ttu-id="6ac92-177">WCF implementa 3 versiones de WS-Addressing:</span><span class="sxs-lookup"><span data-stu-id="6ac92-177">WCF implements 3 versions of WS-Addressing:</span></span>

- <span data-ttu-id="6ac92-178">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="6ac92-178">WS-Addressing 2004/08</span></span>

- <span data-ttu-id="6ac92-179">Núcleo de W3C Web Services Addressing 1.0 (ADDR10-CORE) y enlace SOAP (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="6ac92-179">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>

- <span data-ttu-id="6ac92-180">WS-Addressing 1.0 - Metadatos</span><span class="sxs-lookup"><span data-stu-id="6ac92-180">WS-Addressing 1.0 - Metadata</span></span>

### <a name="endpoint-references"></a><span data-ttu-id="6ac92-181">Referencias de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6ac92-181">Endpoint References</span></span>
<span data-ttu-id="6ac92-182">Todas las versiones de WS-Addressing que implementa WCF usan referencias de punto de conexión para describir los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="6ac92-182">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>

#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="6ac92-183">Referencias de punto de conexión y WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="6ac92-183">Endpoint References and WS-Addressing Versions</span></span>
<span data-ttu-id="6ac92-184">WCF implementa varios protocolos de infraestructura que usan WS-Addressing y en particular el `EndpointReference` elemento y `W3C.WsAddressing.EndpointReferenceType` (clase) (por ejemplo, WS-ReliableMessaging, WS-SecureConversation y WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="6ac92-184">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="6ac92-185">WCF admite el uso de cualquier versión de WS-Addressing con otros protocolos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="6ac92-185">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="6ac92-186">Los extremos de WCF admiten una versión de WS-Addressing por punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6ac92-186">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>

<span data-ttu-id="6ac92-187">Para R3111, el espacio de nombres para el `EndpointReference` elemento o el tipo utilizado en mensajes intercambiados con un extremo de WCF debe coincidir con la versión de WS-Addressing implementado por este extremo.</span><span class="sxs-lookup"><span data-stu-id="6ac92-187">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>

<span data-ttu-id="6ac92-188">Por ejemplo, si un extremo de WCF implementa WS-ReliableMessaging, el `AcksTo` devuelto por este extremo dentro del encabezado `CreateSequenceResponse` usa la versión de WS-Addressing que el `EncodingBinding` elemento especifica para este extremo.</span><span class="sxs-lookup"><span data-stu-id="6ac92-188">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>

#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="6ac92-189">Referencias de punto de conexión y metadatos</span><span class="sxs-lookup"><span data-stu-id="6ac92-189">Endpoint References and Metadata</span></span>
<span data-ttu-id="6ac92-190">Varios escenarios requieren comunicar metadatos o una referencia a los metadatos para un punto de conexión determinado.</span><span class="sxs-lookup"><span data-stu-id="6ac92-190">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>

<span data-ttu-id="6ac92-191">B3121: WCF emplea mecanismos descritos en la sección 6, para incluir metadatos para referencias de punto de conexión por valor o por referencia de la especificación de WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="6ac92-191">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>

<span data-ttu-id="6ac92-192">Considere un escenario donde un servicio WCF requiere la autenticación mediante un token de lenguaje de marcado de aserción de seguridad (SAML) emitido por el emisor del token en `http://sts.fabrikam123.com`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-192">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at `http://sts.fabrikam123.com`.</span></span> <span data-ttu-id="6ac92-193">El punto de conexión WCF describe este requisito de autenticación mediante `sp:IssuedToken` aserción con anidada `sp:Issuer` aserción que señala al emisor del token.</span><span class="sxs-lookup"><span data-stu-id="6ac92-193">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="6ac92-194">Las aplicaciones de cliente que obtienen acceso a la aserción `sp:Issuer` han de saber cómo comunicarse con el punto de conexión del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="6ac92-194">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="6ac92-195">El cliente ha de saber los metadatos sobre el emisor del token.</span><span class="sxs-lookup"><span data-stu-id="6ac92-195">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="6ac92-196">Con las extensiones de metadatos de referencia de punto de conexión definidas en MEX, WCF proporciona una referencia a los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="6ac92-196">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a><span data-ttu-id="6ac92-197">Encabezados de direccionamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="6ac92-197">Message Addressing Headers</span></span>

#### <a name="message-headers"></a><span data-ttu-id="6ac92-198">Encabezados de mensajes</span><span class="sxs-lookup"><span data-stu-id="6ac92-198">Message Headers</span></span>
<span data-ttu-id="6ac92-199">Para ambas versiones de WS-Addressing, WCF usa los siguientes encabezados de mensaje tal y como describen las especificaciones `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, y `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-199">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>

<span data-ttu-id="6ac92-200">B3211: Para todas las versiones de WS-Addressing, WCF respeta, pero no se genera desde el principio, los encabezados de mensaje de WS-Addressing `wsa:FaultTo` y `wsa:From`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-200">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>

<span data-ttu-id="6ac92-201">Las aplicaciones que interactúan con aplicaciones WCF que se pueden agregar que estos encabezados de mensaje y WCF procesará consecuentemente.</span><span class="sxs-lookup"><span data-stu-id="6ac92-201">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>

#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="6ac92-202">Parámetros de referencia y propiedades</span><span class="sxs-lookup"><span data-stu-id="6ac92-202">Reference Parameters and Properties</span></span>

<span data-ttu-id="6ac92-203">WCF implementa el procesamiento de los parámetros de referencia de punto de conexión y propiedades de referencia de acuerdo con las especificaciones respectivas.</span><span class="sxs-lookup"><span data-stu-id="6ac92-203">WCF implements processing of endpoint reference parameters and reference properties in accordance with respective specifications.</span></span>

<span data-ttu-id="6ac92-204">B3221: Cuando se configura para utilizar WS-Addressing 2004/08, los extremos de WCF no diferencian entre procesar propiedades de referencia y los parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="6ac92-204">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>

### <a name="message-exchange-patterns"></a><span data-ttu-id="6ac92-205">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="6ac92-205">Message Exchange Patterns</span></span>
<span data-ttu-id="6ac92-206">La secuencia de mensajes implicada en la invocación de operación de servicio Web se conoce como el *patrón de intercambio de mensajes*.</span><span class="sxs-lookup"><span data-stu-id="6ac92-206">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="6ac92-207">Patrones de intercambio de mensajes dúplex, de solicitud-respuesta y unidireccionales de WCF admite.</span><span class="sxs-lookup"><span data-stu-id="6ac92-207">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="6ac92-208">En esta sección se aclaran los requisitos de WS-Addressing sobre el procesamiento de mensajes en función del patrón de intercambio de mensajes que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="6ac92-208">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>

<span data-ttu-id="6ac92-209">A lo largo de esta sección, el solicitante envía el primer mensaje y el respondedor recibe el primer mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ac92-209">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="6ac92-210">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="6ac92-210">One-Way Message</span></span>
<span data-ttu-id="6ac92-211">Cuando se configura un extremo de WCF para admitir mensajes con un determinado `Action` para seguir un patrón unidireccional, el punto de conexión WCF sigue los siguientes comportamientos y requisitos.</span><span class="sxs-lookup"><span data-stu-id="6ac92-211">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="6ac92-212">A menos que se especifique lo contrario, los comportamientos y reglas se aplican a ambas versiones de WS-Addressing de WCF admitidos:</span><span class="sxs-lookup"><span data-stu-id="6ac92-212">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="6ac92-213">R3311: El solicitante debe incluir `wsa:To`, `wsa:Action`y los encabezados para todos los parámetros de referencia especificados por la referencia del extremo.</span><span class="sxs-lookup"><span data-stu-id="6ac92-213">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="6ac92-214">Cuando se utiliza WS-Addressing 2004/08 y la referencia de punto de conexión especifica las [propiedades de referencia], los encabezados correspondientes también deben agregarse al mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ac92-214">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>

- <span data-ttu-id="6ac92-215">B3312: El solicitante puede incluir `MessageID`, `ReplyTo`, y `FaultTo` encabezados.</span><span class="sxs-lookup"><span data-stu-id="6ac92-215">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="6ac92-216">La infraestructura del receptor los omitirá y se pasarán a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ac92-216">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>

- <span data-ttu-id="6ac92-217">R3313: Cuando se usa HTTP y no se envía ningún mensaje en la bifurcación de la respuesta HTTP, el Respondedor debe enviar una respuesta HTTP con un cuerpo vacío y un código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="6ac92-217">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>

     <span data-ttu-id="6ac92-218">Si el transporte HTTP está en uso y el contrato de operación declara un mensaje unidireccional, la respuesta HTTP todavía se puede utilizar para enviar mensajes de infraestructura, por ejemplo, la mensajería de confianza puede enviar un mensaje `SequenceAcknowledgement` en una respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-218">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>

- <span data-ttu-id="6ac92-219">B3314: El servicio de respuesta WCF no envía un mensaje de error en respuesta a un mensaje unidireccional.</span><span class="sxs-lookup"><span data-stu-id="6ac92-219">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>

#### <a name="request-reply"></a><span data-ttu-id="6ac92-220">Solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="6ac92-220">Request-Reply</span></span>
<span data-ttu-id="6ac92-221">Cuando se configura un extremo de WCF para un mensaje con un determinado `Action` para seguir el patrón de solicitud-respuesta, el punto de conexión WCF sigue los comportamientos y requisitos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6ac92-221">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="6ac92-222">A menos que se especifique lo contrario, los comportamientos y reglas se aplican a ambas versiones de WS-Addressing de WCF admitidos:</span><span class="sxs-lookup"><span data-stu-id="6ac92-222">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="6ac92-223">R3321: El solicitante debe incluir en la solicitud `wsa:To`, `wsa:Action`, `wsa:MessageID`y los encabezados para todos los parámetros de referencia o referencia propiedades (o ambos) especificados por la referencia del extremo.</span><span class="sxs-lookup"><span data-stu-id="6ac92-223">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>

- <span data-ttu-id="6ac92-224">R3322: Cuando se utiliza WS-Addressing 2004/08, `ReplyTo` también debe incluirse en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6ac92-224">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>

- <span data-ttu-id="6ac92-225">R3323: Cuando se utiliza WS-Addressing 1.0 y `ReplyTo` no está presente en la solicitud, una referencia de punto de conexión predeterminada con la propiedad [dirección] igual a `http://www.w3.org/2005/08/addressing/anonymous` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="6ac92-225">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to `http://www.w3.org/2005/08/addressing/anonymous` is used.</span></span>

- <span data-ttu-id="6ac92-226">R3324: El solicitante debe incluir `wsa:To`, `wsa:Action`, y `wsa:RelatesTo` encabezados en el mensaje de respuesta, así como los encabezados para todos los parámetros de referencia o referencia propiedades (o ambos) especificados por el `ReplyTo` referencia del extremo en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6ac92-226">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>

### <a name="web-services-addressing-faults"></a><span data-ttu-id="6ac92-227">Errores de direccionamiento de servicios Web</span><span class="sxs-lookup"><span data-stu-id="6ac92-227">Web Services Addressing Faults</span></span>
<span data-ttu-id="6ac92-228">R3411: WCF genera los siguientes errores definidos por WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="6ac92-228">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>

| <span data-ttu-id="6ac92-229">Código</span><span class="sxs-lookup"><span data-stu-id="6ac92-229">Code</span></span> | <span data-ttu-id="6ac92-230">Motivo</span><span class="sxs-lookup"><span data-stu-id="6ac92-230">Cause</span></span> |
|----------|-----------|
| `wsa:DestinationUnreachable` | <span data-ttu-id="6ac92-231">El mensaje llegó con un `ReplyTo` diferente a la dirección de respuesta establecida para este canal; no hay ningún punto de conexión que escuche en la dirección especificada en el encabezado To.</span><span class="sxs-lookup"><span data-stu-id="6ac92-231">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa:ActionNotSupported` | <span data-ttu-id="6ac92-232">los canales de infraestructura o el distribuidor asociados al punto de conexión no reconocen la acción especificada en el encabezado `Action`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-232">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span> |

<span data-ttu-id="6ac92-233">R3412: WCF genera los siguientes errores definidos por WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="6ac92-233">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>

| <span data-ttu-id="6ac92-234">Código</span><span class="sxs-lookup"><span data-stu-id="6ac92-234">Code</span></span> | <span data-ttu-id="6ac92-235">Motivo</span><span class="sxs-lookup"><span data-stu-id="6ac92-235">Cause</span></span> |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | <span data-ttu-id="6ac92-236">Duplicar `wsa:To`, `wsa:ReplyTo`, `wsa:From` o `wsa:MessageID`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-236">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="6ac92-237">Duplicar `wsa:RelatesTo` con el mismo `RelationshipType`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-237">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span> |
| `wsa10:MessageAddressingHeaderRequired` | <span data-ttu-id="6ac92-238">Falta el encabezado Addressing necesario.</span><span class="sxs-lookup"><span data-stu-id="6ac92-238">The required Addressing header is missing.</span></span> |
| `wsa10:DestinationUnreachable` | <span data-ttu-id="6ac92-239">El mensaje llegó con un `ReplyTo` diferente a la dirección de respuesta establecida para este canal.</span><span class="sxs-lookup"><span data-stu-id="6ac92-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="6ac92-240">No hay ningún punto de conexión escuchando en la dirección especificada en encabezado To.</span><span class="sxs-lookup"><span data-stu-id="6ac92-240">There is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa10:ActionNotSupported` | <span data-ttu-id="6ac92-241">Los canales de infraestructura o el distribuidor asociados al punto de conexión no reconocen una acción especificada en el encabezado `Action`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-241">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span> |
| `wsa10:EndpointUnavailable` | <span data-ttu-id="6ac92-242">El canal RM devuelve este error, indicando que el extremo no procesará la secuencia basada en el examen de los encabezados de direccionamiento del mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-242">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span> |

<span data-ttu-id="6ac92-243">El código de las tablas anteriores se asigna a `FaultCode` en SOAP 1.1 y `SubCode` (con Code=Sender) en SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="6ac92-243">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="6ac92-244">Enlace WSDL 1.1 y aserciones de WS-Policy</span><span class="sxs-lookup"><span data-stu-id="6ac92-244">WSDL 1.1 Binding and WS-Policy Assertions</span></span>

#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="6ac92-245">Indicación del uso de WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="6ac92-245">Indicating Use of WS-Addressing</span></span>
<span data-ttu-id="6ac92-246">WCF utiliza las aserciones de directiva para indicar la compatibilidad de punto de conexión para una determinada versión de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="6ac92-246">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>

<span data-ttu-id="6ac92-247">La siguiente aserción de directiva tiene Asunto de directiva de extremo [WS PA] e indica que los mensajes enviados y recibidos desde el extremo deben utilizar WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="6ac92-247">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsap:UsingAddressing />
```

<span data-ttu-id="6ac92-248">Esta aserción de directiva aumenta la especificación WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="6ac92-248">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>

<span data-ttu-id="6ac92-249">La siguiente aserción de directiva indica que los mensajes enviados y recibidos deben usar WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="6ac92-249">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>

```xml
<wsam:Addressing/>
```

<span data-ttu-id="6ac92-250">La siguiente aserción de directiva tiene un asunto de directiva de punto de conexión [WS PA] e indica que los mensajes enviados y recibidos desde el punto de conexión deben utilizar WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="6ac92-250">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsaw10:UsingAddressing />
```

<span data-ttu-id="6ac92-251">El elemento `wsaw10:UsingAddressing` se toma prestado de [WSDL de WS-Addressing] y se utiliza en el contexto de WS-Addressing cumpliendo con esa especificación, sección 3.1.2.</span><span class="sxs-lookup"><span data-stu-id="6ac92-251">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>

<span data-ttu-id="6ac92-252">El uso de direccionamiento no modifica la semántica de WSDL 1.1, SOAP 1.1 y enlaces HTTP SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="6ac92-252">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="6ac92-253">Por ejemplo, si una respuesta se espera para una solicitud que se envía a un punto de conexión que usa direccionamiento y enlace HTTP de SOAP 1.x de WSDL, la respuesta se debe enviar utilizando la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-253">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>

<span data-ttu-id="6ac92-254">Para las respuestas enviadas a través de la respuesta http, la aserción de WS-AM es:</span><span class="sxs-lookup"><span data-stu-id="6ac92-254">For replies sent over the http response, the WS-AM assertion is:</span></span>

```xml
<wsam:AnonymousResponses/>
```

<span data-ttu-id="6ac92-255">La apariencia de la aserción de directiva completa debe ser como esta:</span><span class="sxs-lookup"><span data-stu-id="6ac92-255">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="6ac92-256">Sin embargo, hay patrones de intercambio de mensajes que se benefician de tener dos conexiones HTTP inversas independientes establecidas entre el solicitante y el respondedor, por ejemplo, los mensajes unidireccionales no solicitados enviados por el respondedor.</span><span class="sxs-lookup"><span data-stu-id="6ac92-256">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>

<span data-ttu-id="6ac92-257">WCF ofrece una característica por la que dos canales de transporte subyacentes pueden formar un canal dúplex compuesto, donde un canal se usa para mensajes de entrada y la otra se usa para los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="6ac92-257">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="6ac92-258">En el caso del transporte HTTP, el Dúplex Compuesto proporciona dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="6ac92-258">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="6ac92-259">El solicitante utiliza una conexión para enviar mensajes al respondedor y el respondedor usa la otra para devolver mensajes al solicitante.</span><span class="sxs-lookup"><span data-stu-id="6ac92-259">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>

<span data-ttu-id="6ac92-260">Para las respuestas enviadas a través de solicitudes independientes http, la aserción de ws-am es:</span><span class="sxs-lookup"><span data-stu-id="6ac92-260">For replies sent over separate http requests, the ws-am assertion is</span></span>

```xml
<wsam:NonAnonymousResponses/>
```

<span data-ttu-id="6ac92-261">La apariencia de la aserción de directiva completa debe ser como esta:</span><span class="sxs-lookup"><span data-stu-id="6ac92-261">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="6ac92-262">El uso de la siguiente aserción que tiene un asunto de extremo de directiva [WS-PA] en los extremos que usan enlaces HTTP de SOAP 1.1x de WDSL 1.1 requiere dos conexiones HTTP inversas independientes que se utilizarán para los mensajes que fluyen del solicitante al respondedor y del respondedor al solicitante, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6ac92-262">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>

```xml
<cdp:CompositeDuplex/>
```

<span data-ttu-id="6ac92-263">La declaración anterior conduce a los siguientes requisitos en el encabezado `wsa:ReplyTo` para los mensajes de solicitud:</span><span class="sxs-lookup"><span data-stu-id="6ac92-263">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>

- <span data-ttu-id="6ac92-264">R3514: Solicitar a los mensajes enviados a un punto de conexión deben tener un `ReplyTo` encabezado con el `[address]` propiedad no es igual a `http://www.w3.org/2005/08/addressing/anonymous` si el punto de conexión utiliza un enlace de WSDL 1.1 SOAP 1.x HTTP y tiene una directiva alternativa con un `wsap10:UsingAddressing` o `wsap:UsingAddressing` aserción junto con `cdp:CompositeDuplex` adjunta.</span><span class="sxs-lookup"><span data-stu-id="6ac92-264">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>

- <span data-ttu-id="6ac92-265">R3515: Solicitar a los mensajes enviados a un punto de conexión deben tener un `ReplyTo` encabezado con el `[address]` propiedad igual a `http://www.w3.org/2005/08/addressing/anonymous`, o no tiene un `ReplyTo` encabezado en absoluto, si el punto de conexión utiliza un enlace de WSDL 1.1 SOAP 1.x HTTP y tiene una directiva alternativa con `wsap10:UsingAddressing` aserción y no `cdp:CompositeDuplex` aserción adjuntada.</span><span class="sxs-lookup"><span data-stu-id="6ac92-265">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous`, or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

- <span data-ttu-id="6ac92-266">R3516: Solicitar a los mensajes enviados a un punto de conexión deben tener un `ReplyTo` encabezado con un `[address]` propiedad igual a `http://www.w3.org/2005/08/addressing/anonymous` si el punto de conexión utiliza un enlace de WSDL 1.1 SOAP 1.x HTTP y tiene una directiva alternativa con `wsap:UsingAddressing` aserción y no `cdp:CompositeDuplex` aserción adjuntada.</span><span class="sxs-lookup"><span data-stu-id="6ac92-266">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

<span data-ttu-id="6ac92-267">La especificación WSDL de WS-Addressing intenta describir enlaces de protocolos similares introduciendo un elemento `<wsaw:Anonymous/>` con tres valores textuales (requerido, opcional y prohibido) para indicar requisitos en el encabezado `wsa:ReplyTo` (sección 3.2).</span><span class="sxs-lookup"><span data-stu-id="6ac92-267">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="6ac92-268">Desafortunadamente, tal definición de elemento no es especialmente utilizable como aserción en el contexto de WS-Policy, porque requiere extensiones específicas del dominio para admitir la intersección de alternativas usando este tipo de elementos como aserción.</span><span class="sxs-lookup"><span data-stu-id="6ac92-268">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="6ac92-269">Tal definición de elemento también indica el valor del encabezado `ReplyTo` frente al comportamiento del extremo en la conexión, que lo hace específico para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-269">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>

#### <a name="action-definition"></a><span data-ttu-id="6ac92-270">Definición de acción</span><span class="sxs-lookup"><span data-stu-id="6ac92-270">Action Definition</span></span>
<span data-ttu-id="6ac92-271">WS-Addressing 2004/08 define un atributo `wsa:Action` para los elementos`wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-271">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="6ac92-272">El enlace ESDL de WS-Addressing 1.0 (WS-ADDR10-WSDL) define un atributo similar, `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-272">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>

<span data-ttu-id="6ac92-273">La única diferencia entre los dos es la semántica de patrón de Acción predeterminada descrita en la sección 3.3.2 de WS-ADDR y la sección 4.4.4 de WS-ADDR10-WSDL, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6ac92-273">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>

<span data-ttu-id="6ac92-274">Es razonable tener dos extremos que comparten el mismo `portType` (o contrato, en la terminología de WCF), pero con diferentes versiones de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="6ac92-274">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="6ac92-275">Pero suponiendo que esa acción esté definida por `portType` y no debería cambiar a lo largo de los extremos que implementan `portType`, se hace imposible admitir ambos patrones de acción predeterminados.</span><span class="sxs-lookup"><span data-stu-id="6ac92-275">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>

<span data-ttu-id="6ac92-276">Para resolver esta controversia, WCF admite una única versión de la `Action` atributo.</span><span class="sxs-lookup"><span data-stu-id="6ac92-276">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>

<span data-ttu-id="6ac92-277">B3521: WCF usa la `wsaw10:Action` atributo `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elementos tal como se define en WS-ADDR10-WSDL para determinar el `Action` URI para los mensajes correspondientes independientemente de la versión de WS-Addressing utilizada por el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6ac92-277">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>

#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="6ac92-278">Uso de la referencia de extremo dentro del puerto WSDL</span><span class="sxs-lookup"><span data-stu-id="6ac92-278">Use Endpoint Reference Inside WSDL Port</span></span>
<span data-ttu-id="6ac92-279">La sección 4.1 de WS-ADDR10-WSDL extiende el elemento `wsdl:port` para incluir el elemento secundario `<wsa10:EndpointReference…/>` para describir el punto de conexión en términos de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="6ac92-279">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="6ac92-280">WCF expande esta utilidad en WS-Addressing 2004/08, permitiendo `<wsa:EndpointReference…/>` aparezca como un elemento secundario de `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-280">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>

- <span data-ttu-id="6ac92-281">R3531: Si un punto de conexión tiene una directiva alternativa adjunta con una `<wsaw10:UsingAddressing/>` aserción de directiva, la correspondiente `wsdl:port` elemento puede contener un elemento secundario `<wsa10:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-281">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>

- <span data-ttu-id="6ac92-282">R3532: Si un `wsdl:port` contiene un elemento secundario `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` valor del elemento secundario debe coincidir con el valor de la `@address` atributo del nodo relacionado `wsdl:port` / `wsdl:location` elemento.</span><span class="sxs-lookup"><span data-stu-id="6ac92-282">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

- <span data-ttu-id="6ac92-283">R3533: Si un punto de conexión tiene una directiva alternativa adjunta con `<wsap:UsingAddressing/>` aserción de directiva, la correspondiente `wsdl:port` elemento puede contener un elemento secundario `<wsa:EndpointReference …/>`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-283">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>

- <span data-ttu-id="6ac92-284">R3534: Si un `wsdl:port` contiene un elemento secundario `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` valor del elemento secundario debe coincidir con el valor de la `@address` atributo del nodo relacionado `wsdl:port` / `wsdl:location` elemento.</span><span class="sxs-lookup"><span data-stu-id="6ac92-284">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="6ac92-285">Composición con WS-Security</span><span class="sxs-lookup"><span data-stu-id="6ac92-285">Composition with WS-Security</span></span>
<span data-ttu-id="6ac92-286">Según las secciones de consideración de seguridad en WS-ADDR y WS-ADDR10, se recomienda que todos los encabezados de mensajes de direccionamiento se firmen junto con el cuerpo del mensaje para enlazarlos juntos.</span><span class="sxs-lookup"><span data-stu-id="6ac92-286">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>

<span data-ttu-id="6ac92-287">Cuando WS-Security se utiliza para la protección de la integridad de mensajes, los encabezados de mensajes WS-Addressing, así como los encabezados resultantes de parámetros o propiedades de referencia (o ambos) se deben firmar junto con el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ac92-287">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>

### <a name="examples"></a><span data-ttu-id="6ac92-288">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6ac92-288">Examples</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="6ac92-289">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="6ac92-289">One-Way Message</span></span>
<span data-ttu-id="6ac92-290">En este escenario, el remitente envía un mensaje unidireccional al receptor.</span><span class="sxs-lookup"><span data-stu-id="6ac92-290">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="6ac92-291">Se usan SOAP 1.2, HTTP 1.1 y WS-Addressing de W3C 1.0.</span><span class="sxs-lookup"><span data-stu-id="6ac92-291">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="6ac92-292">La estructura del mensaje de solicitud: Incluyen los encabezados del mensaje `wsa10:To` y `wsa10:Action` elementos.</span><span class="sxs-lookup"><span data-stu-id="6ac92-292">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="6ac92-293">El cuerpo del mensaje incluye un elemento `<app:Ping>` concreto del espacio de nombres de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ac92-293">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>

<span data-ttu-id="6ac92-294">Encabezados HTTP: El destino en POST coincide con el URI en el `wsa10:To` elemento.</span><span class="sxs-lookup"><span data-stu-id="6ac92-294">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>

<span data-ttu-id="6ac92-295">El encabezado Content-Type tiene el valor de `application/soap+xml` que requiere SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="6ac92-295">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="6ac92-296">Se incluyen los parámetros `charset` y `action`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-296">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="6ac92-297">El parámetro `action` del encabezado Content-Type coincide con el valor del encabezado `wsa10:Action` del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6ac92-297">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>

```
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay 
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

<span data-ttu-id="6ac92-298">El receptor responde con una respuesta HTTP vacía y el estado 202.</span><span class="sxs-lookup"><span data-stu-id="6ac92-298">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="6ac92-299">Un ejemplo de la respuesta HTTP:</span><span class="sxs-lookup"><span data-stu-id="6ac92-299">An example of the HTTP response:</span></span>

```
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="6ac92-300">Mecanismo de optimización de transmisión de mensajes SOAP</span><span class="sxs-lookup"><span data-stu-id="6ac92-300">SOAP Message Transmission Optimization Mechanism</span></span>
<span data-ttu-id="6ac92-301">Esta sección describen los detalles de implementación de WCF para MTOM de SOAP de HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-301">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="6ac92-302">Tecnología de MTOM es el mecanismo de codificación de mensaje SOAP de la misma clase que la codificación de XML/texto tradicional o codificación binaria en WCF.</span><span class="sxs-lookup"><span data-stu-id="6ac92-302">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="6ac92-303">MTOM incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ac92-303">MTOM includes the following:</span></span>

- <span data-ttu-id="6ac92-304">Una codificación de XML y un mecanismo de empaquetado descritos por [XOP] que optimiza elementos de información XML que contienen datos binarios codificados por base64 en partes binarias independientes.</span><span class="sxs-lookup"><span data-stu-id="6ac92-304">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>

- <span data-ttu-id="6ac92-305">Una encapsulación MIME del paquete de XOP que serializa el conjunto de información XML y cada parte binaria del paquete de XOP en una parte MIME independiente.</span><span class="sxs-lookup"><span data-stu-id="6ac92-305">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>

- <span data-ttu-id="6ac92-306">Una codificación XOP MIME aplicada a la envoltura de SOAP 1.x.</span><span class="sxs-lookup"><span data-stu-id="6ac92-306">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="6ac92-307">Un enlace de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-307">An HTTP transport binding.</span></span>

<span data-ttu-id="6ac92-308">Es posible utilizar MTOM con transportes no HTTP con WCF.</span><span class="sxs-lookup"><span data-stu-id="6ac92-308">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="6ac92-309">Sin embargo, en este tema nos centraremos en HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-309">However, in this topic we will focus on HTTP.</span></span>

<span data-ttu-id="6ac92-310">El formato MTOM reutiliza un largo conjunto de especificaciones que cubren el propio MTOM, XOP y MIME.</span><span class="sxs-lookup"><span data-stu-id="6ac92-310">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="6ac92-311">La modularidad de este conjunto de especificaciones hace algo difícil reconstruir requisitos exactos en la semántica de procesamiento y formato.</span><span class="sxs-lookup"><span data-stu-id="6ac92-311">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="6ac92-312">En esta sección se describe los requisitos de procesamiento y formato para enlace MTOM.</span><span class="sxs-lookup"><span data-stu-id="6ac92-312">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>

### <a name="mtom-message-encoding"></a><span data-ttu-id="6ac92-313">Codificación de mensajes MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-313">MTOM Message Encoding</span></span>

#### <a name="generating-mtom-messages"></a><span data-ttu-id="6ac92-314">Generación de mensajes MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-314">Generating MTOM messages</span></span>
<span data-ttu-id="6ac92-315">La sección 3.1 de [XOP] describe el proceso de codificación de XML con elementos de información de elementos que contienen los valores de base64 en un paquete XOP definido de manera abstracta.</span><span class="sxs-lookup"><span data-stu-id="6ac92-315">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>

<span data-ttu-id="6ac92-316">La siguiente secuencia de pasos describe el proceso de codificación específico del MTOM:</span><span class="sxs-lookup"><span data-stu-id="6ac92-316">The following sequence of steps describes the MTOM-specific encoding process:</span></span>

1. <span data-ttu-id="6ac92-317">Asegúrese de que la envoltura de SOAP que se desea codificar no contiene ninguna información de elemento con un `[namespace name]` de `http://www.w3.org/2004/08/xop/include` y un `[local name]` de `Include`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-317">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of `http://www.w3.org/2004/08/xop/include` and a `[local name]` of `Include`.</span></span>

2. <span data-ttu-id="6ac92-318">Cree un paquete MIME vacío.</span><span class="sxs-lookup"><span data-stu-id="6ac92-318">Create an empty MIME package.</span></span>

3. <span data-ttu-id="6ac92-319">Identifique los elementos de información que se van a optimizar dentro del conjunto de información XML original.</span><span class="sxs-lookup"><span data-stu-id="6ac92-319">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="6ac92-320">Para que los elementos que se optimizarán, los caracteres que constituyen el `[children]` de la información del elemento elemento debe estar en la forma canónica de `xs:base64Binary` (Véase XSD-2, 3.2.16 base64Binary) y no puede contener cualquier carácter de espacio en blanco anterior, en línea, o siguen al contenido que no sea un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="6ac92-320">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>

4. <span data-ttu-id="6ac92-321">Cree una envoltura SOAP de XOP que sea una copia de la envoltura SOAP original, pero con los elementos secundarios de cada elemento de información de elemento identificados en el paso anterior reemplazados por un elemento de información de elemento `xop:Include` construido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6ac92-321">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>

    1. <span data-ttu-id="6ac92-322">Transforme los caracteres reemplazados en datos binarios procesándolos como datos codificados en base64.</span><span class="sxs-lookup"><span data-stu-id="6ac92-322">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>

    2. <span data-ttu-id="6ac92-323">Genere un valor del encabezado Content-ID único que cumpla los requisitos R3133 y R3134.</span><span class="sxs-lookup"><span data-stu-id="6ac92-323">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>

    3. <span data-ttu-id="6ac92-324">Genere un encabezado MIME de codificación de transferencia del contenido con el valor binario.</span><span class="sxs-lookup"><span data-stu-id="6ac92-324">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>

    4. <span data-ttu-id="6ac92-325">Si el elemento de información de elemento que se optimiza (el [primario] del elemento de información de elemento recientemente insertado `xop:Include`) tiene un elemento de información de atributos `xmime:contentType`, genere un encabezado MIME de tipo de contenido con el valor del atributo `xmime:contentType`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-325">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>

    5. <span data-ttu-id="6ac92-326">Genere una nueva parte MIME binaria con contenido formado por datos binarios descodificados a partir de los caracteres reemplazados procesados como base64, encabezado del Content-ID de 4b, encabezado de codificación de transferencia de contenido de 4c, encabezado de tipo de contenido si se generó en el paso 4d.</span><span class="sxs-lookup"><span data-stu-id="6ac92-326">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>

    6. <span data-ttu-id="6ac92-327">Agregue un atributo `href` al elemento `xop:Include` con el valor cid: uri derivado del valor del encabezado Content-ID generado en el paso 4b.</span><span class="sxs-lookup"><span data-stu-id="6ac92-327">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="6ac92-328">Quitar el cierre "\<" y ">" caracteres, la cadena restante y agregue el prefijo de dirección URL de escape `cid:`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-328">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="6ac92-329">El juego de caracteres mínimo siguiente se exige para que RFC1738 y RFC2396 puedan escapar.</span><span class="sxs-lookup"><span data-stu-id="6ac92-329">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="6ac92-330">Se pueden escapar otros caracteres.</span><span class="sxs-lookup"><span data-stu-id="6ac92-330">Other characters can be escaped.</span></span>

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. <span data-ttu-id="6ac92-331">Cree una parte MIME de raíz con la envoltura SOAP de XOP a partir del paso 4.</span><span class="sxs-lookup"><span data-stu-id="6ac92-331">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>

6. <span data-ttu-id="6ac92-332">Escriba los encabezados HTTP, incluido de tipo de contenido HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-332">Write the HTTP headers, including the HTTP Content-Type header.</span></span>

7. <span data-ttu-id="6ac92-333">Escriba el paquete MIME.</span><span class="sxs-lookup"><span data-stu-id="6ac92-333">Write the MIME package.</span></span>

#### <a name="processing-mtom-messages"></a><span data-ttu-id="6ac92-334">Procesamiento de mensajes MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-334">Processing MTOM messages</span></span>
<span data-ttu-id="6ac92-335">Procesar un mensaje MTOM es justo lo contrario al proceso descrito en la sección “Generación de mensajes MTOM":</span><span class="sxs-lookup"><span data-stu-id="6ac92-335">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>

1. <span data-ttu-id="6ac92-336">Asegúrese de que la parte MIME de la raíz tiene el tipo de contenido `application/xop+xml`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-336">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>

2. <span data-ttu-id="6ac92-337">Construya una envoltura SOAP analizando la parte MIME de la raíz del paquete como un documento XML.</span><span class="sxs-lookup"><span data-stu-id="6ac92-337">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="6ac92-338">El parámetro `charset` del tipo de contenido de la parte MIME de la raíz determina la codificación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6ac92-338">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>

3. <span data-ttu-id="6ac92-339">Para cada elemento de información de elemento en la envoltura SOAP construida, que tiene, como único miembro de su propiedad [elemento secundario], un elemento de información de elemento `xop:Include`:</span><span class="sxs-lookup"><span data-stu-id="6ac92-339">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>

    1. <span data-ttu-id="6ac92-340">Elimine el prefijo `cid:` y quite los caracteres de escape de todas las secuencias de escape de URI (RFC 2396) en el valor del atributo `@href` del elemento `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-340">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="6ac92-341">Incluya la cadena de resultado de "\<", ">".</span><span class="sxs-lookup"><span data-stu-id="6ac92-341">Enclose the result string in "\<", ">".</span></span>

    2. <span data-ttu-id="6ac92-342">Busque la parte MIME con el valor del encabezado de identificador de contenido que coincida con la cadena derivada en el paso 3a.</span><span class="sxs-lookup"><span data-stu-id="6ac92-342">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>

    3. <span data-ttu-id="6ac92-343">Reemplace el elemento de información de elemento `xop:Include` que aparece en la propiedad `children` de cada elemento con los elementos de información de caracteres que representan la codificación de base64 canónica (vea XSD-2, 3.2.16 base64Binary) del cuerpo de la entidad de la parte MIME identificada en el paso 3b (reemplace de manera eficaz el elemento de información de elemento `xop:Include` con los datos reconstruidos a partir de la parte del paquete).</span><span class="sxs-lookup"><span data-stu-id="6ac92-343">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>

#### <a name="http-content-type-header"></a><span data-ttu-id="6ac92-344">Encabezado de tipo de contenido HTTP</span><span class="sxs-lookup"><span data-stu-id="6ac92-344">HTTP Content-Type Header</span></span>
<span data-ttu-id="6ac92-345">La siguiente es una lista de aclaraciones de WCF para el formato del encabezado HTTP Content-Type de un mensaje SOAP 1.x codificados por MTOM derivado de los requisitos establecidos en la propia especificación MTOM y se deriva de MTOM y RFC 2387.</span><span class="sxs-lookup"><span data-stu-id="6ac92-345">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>

- <span data-ttu-id="6ac92-346">R4131: El valor de multiparte/relacionado (mayúsculas y minúsculas) y sus parámetros, debe tener un encabezado HTTP Content-Type.</span><span class="sxs-lookup"><span data-stu-id="6ac92-346">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="6ac92-347">Los nombres de parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ac92-347">Parameter names are case-insensitive.</span></span> <span data-ttu-id="6ac92-348">El orden de los parámetros no importa.</span><span class="sxs-lookup"><span data-stu-id="6ac92-348">Parameter order is not significant.</span></span>

- <span data-ttu-id="6ac92-349">Se enumera la forma de Backus-Naur completa (BNF) del encabezado de tipo de contenido para los mensajes MIME en RFC 2045, sección 5.1.</span><span class="sxs-lookup"><span data-stu-id="6ac92-349">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>

- <span data-ttu-id="6ac92-350">R4132: Un encabezado HTTP Content-Type debe tener un parámetro de tipo con el valor `application/xop+xml` entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="6ac92-350">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>

<span data-ttu-id="6ac92-351">Aunque el requisito para usar comillas dobles no es explícito en RFC 2387, el texto observa que todos los parámetros de tipo de medio de multiparte/relacionado probablemente contienen caracteres reservados como "\@" o "/" y, por tanto, necesitan comillas dobles marcas.</span><span class="sxs-lookup"><span data-stu-id="6ac92-351">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>

- <span data-ttu-id="6ac92-352">R4133: Un encabezado HTTP Content-Type debe tener un parámetro de inicio con el valor del encabezado Content-ID de la parte MIME que contiene el mensaje SOAP 1.x sobres, entrecomillada comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="6ac92-352">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="6ac92-353">Si se omite el parámetro de inicio, la primera parte MIME debe contener la envoltura de SOAP 1.x.</span><span class="sxs-lookup"><span data-stu-id="6ac92-353">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="6ac92-354">R4134: Un encabezado HTTP Content-Type para un mensaje codificado de MTOM de SOAP 1.1 debe incluir el parámetro de información de inicio con el valor de texto/xml, encerrado entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="6ac92-354">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="6ac92-355">R4135: Un encabezado HTTP Content-Type para un mensaje codificado en MTOM de SOAP 1.2 debe incluir el parámetro de información de inicio con el valor de `application/soap+xml`, encerrado entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="6ac92-355">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="6ac92-356">R4136: Encabezado HTTP Content-Type para un mensaje codificado en MTOM de SOAP 1.x debe tener el parámetro de límite con el valor (entre comillas dobles) que coincide con el límite MIME que BNF definido en RFC 2046, sección 5.1.1</span><span class="sxs-lookup"><span data-stu-id="6ac92-356">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>

    ```
    boundary := 0*69<bchars> bcharsnospace 
    bchars := bcharsnospace / " " 
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+" 
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     <span data-ttu-id="6ac92-357">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="6ac92-357">Examples:</span></span>

     <span data-ttu-id="6ac92-358">CORRECTO</span><span class="sxs-lookup"><span data-stu-id="6ac92-358">CORRECT</span></span>

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     <span data-ttu-id="6ac92-359">CORRECTO</span><span class="sxs-lookup"><span data-stu-id="6ac92-359">CORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     <span data-ttu-id="6ac92-360">INCORRECTO</span><span class="sxs-lookup"><span data-stu-id="6ac92-360">INCORRECT</span></span>

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1" 
    ```

#### <a name="infoset-mime-part"></a><span data-ttu-id="6ac92-361">Parte del conjunto de información de MIME</span><span class="sxs-lookup"><span data-stu-id="6ac92-361">Infoset MIME Part</span></span>
<span data-ttu-id="6ac92-362">La envoltura de SOAP 1.x se encapsula como una parte de la raíz del paquete de MIME XOP y se llama a menudo la parte `infoset`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-362">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>

- <span data-ttu-id="6ac92-363">R4141: SOAP 1.x sobres se deben encapsular como una parte de la raíz del paquete de XOP MIME, denominado el `infoset` parte y que se hace referencia desde el tipo de contenido HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ac92-363">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>

- <span data-ttu-id="6ac92-364">R4142: SOAP `Infoset` parte debe incluir los encabezados MIME siguientes: `Content-ID`, `Content-Transfer-Encoding`, y `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-364">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>

<span data-ttu-id="6ac92-365">RFC 2045 define el formato del encabezado del id. de contenido como</span><span class="sxs-lookup"><span data-stu-id="6ac92-365">The format of the Content-ID header is defined by RFC 2045 as</span></span>

```
"Content-ID" ":" msg-id
```

<span data-ttu-id="6ac92-366">donde `msg-id` está definido en RFC 2822 (que reemplaza a RFC 822, al que se hace referencia en RFC 2045) como:</span><span class="sxs-lookup"><span data-stu-id="6ac92-366">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

<span data-ttu-id="6ac92-367">y es efectivamente una dirección de correo electrónico encerrada entre "\<" y ">".</span><span class="sxs-lookup"><span data-stu-id="6ac92-367">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="6ac92-368">El prefijo y sufijo `[CFWS]` se agregaron en RFC 2822 para incluir comentarios y no deben usarse para conservar la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="6ac92-368">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>

<span data-ttu-id="6ac92-369">R4143: El valor del encabezado Content-ID de la parte MIME del conjunto de información debe seguir `msg-id` producción de RFC 2822 con el `[CFWS]` partes de prefijo y sufijo se omite.</span><span class="sxs-lookup"><span data-stu-id="6ac92-369">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>

<span data-ttu-id="6ac92-370">Varias implementaciones MIME redujeron los requisitos para el valor encerrado entre "\<" y ">" para ser una dirección de correo electrónico y usar `absoluteURI` entre "\<", ">" Además de la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6ac92-370">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="6ac92-371">Esta versión de WCF usa los valores del encabezado MIME Content-ID del formulario:</span><span class="sxs-lookup"><span data-stu-id="6ac92-371">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>

```
Content-ID: <http://tempuri.org/0> 
```

<span data-ttu-id="6ac92-372">R4144: Procesadores MTOM deberían aceptar más flexible de los siguientes valores que coincidan con los valores de encabezado Content-ID `msg-id`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-372">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

<span data-ttu-id="6ac92-373">MIME (RFC 2045) proporciona el encabezado de codificación de transferencia de contenido para comunicar la codificación del contenido de la parte MIME.</span><span class="sxs-lookup"><span data-stu-id="6ac92-373">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="6ac92-374">El valor predeterminado definido para la codificación de transferencia de contenido es 7 bits, que no es apto para la mayoría de mensajes SOAP, por lo que el encabezado de codificación de transferencia de contenido se necesita para una mayor interoperabilidad:</span><span class="sxs-lookup"><span data-stu-id="6ac92-374">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>

- <span data-ttu-id="6ac92-375">R4145: La parte del conjunto de información de SOAP debe contener el encabezado Content-Transfer-Encoding.</span><span class="sxs-lookup"><span data-stu-id="6ac92-375">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>

- <span data-ttu-id="6ac92-376">R4146: Si la codificación de caracteres de la envoltura SOAP es UTF-8, el valor del encabezado Content-Transfer-Encoding debe ser de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="6ac92-376">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>

- <span data-ttu-id="6ac92-377">R4147: Si la codificación de caracteres de la envoltura SOAP es UTF-16, el valor del encabezado Content-Transfer-Encoding debe ser binario.</span><span class="sxs-lookup"><span data-stu-id="6ac92-377">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>

- <span data-ttu-id="6ac92-378">Según la sección 5 de [XOP],</span><span class="sxs-lookup"><span data-stu-id="6ac92-378">According to [XOP] section 5,</span></span>

- <span data-ttu-id="6ac92-379">R4148: Parte del conjunto de información de SOAP 1.1 debe contener el encabezado Content-Type con el tipo de medio aplicación/xop + xml y los parámetros type = "text/xml" y juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ac92-379">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- <span data-ttu-id="6ac92-380">R4149: La parte del conjunto de información de SOAP 1.2 debe contener el encabezado Content-Type con el tipo de medio `application/xop+xml` y los parámetros type = "`application/soap+xml`" y `charset`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-380">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     <span data-ttu-id="6ac92-381">Aunque XOP defina el parámetro `charset` para `application/xop+xml` como opcional, se necesita para una interoperabilidad similar a la del requisito BP 1.1 del parámetro `charset` para el tipo de medio `text/xml`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-381">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>

- <span data-ttu-id="6ac92-382">R41410: El `type` y `charset` parámetros deben estar presentes en el encabezado Content-Type del elemento de conjunto de información SOAP 1.x.</span><span class="sxs-lookup"><span data-stu-id="6ac92-382">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>

#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="6ac92-383">Compatibilidad de punto de conexión WCF para MTOM.</span><span class="sxs-lookup"><span data-stu-id="6ac92-383">WCF Endpoint Support for MTOM</span></span>
<span data-ttu-id="6ac92-384">El propósito de MTOM es codificar un mensaje SOAP para optimizar los datos codificados en base64.</span><span class="sxs-lookup"><span data-stu-id="6ac92-384">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="6ac92-385">A continuación se muestra una lista de restricciones:</span><span class="sxs-lookup"><span data-stu-id="6ac92-385">The following is a list of constraints:</span></span>

- <span data-ttu-id="6ac92-386">R4151: Se puede optimizar cualquier información de elemento que contiene datos codificados en base64.</span><span class="sxs-lookup"><span data-stu-id="6ac92-386">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>

- <span data-ttu-id="6ac92-387">B4152: WCF optimiza elementos de información que contienen datos codificados en base64 y superan los 1.024 bytes de longitud.</span><span class="sxs-lookup"><span data-stu-id="6ac92-387">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>

<span data-ttu-id="6ac92-388">Un extremo de WCF configurado para utilizar MTOM siempre enviará los mensajes codificados por MTOM.</span><span class="sxs-lookup"><span data-stu-id="6ac92-388">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="6ac92-389">Incluso cuando ninguna parte cumpla los criterios necesarios, el mensaje seguirá estando codificado por MTOM (serializado como un paquete MIME con una parte MIME única que contiene la envoltura SOAP).</span><span class="sxs-lookup"><span data-stu-id="6ac92-389">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>

### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="6ac92-390">Aserción de la WS-Policy para MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-390">WS-Policy Assertion for MTOM</span></span>
<span data-ttu-id="6ac92-391">WCF usa la siguiente aserción de directiva para indicar el uso de MTOM por extremo:</span><span class="sxs-lookup"><span data-stu-id="6ac92-391">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- <span data-ttu-id="6ac92-392">R4211: La aserción de directiva anterior tiene un asunto de directiva de punto de conexión y especifica que todos los mensajes enviados y recibidos desde el punto de conexión se deben optimizar utilizando MTOM.</span><span class="sxs-lookup"><span data-stu-id="6ac92-392">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>

- <span data-ttu-id="6ac92-393">B4212: Cuando se configura para usar la optimización de MTOM, un punto de conexión WCF agrega una aserción de directiva MTOM a la directiva asociada al correspondiente `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="6ac92-393">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="6ac92-394">Composición con WS-Security</span><span class="sxs-lookup"><span data-stu-id="6ac92-394">Composition with WS-Security</span></span>
<span data-ttu-id="6ac92-395">MTOM es un mecanismo de codificación que es similar a `text/xml` y XML binario WCF.</span><span class="sxs-lookup"><span data-stu-id="6ac92-395">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="6ac92-396">MTOM proporciona una composición natural con WS-Security y otros protocolos WS - \*: un mensaje protegido mediante WS-Security puede optimizarse mediante MTOM.</span><span class="sxs-lookup"><span data-stu-id="6ac92-396">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>

### <a name="examples"></a><span data-ttu-id="6ac92-397">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6ac92-397">Examples</span></span>

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="6ac92-398">Mensaje de SOAP 1.1 WCF codificado mediante MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-398">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>

```
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="6ac92-399">Mensaje de SOAP 1.2 WCF codificado mediante MTOM</span><span class="sxs-lookup"><span data-stu-id="6ac92-399">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>
<span data-ttu-id="6ac92-400">En este ejemplo, un mensaje se codifica utilizando MTOM y SOAP 1.2 que está protegido mediante WS-Security.</span><span class="sxs-lookup"><span data-stu-id="6ac92-400">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="6ac92-401">Las partes binarias identificadas para su codificación son el contenido de `BinarySecurityToken`, `CipherValue` de los `EncryptedData` que corresponden a la firma y al cuerpo cifrados.</span><span class="sxs-lookup"><span data-stu-id="6ac92-401">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="6ac92-402">Tenga en cuenta que el `CipherValue` de la `EncryptedKey` no se ha identificado para la optimización por WCF, porque su longitud es inferior a 1.024 bytes.</span><span class="sxs-lookup"><span data-stu-id="6ac92-402">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>

```
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml"; 
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```
