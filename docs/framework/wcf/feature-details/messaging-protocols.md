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
# <a name="messaging-protocols"></a>Protocolos de mensajería

La pila de canales de Windows Communication Foundation (WCF) emplea codificación y canales de transporte para transformar la representación interna de mensajes en su formato de conexión y enviarla utilizando un transporte determinado. El transporte más común utilizado para la interoperabilidad de servicios Web es HTTP y las codificaciones más comunes utilizadas por los servicios Web son las basadas en XML, SOAP 1.1, SOAP 1.2 y el Mecanismo de optimización de transmisión de mensajes (MTOM).

En este tema se trata los detalles de implementación de WCF para los siguientes protocolos empleados por <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.

Documento de especificaciones /:

- [HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)
- [Enlace SOAP 1.1 HTTP](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), sección 7
- [Enlace HTTP 1.2 de SOAP](https://www.w3.org/TR/soap12-part2) sección 7

En este tema cubre los detalles de implementación de WCF para los siguientes protocolos <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> emplear.

Documento de especificaciones /:

- [XML](https://www.w3.org/TR/REC-xml)
- [SOAP 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [Núcleo de SOAP 1.2](https://www.w3.org/TR/soap12-part1/)
- [WS-Addressing 2004/08](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [W3C Web Services Addressing 1.0 - núcleo](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [W3C Web Services Addressing 1.0 - enlace SOAP](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [W3C Web Services Addressing 1.0 – enlace WSDL](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [W3C Web Services Addressing 1.0 - metadatos](https://www.w3.org/TR/ws-addr-metadata/)
- [Enlace SOAP 1.1 de WSDL](https://www.w3.org/TR/wsdl/)
- [Enlace SOAP 1.2 de WSDL](https://www.w3.org/Submission/wsdl11soap12/)

En este tema cubre los detalles de implementación de WCF para los siguientes protocolos <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> emplea.

Documento de especificaciones /:

- [XOP](https://www.w3.org/TR/xop10/)
- [SOAP 1.2 + MTOM enlace](https://www.w3.org/TR/soap12-mtom/)
- [MTOM enlace SOAP 1.1](https://www.w3.org/Submission/soap11mtom10/)
- [Aserción de directiva WS MTOM](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

Los siguientes espacios de nombres XML y prefijos asociados se usan a lo largo de este tema:

| Prefijo | Espacio de nombres de identificador uniforme de recursos (URI) |
|------------|---------------------------------------------------|
| s11 | `http://schemas.xmlsoap.org/soap/envelope` |
| s12 |`http://www.w3.org/2003/05/soap-envelope` |
| wsa |`http://www.w3.org/2004/08/addressing` |
| wsam |`http://www.w3.org/2007/05/addressing/metadata` |
| wsap |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| wsa10 |`http://www.w3.org/2005/08/addressing` |
| wsaw10 |`http://www.w3.org/2006/05/addressing/wsdl` |
| xop |`http://www.w3.org/2004/08/xop/include` |
| xmime |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| dp |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a>SOAP 1.1 y SOAP 1.2

### <a name="envelope-and-processing-model"></a>Modelo de procesado y envoltura
WCF implementa el procesado de envoltura SOAP 1.1 siguiendo perfil básico 1.1 (BP11) y Basic Profile 1.0 (SSBP10). El procesamiento de envoltura SOAP 1.2 se implementa siguiendo SOAP12-Part1.

En esta sección se explica ciertas opciones de implementación tomadas por WCF con respecto a BP11 y SOAP12-Part1.

#### <a name="mandatory-header-processing"></a>Procesamiento del encabezado obligatorio
WCF sigue las reglas para procesar encabezados marcados `mustUnderstand` descritos en las especificaciones SOAP 1.1 y SOAP 1.2, con las siguientes variaciones.

Canales individuales configurados por elementos de enlace asociada, por ejemplo, codificación de mensajes de texto, seguridad, mensajería confiable y transacciones procesa un mensaje que entra en la pila de canales WCF. Cada canal reconoce los encabezados del espacio de nombres asociado y los marca como comprendidos. Cuando un mensaje escribe el distribuidor, el formateador de operaciones lee encabezados esperados por el contrato de operación/mensaje correspondiente y los marca como comprendidos. A continuación, el distribuidor comprueba si algún encabezado restante no se entiende pero está marcado como `mustUnderstand` y produce una excepción. Los mensajes que contienen encabezados `mustUnderstand` que tienen como destino el destinatario no son procesados por el código de aplicación de destinatario.

Tal procesamiento superpuesto permite la separación entre las capas de la infraestructura y las capas de la aplicación del nodo SOAP:

- B1111: Se detectan encabezados que no se entienden una vez que el mensaje es procesado por la pila de canales de infraestructura WCF, pero antes de procesarse por aplicación

     El valor de encabezado `mustUnderstand` difiere entre SOAP 1.1 y SOAP 1.2. Basic Profile 1.1 requiere que el valor `mustUnderstand` sea 0 o 1 para los mensajes SOAP 1.1. SOAP 1.2 permite 0, 1, `false` y `true` como valores, pero recomienda emitir una representación canónica de valores (`xs:boolean`, `false`) `true`.

- B1112: Emite WCF `mustUnderstand` valores 0 y 1 para las versiones de SOAP 1.1 y SOAP 1.2 de la envoltura SOAP. WCF acepta el espacio de valor completo de `xs:boolean` para el `mustUnderstand` encabezado (0, 1, `false`, `true`)

#### <a name="soap-faults"></a>Errores SOAP
La siguiente es una lista de implementaciones de errores de SOAP de WCF específico.

- B2121: WCF devuelve los siguientes códigos de error de SOAP 1.1: `s11:mustUnderstand`, `s11:Client`, y `s11:Server`.

- B2122: WCF devuelve los siguientes códigos de error de SOAP 1.2: `s12:MustUnderstand`, `s12:Sender`, y `s12:Receiver`.

### <a name="http-binding"></a>Enlace HTTP

#### <a name="soap-11-http-binding"></a>Enlace HTTP de SOAP 1.1
WCF implementa enlace HTTP de SOAP1.1 siguiendo la sección 3.4 siguientes aclaraciones de especificación de Basic Profile 1.1:

- B2211: Servicio de WCF no implementa la redirección de solicitudes HTTP POST.

- B2212: Los clientes de WCF admiten Cookies HTTP de acuerdo con 3.4.8.

#### <a name="soap-12-http-binding"></a>Enlace HTTP de SOAP 1,2
WCF implementa enlace HTTP de SOAP 1.2 tal y como se describe en SOAP 1.2-parte 2 (SOAP12Part2) especificación con las siguientes aclaraciones.

SOAP 1.2 introdujo un parámetro de acción opcional para el tipo de medio `application/soap+xml`. Este parámetro es útil para optimizar la distribución de mensajes sin requerir que se analice el cuerpo del mensaje SOAP cuando no se utiliza WS-Addresing.

- R2221: El `application/soap+xml` parámetro action, cuando está presente en una solicitud SOAP 1.2, debe coincidir con el `soapAction` atributo el `wsoap12:operation` elemento de enlace WSDL correspondiente.

- R2222: El `application/soap+xml` parámetro action, cuando está presente en un mensaje SOAP 1.2, debe coincidir con `wsa:Action` cuando se usan WS-Addressing 2004/08 o WS-Addressing 1.0.

Cuando WS-Addressing está deshabilitado y una solicitud entrante no contiene ningún parámetro de acción, `Action` del mensaje se considera como no especificada.

## <a name="ws-addressing"></a>WS-Addressing
WCF implementa 3 versiones de WS-Addressing:

- WS-Addressing 2004/08

- Núcleo de W3C Web Services Addressing 1.0 (ADDR10-CORE) y enlace SOAP (ADDR10-SOAP)

- WS-Addressing 1.0 - Metadatos

### <a name="endpoint-references"></a>Referencias de punto de conexión
Todas las versiones de WS-Addressing que implementa WCF usan referencias de punto de conexión para describir los puntos de conexión.

#### <a name="endpoint-references-and-ws-addressing-versions"></a>Referencias de punto de conexión y WS-Addressing
WCF implementa varios protocolos de infraestructura que usan WS-Addressing y en particular el `EndpointReference` elemento y `W3C.WsAddressing.EndpointReferenceType` (clase) (por ejemplo, WS-ReliableMessaging, WS-SecureConversation y WS-Trust). WCF admite el uso de cualquier versión de WS-Addressing con otros protocolos de infraestructura. Los extremos de WCF admiten una versión de WS-Addressing por punto de conexión.

Para R3111, el espacio de nombres para el `EndpointReference` elemento o el tipo utilizado en mensajes intercambiados con un extremo de WCF debe coincidir con la versión de WS-Addressing implementado por este extremo.

Por ejemplo, si un extremo de WCF implementa WS-ReliableMessaging, el `AcksTo` devuelto por este extremo dentro del encabezado `CreateSequenceResponse` usa la versión de WS-Addressing que el `EncodingBinding` elemento especifica para este extremo.

#### <a name="endpoint-references-and-metadata"></a>Referencias de punto de conexión y metadatos
Varios escenarios requieren comunicar metadatos o una referencia a los metadatos para un punto de conexión determinado.

B3121: WCF emplea mecanismos descritos en la sección 6, para incluir metadatos para referencias de punto de conexión por valor o por referencia de la especificación de WS-MetadataExchange (MEX).

Considere un escenario donde un servicio WCF requiere la autenticación mediante un token de lenguaje de marcado de aserción de seguridad (SAML) emitido por el emisor del token en `http://sts.fabrikam123.com`. El punto de conexión WCF describe este requisito de autenticación mediante `sp:IssuedToken` aserción con anidada `sp:Issuer` aserción que señala al emisor del token. Las aplicaciones de cliente que obtienen acceso a la aserción `sp:Issuer` han de saber cómo comunicarse con el punto de conexión del emisor del token. El cliente ha de saber los metadatos sobre el emisor del token. Con las extensiones de metadatos de referencia de punto de conexión definidas en MEX, WCF proporciona una referencia a los metadatos del emisor del token.

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

### <a name="message-addressing-headers"></a>Encabezados de direccionamiento de mensajes

#### <a name="message-headers"></a>Encabezados de mensajes
Para ambas versiones de WS-Addressing, WCF usa los siguientes encabezados de mensaje tal y como describen las especificaciones `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, y `wsa:RelatesTo`.

B3211: Para todas las versiones de WS-Addressing, WCF respeta, pero no se genera desde el principio, los encabezados de mensaje de WS-Addressing `wsa:FaultTo` y `wsa:From`.

Las aplicaciones que interactúan con aplicaciones WCF que se pueden agregar que estos encabezados de mensaje y WCF procesará consecuentemente.

#### <a name="reference-parameters-and-properties"></a>Parámetros de referencia y propiedades

WCF implementa el procesamiento de los parámetros de referencia de punto de conexión y propiedades de referencia de acuerdo con las especificaciones respectivas.

B3221: Cuando se configura para utilizar WS-Addressing 2004/08, los extremos de WCF no diferencian entre procesar propiedades de referencia y los parámetros de referencia.

### <a name="message-exchange-patterns"></a>Modelos de intercambio de mensajes
La secuencia de mensajes implicada en la invocación de operación de servicio Web se conoce como el *patrón de intercambio de mensajes*. Patrones de intercambio de mensajes dúplex, de solicitud-respuesta y unidireccionales de WCF admite. En esta sección se aclaran los requisitos de WS-Addressing sobre el procesamiento de mensajes en función del patrón de intercambio de mensajes que se utiliza.

A lo largo de esta sección, el solicitante envía el primer mensaje y el respondedor recibe el primer mensaje.

#### <a name="one-way-message"></a>Mensaje unidireccional
Cuando se configura un extremo de WCF para admitir mensajes con un determinado `Action` para seguir un patrón unidireccional, el punto de conexión WCF sigue los siguientes comportamientos y requisitos. A menos que se especifique lo contrario, los comportamientos y reglas se aplican a ambas versiones de WS-Addressing de WCF admitidos:

- R3311: El solicitante debe incluir `wsa:To`, `wsa:Action`y los encabezados para todos los parámetros de referencia especificados por la referencia del extremo. Cuando se utiliza WS-Addressing 2004/08 y la referencia de punto de conexión especifica las [propiedades de referencia], los encabezados correspondientes también deben agregarse al mensaje.

- B3312: El solicitante puede incluir `MessageID`, `ReplyTo`, y `FaultTo` encabezados. La infraestructura del receptor los omitirá y se pasarán a la aplicación.

- R3313: Cuando se usa HTTP y no se envía ningún mensaje en la bifurcación de la respuesta HTTP, el Respondedor debe enviar una respuesta HTTP con un cuerpo vacío y un código de estado HTTP 202.

     Si el transporte HTTP está en uso y el contrato de operación declara un mensaje unidireccional, la respuesta HTTP todavía se puede utilizar para enviar mensajes de infraestructura, por ejemplo, la mensajería de confianza puede enviar un mensaje `SequenceAcknowledgement` en una respuesta HTTP.

- B3314: El servicio de respuesta WCF no envía un mensaje de error en respuesta a un mensaje unidireccional.

#### <a name="request-reply"></a>Solicitud-respuesta
Cuando se configura un extremo de WCF para un mensaje con un determinado `Action` para seguir el patrón de solicitud-respuesta, el punto de conexión WCF sigue los comportamientos y requisitos siguientes. A menos que se especifique lo contrario, los comportamientos y reglas se aplican a ambas versiones de WS-Addressing de WCF admitidos:

- R3321: El solicitante debe incluir en la solicitud `wsa:To`, `wsa:Action`, `wsa:MessageID`y los encabezados para todos los parámetros de referencia o referencia propiedades (o ambos) especificados por la referencia del extremo.

- R3322: Cuando se utiliza WS-Addressing 2004/08, `ReplyTo` también debe incluirse en la solicitud.

- R3323: Cuando se utiliza WS-Addressing 1.0 y `ReplyTo` no está presente en la solicitud, una referencia de punto de conexión predeterminada con la propiedad [dirección] igual a `http://www.w3.org/2005/08/addressing/anonymous` se utiliza.

- R3324: El solicitante debe incluir `wsa:To`, `wsa:Action`, y `wsa:RelatesTo` encabezados en el mensaje de respuesta, así como los encabezados para todos los parámetros de referencia o referencia propiedades (o ambos) especificados por el `ReplyTo` referencia del extremo en la solicitud.

### <a name="web-services-addressing-faults"></a>Errores de direccionamiento de servicios Web
R3411: WCF genera los siguientes errores definidos por WS-Addressing 2004/08.

| Código | Motivo |
|----------|-----------|
| `wsa:DestinationUnreachable` | El mensaje llegó con un `ReplyTo` diferente a la dirección de respuesta establecida para este canal; no hay ningún punto de conexión que escuche en la dirección especificada en el encabezado To. |
| `wsa:ActionNotSupported` | los canales de infraestructura o el distribuidor asociados al punto de conexión no reconocen la acción especificada en el encabezado `Action`. |

R3412: WCF genera los siguientes errores definidos por WS-Addressing 1.0.

| Código | Motivo |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | Duplicar `wsa:To`, `wsa:ReplyTo`, `wsa:From` o `wsa:MessageID`. Duplicar `wsa:RelatesTo` con el mismo `RelationshipType`. |
| `wsa10:MessageAddressingHeaderRequired` | Falta el encabezado Addressing necesario. |
| `wsa10:DestinationUnreachable` | El mensaje llegó con un `ReplyTo` diferente a la dirección de respuesta establecida para este canal. No hay ningún punto de conexión escuchando en la dirección especificada en encabezado To. |
| `wsa10:ActionNotSupported` | Los canales de infraestructura o el distribuidor asociados al punto de conexión no reconocen una acción especificada en el encabezado `Action`. |
| `wsa10:EndpointUnavailable` | El canal RM devuelve este error, indicando que el extremo no procesará la secuencia basada en el examen de los encabezados de direccionamiento del mensaje `CreateSequence`. |

El código de las tablas anteriores se asigna a `FaultCode` en SOAP 1.1 y `SubCode` (con Code=Sender) en SOAP 1.2.

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a>Enlace WSDL 1.1 y aserciones de WS-Policy

#### <a name="indicating-use-of-ws-addressing"></a>Indicación del uso de WS-Addressing
WCF utiliza las aserciones de directiva para indicar la compatibilidad de punto de conexión para una determinada versión de WS-Addressing.

La siguiente aserción de directiva tiene Asunto de directiva de extremo [WS PA] e indica que los mensajes enviados y recibidos desde el extremo deben utilizar WS-Addressing 2004/08.

```xml
<wsap:UsingAddressing />
```

Esta aserción de directiva aumenta la especificación WS-Addressing 2004/08.

La siguiente aserción de directiva indica que los mensajes enviados y recibidos deben usar WS-Addressing 1.0.

```xml
<wsam:Addressing/>
```

La siguiente aserción de directiva tiene un asunto de directiva de punto de conexión [WS PA] e indica que los mensajes enviados y recibidos desde el punto de conexión deben utilizar WS-Addressing 2004/08.

```xml
<wsaw10:UsingAddressing />
```

El elemento `wsaw10:UsingAddressing` se toma prestado de [WSDL de WS-Addressing] y se utiliza en el contexto de WS-Addressing cumpliendo con esa especificación, sección 3.1.2.

El uso de direccionamiento no modifica la semántica de WSDL 1.1, SOAP 1.1 y enlaces HTTP SOAP 1.2. Por ejemplo, si una respuesta se espera para una solicitud que se envía a un punto de conexión que usa direccionamiento y enlace HTTP de SOAP 1.x de WSDL, la respuesta se debe enviar utilizando la respuesta HTTP.

Para las respuestas enviadas a través de la respuesta http, la aserción de WS-AM es:

```xml
<wsam:AnonymousResponses/>
```

La apariencia de la aserción de directiva completa debe ser como esta:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Sin embargo, hay patrones de intercambio de mensajes que se benefician de tener dos conexiones HTTP inversas independientes establecidas entre el solicitante y el respondedor, por ejemplo, los mensajes unidireccionales no solicitados enviados por el respondedor.

WCF ofrece una característica por la que dos canales de transporte subyacentes pueden formar un canal dúplex compuesto, donde un canal se usa para mensajes de entrada y la otra se usa para los mensajes de salida. En el caso del transporte HTTP, el Dúplex Compuesto proporciona dos conexiones HTTP inversas. El solicitante utiliza una conexión para enviar mensajes al respondedor y el respondedor usa la otra para devolver mensajes al solicitante.

Para las respuestas enviadas a través de solicitudes independientes http, la aserción de ws-am es:

```xml
<wsam:NonAnonymousResponses/>
```

La apariencia de la aserción de directiva completa debe ser como esta:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

El uso de la siguiente aserción que tiene un asunto de extremo de directiva [WS-PA] en los extremos que usan enlaces HTTP de SOAP 1.1x de WDSL 1.1 requiere dos conexiones HTTP inversas independientes que se utilizarán para los mensajes que fluyen del solicitante al respondedor y del respondedor al solicitante, respectivamente.

```xml
<cdp:CompositeDuplex/>
```

La declaración anterior conduce a los siguientes requisitos en el encabezado `wsa:ReplyTo` para los mensajes de solicitud:

- R3514: Solicitar a los mensajes enviados a un punto de conexión deben tener un `ReplyTo` encabezado con el `[address]` propiedad no es igual a `http://www.w3.org/2005/08/addressing/anonymous` si el punto de conexión utiliza un enlace de WSDL 1.1 SOAP 1.x HTTP y tiene una directiva alternativa con un `wsap10:UsingAddressing` o `wsap:UsingAddressing` aserción junto con `cdp:CompositeDuplex` adjunta.

- R3515: Solicitar a los mensajes enviados a un punto de conexión deben tener un `ReplyTo` encabezado con el `[address]` propiedad igual a `http://www.w3.org/2005/08/addressing/anonymous`, o no tiene un `ReplyTo` encabezado en absoluto, si el punto de conexión utiliza un enlace de WSDL 1.1 SOAP 1.x HTTP y tiene una directiva alternativa con `wsap10:UsingAddressing` aserción y no `cdp:CompositeDuplex` aserción adjuntada.

- R3516: Solicitar a los mensajes enviados a un punto de conexión deben tener un `ReplyTo` encabezado con un `[address]` propiedad igual a `http://www.w3.org/2005/08/addressing/anonymous` si el punto de conexión utiliza un enlace de WSDL 1.1 SOAP 1.x HTTP y tiene una directiva alternativa con `wsap:UsingAddressing` aserción y no `cdp:CompositeDuplex` aserción adjuntada.

La especificación WSDL de WS-Addressing intenta describir enlaces de protocolos similares introduciendo un elemento `<wsaw:Anonymous/>` con tres valores textuales (requerido, opcional y prohibido) para indicar requisitos en el encabezado `wsa:ReplyTo` (sección 3.2). Desafortunadamente, tal definición de elemento no es especialmente utilizable como aserción en el contexto de WS-Policy, porque requiere extensiones específicas del dominio para admitir la intersección de alternativas usando este tipo de elementos como aserción. Tal definición de elemento también indica el valor del encabezado `ReplyTo` frente al comportamiento del extremo en la conexión, que lo hace específico para el transporte HTTP.

#### <a name="action-definition"></a>Definición de acción
WS-Addressing 2004/08 define un atributo `wsa:Action` para los elementos`wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`. El enlace ESDL de WS-Addressing 1.0 (WS-ADDR10-WSDL) define un atributo similar, `wsaw10:Action`.

La única diferencia entre los dos es la semántica de patrón de Acción predeterminada descrita en la sección 3.3.2 de WS-ADDR y la sección 4.4.4 de WS-ADDR10-WSDL, respectivamente.

Es razonable tener dos extremos que comparten el mismo `portType` (o contrato, en la terminología de WCF), pero con diferentes versiones de WS-Addressing. Pero suponiendo que esa acción esté definida por `portType` y no debería cambiar a lo largo de los extremos que implementan `portType`, se hace imposible admitir ambos patrones de acción predeterminados.

Para resolver esta controversia, WCF admite una única versión de la `Action` atributo.

B3521: WCF usa la `wsaw10:Action` atributo `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elementos tal como se define en WS-ADDR10-WSDL para determinar el `Action` URI para los mensajes correspondientes independientemente de la versión de WS-Addressing utilizada por el punto de conexión.

#### <a name="use-endpoint-reference-inside-wsdl-port"></a>Uso de la referencia de extremo dentro del puerto WSDL
La sección 4.1 de WS-ADDR10-WSDL extiende el elemento `wsdl:port` para incluir el elemento secundario `<wsa10:EndpointReference…/>` para describir el punto de conexión en términos de WS-Addressing. WCF expande esta utilidad en WS-Addressing 2004/08, permitiendo `<wsa:EndpointReference…/>` aparezca como un elemento secundario de `wsdl:port`.

- R3531: Si un punto de conexión tiene una directiva alternativa adjunta con una `<wsaw10:UsingAddressing/>` aserción de directiva, la correspondiente `wsdl:port` elemento puede contener un elemento secundario `<wsa10:EndpointReference …/>`.

- R3532: Si un `wsdl:port` contiene un elemento secundario `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` valor del elemento secundario debe coincidir con el valor de la `@address` atributo del nodo relacionado `wsdl:port` / `wsdl:location` elemento.

- R3533: Si un punto de conexión tiene una directiva alternativa adjunta con `<wsap:UsingAddressing/>` aserción de directiva, la correspondiente `wsdl:port` elemento puede contener un elemento secundario `<wsa:EndpointReference …/>`.

- R3534: Si un `wsdl:port` contiene un elemento secundario `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` valor del elemento secundario debe coincidir con el valor de la `@address` atributo del nodo relacionado `wsdl:port` / `wsdl:location` elemento.

### <a name="composition-with-ws-security"></a>Composición con WS-Security
Según las secciones de consideración de seguridad en WS-ADDR y WS-ADDR10, se recomienda que todos los encabezados de mensajes de direccionamiento se firmen junto con el cuerpo del mensaje para enlazarlos juntos.

Cuando WS-Security se utiliza para la protección de la integridad de mensajes, los encabezados de mensajes WS-Addressing, así como los encabezados resultantes de parámetros o propiedades de referencia (o ambos) se deben firmar junto con el cuerpo del mensaje.

### <a name="examples"></a>Ejemplos

#### <a name="one-way-message"></a>Mensaje unidireccional
En este escenario, el remitente envía un mensaje unidireccional al receptor. Se usan SOAP 1.2, HTTP 1.1 y WS-Addressing de W3C 1.0.

La estructura del mensaje de solicitud: Incluyen los encabezados del mensaje `wsa10:To` y `wsa10:Action` elementos. El cuerpo del mensaje incluye un elemento `<app:Ping>` concreto del espacio de nombres de la aplicación.

Encabezados HTTP: El destino en POST coincide con el URI en el `wsa10:To` elemento.

El encabezado Content-Type tiene el valor de `application/soap+xml` que requiere SOAP 1.2. Se incluyen los parámetros `charset` y `action`. El parámetro `action` del encabezado Content-Type coincide con el valor del encabezado `wsa10:Action` del mensaje.

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

El receptor responde con una respuesta HTTP vacía y el estado 202. Un ejemplo de la respuesta HTTP:

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

## <a name="soap-message-transmission-optimization-mechanism"></a>Mecanismo de optimización de transmisión de mensajes SOAP
Esta sección describen los detalles de implementación de WCF para MTOM de SOAP de HTTP. Tecnología de MTOM es el mecanismo de codificación de mensaje SOAP de la misma clase que la codificación de XML/texto tradicional o codificación binaria en WCF. MTOM incluye lo siguiente:

- Una codificación de XML y un mecanismo de empaquetado descritos por [XOP] que optimiza elementos de información XML que contienen datos binarios codificados por base64 en partes binarias independientes.

- Una encapsulación MIME del paquete de XOP que serializa el conjunto de información XML y cada parte binaria del paquete de XOP en una parte MIME independiente.

- Una codificación XOP MIME aplicada a la envoltura de SOAP 1.x.

- Un enlace de transporte HTTP.

Es posible utilizar MTOM con transportes no HTTP con WCF. Sin embargo, en este tema nos centraremos en HTTP.

El formato MTOM reutiliza un largo conjunto de especificaciones que cubren el propio MTOM, XOP y MIME. La modularidad de este conjunto de especificaciones hace algo difícil reconstruir requisitos exactos en la semántica de procesamiento y formato. En esta sección se describe los requisitos de procesamiento y formato para enlace MTOM.

### <a name="mtom-message-encoding"></a>Codificación de mensajes MTOM

#### <a name="generating-mtom-messages"></a>Generación de mensajes MTOM
La sección 3.1 de [XOP] describe el proceso de codificación de XML con elementos de información de elementos que contienen los valores de base64 en un paquete XOP definido de manera abstracta.

La siguiente secuencia de pasos describe el proceso de codificación específico del MTOM:

1. Asegúrese de que la envoltura de SOAP que se desea codificar no contiene ninguna información de elemento con un `[namespace name]` de `http://www.w3.org/2004/08/xop/include` y un `[local name]` de `Include`.

2. Cree un paquete MIME vacío.

3. Identifique los elementos de información que se van a optimizar dentro del conjunto de información XML original. Para que los elementos que se optimizarán, los caracteres que constituyen el `[children]` de la información del elemento elemento debe estar en la forma canónica de `xs:base64Binary` (Véase XSD-2, 3.2.16 base64Binary) y no puede contener cualquier carácter de espacio en blanco anterior, en línea, o siguen al contenido que no sea un espacio en blanco.

4. Cree una envoltura SOAP de XOP que sea una copia de la envoltura SOAP original, pero con los elementos secundarios de cada elemento de información de elemento identificados en el paso anterior reemplazados por un elemento de información de elemento `xop:Include` construido de la siguiente manera:

    1. Transforme los caracteres reemplazados en datos binarios procesándolos como datos codificados en base64.

    2. Genere un valor del encabezado Content-ID único que cumpla los requisitos R3133 y R3134.

    3. Genere un encabezado MIME de codificación de transferencia del contenido con el valor binario.

    4. Si el elemento de información de elemento que se optimiza (el [primario] del elemento de información de elemento recientemente insertado `xop:Include`) tiene un elemento de información de atributos `xmime:contentType`, genere un encabezado MIME de tipo de contenido con el valor del atributo `xmime:contentType`.

    5. Genere una nueva parte MIME binaria con contenido formado por datos binarios descodificados a partir de los caracteres reemplazados procesados como base64, encabezado del Content-ID de 4b, encabezado de codificación de transferencia de contenido de 4c, encabezado de tipo de contenido si se generó en el paso 4d.

    6. Agregue un atributo `href` al elemento `xop:Include` con el valor cid: uri derivado del valor del encabezado Content-ID generado en el paso 4b. Quitar el cierre "\<" y ">" caracteres, la cadena restante y agregue el prefijo de dirección URL de escape `cid:`. El juego de caracteres mínimo siguiente se exige para que RFC1738 y RFC2396 puedan escapar. Se pueden escapar otros caracteres.

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. Cree una parte MIME de raíz con la envoltura SOAP de XOP a partir del paso 4.

6. Escriba los encabezados HTTP, incluido de tipo de contenido HTTP.

7. Escriba el paquete MIME.

#### <a name="processing-mtom-messages"></a>Procesamiento de mensajes MTOM
Procesar un mensaje MTOM es justo lo contrario al proceso descrito en la sección “Generación de mensajes MTOM":

1. Asegúrese de que la parte MIME de la raíz tiene el tipo de contenido `application/xop+xml`.

2. Construya una envoltura SOAP analizando la parte MIME de la raíz del paquete como un documento XML. El parámetro `charset` del tipo de contenido de la parte MIME de la raíz determina la codificación de caracteres.

3. Para cada elemento de información de elemento en la envoltura SOAP construida, que tiene, como único miembro de su propiedad [elemento secundario], un elemento de información de elemento `xop:Include`:

    1. Elimine el prefijo `cid:` y quite los caracteres de escape de todas las secuencias de escape de URI (RFC 2396) en el valor del atributo `@href` del elemento `xop:Include`. Incluya la cadena de resultado de "\<", ">".

    2. Busque la parte MIME con el valor del encabezado de identificador de contenido que coincida con la cadena derivada en el paso 3a.

    3. Reemplace el elemento de información de elemento `xop:Include` que aparece en la propiedad `children` de cada elemento con los elementos de información de caracteres que representan la codificación de base64 canónica (vea XSD-2, 3.2.16 base64Binary) del cuerpo de la entidad de la parte MIME identificada en el paso 3b (reemplace de manera eficaz el elemento de información de elemento `xop:Include` con los datos reconstruidos a partir de la parte del paquete).

#### <a name="http-content-type-header"></a>Encabezado de tipo de contenido HTTP
La siguiente es una lista de aclaraciones de WCF para el formato del encabezado HTTP Content-Type de un mensaje SOAP 1.x codificados por MTOM derivado de los requisitos establecidos en la propia especificación MTOM y se deriva de MTOM y RFC 2387.

- R4131: El valor de multiparte/relacionado (mayúsculas y minúsculas) y sus parámetros, debe tener un encabezado HTTP Content-Type. Los nombres de parámetros no distinguen mayúsculas de minúsculas. El orden de los parámetros no importa.

- Se enumera la forma de Backus-Naur completa (BNF) del encabezado de tipo de contenido para los mensajes MIME en RFC 2045, sección 5.1.

- R4132: Un encabezado HTTP Content-Type debe tener un parámetro de tipo con el valor `application/xop+xml` entre comillas dobles.

Aunque el requisito para usar comillas dobles no es explícito en RFC 2387, el texto observa que todos los parámetros de tipo de medio de multiparte/relacionado probablemente contienen caracteres reservados como "\@" o "/" y, por tanto, necesitan comillas dobles marcas.

- R4133: Un encabezado HTTP Content-Type debe tener un parámetro de inicio con el valor del encabezado Content-ID de la parte MIME que contiene el mensaje SOAP 1.x sobres, entrecomillada comillas dobles. Si se omite el parámetro de inicio, la primera parte MIME debe contener la envoltura de SOAP 1.x.

- R4134: Un encabezado HTTP Content-Type para un mensaje codificado de MTOM de SOAP 1.1 debe incluir el parámetro de información de inicio con el valor de texto/xml, encerrado entre comillas dobles.

- R4135: Un encabezado HTTP Content-Type para un mensaje codificado en MTOM de SOAP 1.2 debe incluir el parámetro de información de inicio con el valor de `application/soap+xml`, encerrado entre comillas dobles.

- R4136: Encabezado HTTP Content-Type para un mensaje codificado en MTOM de SOAP 1.x debe tener el parámetro de límite con el valor (entre comillas dobles) que coincide con el límite MIME que BNF definido en RFC 2046, sección 5.1.1

    ```
    boundary := 0*69<bchars> bcharsnospace 
    bchars := bcharsnospace / " " 
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+" 
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     Ejemplos:

     CORRECTO

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     CORRECTO

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     INCORRECTO

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1" 
    ```

#### <a name="infoset-mime-part"></a>Parte del conjunto de información de MIME
La envoltura de SOAP 1.x se encapsula como una parte de la raíz del paquete de MIME XOP y se llama a menudo la parte `infoset`.

- R4141: SOAP 1.x sobres se deben encapsular como una parte de la raíz del paquete de XOP MIME, denominado el `infoset` parte y que se hace referencia desde el tipo de contenido HTTP.

- R4142: SOAP `Infoset` parte debe incluir los encabezados MIME siguientes: `Content-ID`, `Content-Transfer-Encoding`, y `Content-Type`.

RFC 2045 define el formato del encabezado del id. de contenido como

```
"Content-ID" ":" msg-id
```

donde `msg-id` está definido en RFC 2822 (que reemplaza a RFC 822, al que se hace referencia en RFC 2045) como:

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

y es efectivamente una dirección de correo electrónico encerrada entre "\<" y ">". El prefijo y sufijo `[CFWS]` se agregaron en RFC 2822 para incluir comentarios y no deben usarse para conservar la interoperabilidad.

R4143: El valor del encabezado Content-ID de la parte MIME del conjunto de información debe seguir `msg-id` producción de RFC 2822 con el `[CFWS]` partes de prefijo y sufijo se omite.

Varias implementaciones MIME redujeron los requisitos para el valor encerrado entre "\<" y ">" para ser una dirección de correo electrónico y usar `absoluteURI` entre "\<", ">" Además de la dirección de correo electrónico. Esta versión de WCF usa los valores del encabezado MIME Content-ID del formulario:

```
Content-ID: <http://tempuri.org/0> 
```

R4144: Procesadores MTOM deberían aceptar más flexible de los siguientes valores que coincidan con los valores de encabezado Content-ID `msg-id`.

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

MIME (RFC 2045) proporciona el encabezado de codificación de transferencia de contenido para comunicar la codificación del contenido de la parte MIME. El valor predeterminado definido para la codificación de transferencia de contenido es 7 bits, que no es apto para la mayoría de mensajes SOAP, por lo que el encabezado de codificación de transferencia de contenido se necesita para una mayor interoperabilidad:

- R4145: La parte del conjunto de información de SOAP debe contener el encabezado Content-Transfer-Encoding.

- R4146: Si la codificación de caracteres de la envoltura SOAP es UTF-8, el valor del encabezado Content-Transfer-Encoding debe ser de 8 bits.

- R4147: Si la codificación de caracteres de la envoltura SOAP es UTF-16, el valor del encabezado Content-Transfer-Encoding debe ser binario.

- Según la sección 5 de [XOP],

- R4148: Parte del conjunto de información de SOAP 1.1 debe contener el encabezado Content-Type con el tipo de medio aplicación/xop + xml y los parámetros type = "text/xml" y juego de caracteres

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- R4149: La parte del conjunto de información de SOAP 1.2 debe contener el encabezado Content-Type con el tipo de medio `application/xop+xml` y los parámetros type = "`application/soap+xml`" y `charset`.

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     Aunque XOP defina el parámetro `charset` para `application/xop+xml` como opcional, se necesita para una interoperabilidad similar a la del requisito BP 1.1 del parámetro `charset` para el tipo de medio `text/xml`.

- R41410: El `type` y `charset` parámetros deben estar presentes en el encabezado Content-Type del elemento de conjunto de información SOAP 1.x.

#### <a name="wcf-endpoint-support-for-mtom"></a>Compatibilidad de punto de conexión WCF para MTOM.
El propósito de MTOM es codificar un mensaje SOAP para optimizar los datos codificados en base64. A continuación se muestra una lista de restricciones:

- R4151: Se puede optimizar cualquier información de elemento que contiene datos codificados en base64.

- B4152: WCF optimiza elementos de información que contienen datos codificados en base64 y superan los 1.024 bytes de longitud.

Un extremo de WCF configurado para utilizar MTOM siempre enviará los mensajes codificados por MTOM. Incluso cuando ninguna parte cumpla los criterios necesarios, el mensaje seguirá estando codificado por MTOM (serializado como un paquete MIME con una parte MIME única que contiene la envoltura SOAP).

### <a name="ws-policy-assertion-for-mtom"></a>Aserción de la WS-Policy para MTOM
WCF usa la siguiente aserción de directiva para indicar el uso de MTOM por extremo:

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- R4211: La aserción de directiva anterior tiene un asunto de directiva de punto de conexión y especifica que todos los mensajes enviados y recibidos desde el punto de conexión se deben optimizar utilizando MTOM.

- B4212: Cuando se configura para usar la optimización de MTOM, un punto de conexión WCF agrega una aserción de directiva MTOM a la directiva asociada al correspondiente `wsdl:binding`.

### <a name="composition-with-ws-security"></a>Composición con WS-Security
MTOM es un mecanismo de codificación que es similar a `text/xml` y XML binario WCF. MTOM proporciona una composición natural con WS-Security y otros protocolos WS - *: un mensaje protegido mediante WS-Security puede optimizarse mediante MTOM.

### <a name="examples"></a>Ejemplos

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a>Mensaje de SOAP 1.1 WCF codificado mediante MTOM

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

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a>Mensaje de SOAP 1.2 WCF codificado mediante MTOM
En este ejemplo, un mensaje se codifica utilizando MTOM y SOAP 1.2 que está protegido mediante WS-Security. Las partes binarias identificadas para su codificación son el contenido de `BinarySecurityToken`, `CipherValue` de los `EncryptedData` que corresponden a la firma y al cuerpo cifrados. Tenga en cuenta que el `CipherValue` de la `EncryptedKey` no se ha identificado para la optimización por WCF, porque su longitud es inferior a 1.024 bytes.

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
