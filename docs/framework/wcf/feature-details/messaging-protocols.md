---
title: "Protocolos de mensajer&#237;a | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Protocolos de mensajer&#237;a
La pila del canal [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] emplea codificación y canales de transporte para transformar la representación interna de mensajes en su formato de conexión y enviarla utilizando un transporte determinado.El transporte más común utilizado para la interoperabilidad de servicios Web es HTTP y las codificaciones más comunes utilizadas por los servicios Web son las basadas en XML, SOAP 1.1, SOAP 1.2 y el Mecanismo de optimización de transmisión de mensajes \(MTOM\).  
  
 Este tema cubre los detalles de implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para los siguientes protocolos empleados por <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.  
  
|Especificación\/documento|Vínculo|  
|-------------------------------|-------------|  
|HTTP 1.1|http:\/\/www.ietf.org\/rfc\/rfc2616.txt|  
|Enlace HTTP SOAP 1.1|http:\/\/www.w3.org\/TR\/2000\/NOTE\-SOAP\-20000508\/, sección 7|  
|Enlace HTTP SOAP 1.2|http:\/\/www.w3.org\/TR\/soap12\-part2\/, sección 7|  
  
 Este tema cubre los detalles de implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para los siguientes protocolos empleados por <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
|Especificación\/documento|Vínculo|  
|-------------------------------|-------------|  
|XML|http:\/\/www.w3.org\/TR\/REC\-xml|  
|SOAP 1.1|http:\/\/www.w3.org\/TR\/2000\/NOTE\-SOAP\-20000508\/|  
|Núcleo de SOAP 1.2|http:\/\/www.w3.org\/TR\/soap12\-part1\/|  
|WS\-Addressing 2004\/08|http:\/\/www.w3.org\/Submission\/2004\/SUBM\-ws\-addressing\-20040810\/|  
|W3C Web Services Addressing 1.0 \- Núcleo|http:\/\/www.w3.org\/TR\/2006\/REC\-ws\-addr\-core\-20060509|  
|W3C Web Services Addressing 1.0 – Enlace SOAP|http:\/\/www.w3.org\/TR\/2006\/REC\-ws\-addr\-soap\-20060509|  
|W3C Web Services Addressing 1.0 – Enlace WSDL|http:\/\/www.w3.org\/TR\/2006\/CR\-ws\-addr\-wsdl\-20060529\/|  
|W3C Web Services Addressing 1.0 \- Metadatos|http:\/\/www.w3.org\/TR\/ws\-addr\-metadata\/|  
|Enlace SOAP 1.1 de WSDL|http:\/\/www.w3.org\/TR\/wsdl\/|  
|Enlace SOAP 1.2 de WSDL|http:\/\/www.w3.org\/Submission\/wsdl11soap12\/|  
  
 Este tema cubre los detalles de implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para los siguientes protocolos que emplea<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
|Especificación\/documento|Vínculo|  
|-------------------------------|-------------|  
|XOP|http:\/\/www.w3.org\/TR\/xop10\/|  
|Enlace SOAP 1.2 \+ MTOM|http:\/\/www.w3.org\/TR\/soap12\-mtom\/|  
|Enlace SOAP 1.1 MTOM|http:\/\/www.w3.org\/Submission\/soap11mtom10\/|  
|Aserción de directiva WS MTOM|http:\/\/www.w3.org\/Submission\/2006\/SUBM\-WS\-MTOMPolicy\-20061101\/.|  
  
 Los siguientes espacios de nombres XML y prefijos asociados se usan en todo este tema.  
  
|Prefijo|Espacio de nombres de identificador uniforme de recursos \(URI\)|  
|-------------|----------------------------------------------------------------------|  
|s11|http:\/\/schemas.xmlsoap.org\/soap\/envelope|  
|s12|http:\/\/www.w3.org\/2003\/05\/soap\-envelope|  
|wsa|http:\/\/www.w3.org\/2004\/08\/addressing|  
|wsam|http:\/\/www.w3.org\/2007\/05\/addressing\/metadata|  
|wsap|http:\/\/schemas.xmlsoap.org\/ws\/2004\/09\/policy\/addressing|  
|wsa10|http:\/\/www.w3.org\/2005\/08\/addressing|  
|wsaw10|http:\/\/www.w3.org\/2006\/05\/addressing\/wsdl|  
|xop|http:\/\/www.w3.org\/2004\/08\/xop\/include|  
|xmime|http:\/\/www.w3.org\/2004\/06\/xmlmime<br /><br /> http:\/\/www.w3.org\/2005\/05\/xmlmime|  
|cdp|http:\/\/schemas.microsoft.com\/net\/2006\/06\/duplex|  
  
## SOAP 1.1 y SOAP 1.2  
  
### Modelo de procesado y envoltura  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa el procesado de envoltura SOAP 1.1 siguiendo Perfil básico 1.1 \(BP11\) y Perfil básico 1.0 \(SSBP10\).El procesamiento de envoltura SOAP 1.2 se implementa siguiendo SOAP12\-Part1.  
  
 En esta sección se explican ciertas opciones de implementación tomadas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con respecto a BP11 y SOAP12\-Part1.  
  
#### Procesamiento del encabezado obligatorio  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sigue las reglas para procesar encabezados marcados `mustUnderstand` descritos en las especificaciones SOAP 1.2 y SOAP 1.1, con las siguientes variaciones.  
  
 Un mensaje que entra la pila de canales de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es procesado por canales individuales configurados por elementos de enlace asociados, como, por ejemplo, codificación de mensajes de texto, seguridad, mensajería de confianza y transacciones.Cada canal reconoce los encabezados del espacio de nombres asociado y los marca como comprendidos.Cuando un mensaje escribe el distribuidor, el formateador de operaciones lee encabezados esperados por el contrato de operación\/mensaje correspondiente y los marca como comprendidos.A continuación, el distribuidor comprueba si algún encabezado restante no se entiende pero está marcado como `mustUnderstand` y produce una excepción.Los mensajes que contienen encabezados `mustUnderstand` que tienen como destino el destinatario no son procesados por el código de aplicación de destinatario.  
  
 Tal procesamiento superpuesto permite la separación entre las capas de la infraestructura y las capas de la aplicación del nodo SOAP:  
  
-   B1111: se detectan encabezados que no se entienden una vez que la pila de canales de la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] procesa el mensaje, pero antes que lo procese la aplicación  
  
     El valor de encabezado `mustUnderstand` difiere entre SOAP 1.1 y SOAP 1.2.Basic Profile 1.1 requiere que el valor `mustUnderstand` sea 0 o 1 para los mensajes SOAP 1.1.SOAP 1.2 permite 0, 1, `false` y `true` como valores, pero recomienda emitir una representación canónica de valores \(`false`, `true`\) `xs:boolean`.  
  
-   B1112: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emite los valores 0 y 1 de `mustUnderstand` para ambas versiones de SOAP 1.1 y SOAP 1.2 del sobre SOAP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] acepta todo el espacio del valor de `xs:boolean` para el encabezado `mustUnderstand` \(0, 1, `false`, `true`\)  
  
#### Errores SOAP  
 A continuación, se muestra una lista de implementaciones de errores de SOAP específicos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] devuelve los códigos de error de SOAP 1.1 siguientes: `s11:mustUnderstand`, `s11:Client` y `s11:Server`.  
  
-   B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] devuelve los códigos de error de SOAP 1.2 siguientes: `s12:MustUnderstand`, `s12:Sender` y `s12:Receiver`.  
  
### Enlace HTTP  
  
#### Enlace HTTP de SOAP 1.1  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa enlace HTTP de SOAP1.1 siguiendo la sección 3.4 de la especificación del Perfil básico 1.1 con las siguientes aclaraciones:  
  
-   B2211: el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no implementa la redirección de solicitudes POST HTTP.  
  
-   B2212: los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admiten cookies HTTP de acuerdo con 3.4.8.  
  
#### Enlace HTTP de SOAP 1.2  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa enlace HTTP de SOAP 1.2 tal y como se describe en la especificación SOAP 1.2\-parte 2 \(SOAP12Part2\) siguientes aclaraciones.  
  
 SOAP 1.2 introdujo un parámetro de acción opcional para el tipo de medio `application/soap+xml`.Este parámetro es útil para optimizar la distribución de mensajes sin requerir que se analice el cuerpo del mensaje SOAP cuando no se utiliza WS\-Addresing.  
  
-   R2221: el parámetro de acción `application/soap+xml`, cuando está presente en una solicitud de SOAP 1.2, debe coincidir con el atributo `soapAction` en el elemento `wsoap12:operation` dentro del enlace de WSDL correspondiente.  
  
-   R2222: el parámetro de acción `application/soap+xml`, cuando está presente en un mensaje de SOAP 1.2, debe coincidir con `wsa:Action` cuando se utiliza WS\-Addressing 2004\/08 o WS\-Addressing 1.0.  
  
 Cuando WS\-Addressing está deshabilitado y una solicitud entrante no contiene ningún parámetro de acción, `Action` del mensaje se considera como no especificada.  
  
## WS\-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa 3 versiones de WS\-Addressing:  
  
-   WS\-Addressing 2004\/08  
  
-   Núcleo de W3C Web Services Addressing 1.0 \(ADDR10\-CORE\) y enlace SOAP \(ADDR10\-SOAP\)  
  
-   WS\-Addressing 1.0 \- Metadatos  
  
### Referencias de extremo  
 Todas las versiones de WS\-Addressing que implementa [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usan referencias de extremo para describir los extremos.  
  
#### Referencias de extremo y WS\-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa varios protocolos de infraestructura que usan ws\-Addressing y en particular el elemento `EndpointReference` y la clase `W3C.WsAddressing.EndpointReferenceType` \(por ejemplo, WS\-ReliableMessaging, WS\-SecureConversation y WS\-Trust\).[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el uso de cualquier versión de WS\-Addressing con otros protocolos de infraestructura.Los extremos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admiten una versión de WS\-Addressing por extremo.  
  
 Para R3111, el espacio de nombres para el elemento `EndpointReference` o el tipo utilizado en mensajes intercambiados con un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe coincidir con la versión de WS\-Addressing implementada por este extremo.  
  
 Por ejemplo, si un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS\-ReliableMessaging, el encabezado `AcksTo` devuelto por este tipo de extremo dentro de `CreateSequenceResponse` utiliza la versión de WS\-Addressing que el elemento `EncodingBinding` especifica para este extremo.  
  
#### Referencias de extremo y metadatos  
 Varios escenarios requieren comunicar metadatos o una referencia a los metadatos para un extremo determinado.  
  
 B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emplea mecanismos descritos en la especificación de WS\-MetadataExchange \(MEX\), sección 6, para incluir metadatos para referencias de extremos por valor o referencia.  
  
 Considere un escenario donde un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere la autenticación utilizando un token de lenguaje de marcado de aserciones de seguridad \(SAML\) emitido por el emisor del token en http:\/\/sts.fabrikam123.com.El extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] describe este requisito de autenticación utilizando la aserción `sp:IssuedToken` con una aserción `sp:Issuer` anidada que señala al emisor del token.Las aplicaciones de cliente que obtienen acceso a la aserción `sp:Issuer` han de saber cómo comunicarse con el extremo del emisor del token.El cliente ha de saber los metadatos sobre el emisor del token.Con las extensiones de metadatos de referencia de extremo definidas en MEX, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una referencia a los metadatos de emisor de token.  
  
```  
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
  
### Encabezados de direccionamiento de mensajes  
  
#### Encabezados de mensajes  
 Para ambas versiones de WS\-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa los siguientes encabezados de mensajes tal y como describen las especificaciones `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID` y `wsa:RelatesTo`.  
  
 B3211: para todas las versiones de WS\-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se ajusta a los encabezados de mensajes WS\-Addressing `wsa:FaultTo` y `wsa:From`, pero no los genera inmediatamente.  
  
 Las aplicaciones que interactúan con las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden agregar estos encabezados de mensajes e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] las procesará consecuentemente.  
  
#### Parámetros de referencia y propiedades  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa el procesamiento de parámetros de referencia de extremo y propiedades de  
  
 referencia de acuerdo con las especificaciones respectivas.  
  
 B3221: cuando se configura para utilizar WS\-Addressing 2004\/08, los extremos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no diferencian entre procesar propiedades de referencia y parámetros de referencia.  
  
### Patrones de intercambio de mensajes  
 La secuencia de mensajes implicada en la invocación de operación de servicios web se conoce como *patrón de intercambio de mensajes*.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite modelos de intercambio de mensajes unidireccional, de solicitud\-respuesta y dúplex.En esta sección se aclaran los requisitos de WS\-Addressing sobre el procesamiento de mensajes en función del patrón de intercambio de mensajes que se utiliza.  
  
 A lo largo de esta sección, el solicitante envía el primer mensaje y el respondedor recibe el primer mensaje.  
  
#### Mensaje unidireccional  
 Cuando un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se configura para admitir mensajes con una `Action` determinada para seguir un modelo unidireccional, el extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sigue los siguientes comportamientos y requisitos.A menos que se especifique lo contrario, los comportamientos y reglas se aplican a ambas versiones de WS\-Addressing admitidas en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   R3311: el solicitante debe incluir `wsa:To`, `wsa:Action` y los encabezados para todos los parámetros de referencia especificados por la referencia del extremo.Cuando se utiliza WS\-Addressing 2004\/08 y la referencia de extremo especifica las \[propiedades de referencia\], los encabezados correspondientes también deben agregarse al mensaje.  
  
-   B3312: el solicitante puede incluir `MessageID`, `ReplyTo`y los encabezados `FaultTo`.La infraestructura del receptor los omitirá y se pasarán a la aplicación.  
  
-   R3313: cuando se utiliza HTTP y no se envía ningún mensaje en la rama de respuesta HTTP, el respondedor debe enviar una respuesta HTTP con un cuerpo vacío y un código de estado HTTP 202.  
  
     Si el transporte HTTP está en uso y el contrato de operación declara un mensaje unidireccional, la respuesta HTTP todavía se puede utilizar para enviar mensajes de infraestructura, por ejemplo, la mensajería de confianza puede enviar un mensaje `SequenceAcknowledgement` en una respuesta HTTP.  
  
-   B3314: el respondedor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no envía un mensaje de error en respuesta a un mensaje unidireccional.  
  
#### Solicitud\-respuesta  
 Cuando un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se configura para un mensaje con una `Action` determinada para seguir el patrón de solicitud\-respuesta, el extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sigue los comportamientos y requisitos descritos abajo.A menos que se especifique lo contrario, los comportamientos y reglas se aplican a ambas versiones de WS\-Addressing admitidas en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   R3321: el solicitante debe incluir en la solicitud `wsa:To`, `wsa:Action`, `wsa:MessageID`, y los encabezados para todos \[parámetros de referencia\] o \[propiedades de referencia\] \(o ambos\) especificados para la referencia de extremo.  
  
-   R3322: cuando se utiliza WS\-Addressing 2004\/08, `ReplyTo` también debe incluirse en la solicitud.  
  
-   R3323: Cuando se utiliza WS\-Addressing 1.0 y `ReplyTo` no se encuentra en la solicitud, se utiliza una referencia de extremo predeterminada con la propiedad \[dirección\] igual a "http:\/\/www.w3.org\/2005\/08\/addressing\/anonymous".  
  
-   R3324: el solicitante debe incluir en la solicitud los encabezados `wsa:To`, `wsa:Action` y `wsa:RelatesTo` en el mensaje de respuesta, así como los encabezados para todos los \[parámetros de referencia\] o \[propiedades de referencia\] \(o ambos\) especificados por la referencia de extremo `ReplyTo` en la solicitud.  
  
### Errores de direccionamiento de servicios Web  
 R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera los siguientes errores definidos por WS\-Addressing 2004\/08.  
  
|Código|Motivo|  
|------------|------------|  
|wsa:DestinationUnreachable|El mensaje llegó con un `ReplyTo` diferente a la dirección de respuesta establecida para este canal; no hay ningún extremo que escuche en la dirección especificada en el encabezado To.|  
|wsa:ActionNotSupported|los canales de infraestructura o el distribuidor asociados al extremo no reconocen la acción especificada en el encabezado `Action`.|  
  
 R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produce los siguientes errores definidos por WS\-Addressing 1.0.  
  
|Código|Motivo|  
|------------|------------|  
|wsa10:InvalidAddressingHeader|`wsa:To`, `wsa:ReplyTo`, `wsa:From` o `wsa:MessageID` duplicado.`wsa:RelatesTo` duplicado con el mismo `RelationshipType`.|  
|wsa10:MessageAddressingHeaderRequired|Falta el encabezado Addressing necesario.|  
|wsa10:DestinationUnreachable|El mensaje llegó con un `ReplyTo` diferente a la dirección de respuesta establecida para este canal.No hay ningún extremo escuchando en la dirección especificada en encabezado To.|  
|wsa10:ActionNotSupported|Los canales de infraestructura o el distribuidor asociados al extremo no reconocen una acción especificada en el encabezado `Action`.|  
|wsa10:EndpointUnavailable|El canal RM devuelve este error, indicando que el extremo no procesará la secuencia basada en el examen de los encabezados de direccionamiento del mensaje `CreateSequence`.|  
  
 El código de las tablas anteriores se asigna a `FaultCode` en SOAP 1.1 y `SubCode` \(con Code\=Sender\) en SOAP 1.2.  
  
### Enlace WSDL 1.1 y aserciones de WS\-Policy  
  
#### Indicación del uso de WS\-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza las aserciones de directivas para indicar la compatibilidad de extremo para una versión particular de WS\-Addressing.  
  
 La siguiente aserción de directiva tiene Asunto de directiva de extremo \[WS PA\] e indica que los mensajes enviados y recibidos desde el extremo deben utilizar WS\-Addressing 2004\/08.  
  
```  
<wsap:UsingAddressing />  
```  
  
 Esta aserción de directiva aumenta la especificación WS\-Addressing 2004\/08.  
  
 La siguiente aserción de directiva indica que los mensajes enviados y recibidos deben usar WS\-Addressing 1.0.  
  
```vb  
<wsam:Addressing/>   
```  
  
 La siguiente aserción de directiva tiene un asunto de directiva de extremo \[WS PA\] e indica que los mensajes enviados y recibidos desde el extremo deben utilizar WS\-Addressing 2004\/08.  
  
```  
<wsaw10:UsingAddressing />  
```  
  
 El elemento `wsaw10:UsingAddressing` se toma prestado de \[WSDL de WS\-Addressing\] y se utiliza en el contexto de WS\-Addressing cumpliendo con esa especificación, sección 3.1.2.  
  
 El uso de direccionamiento no modifica la semántica de WSDL 1.1, SOAP 1.1 y enlaces HTTP SOAP 1.2.Por ejemplo, si una respuesta se espera para una solicitud que se envía a un extremo que usa direccionamiento y enlace HTTP de SOAP 1.x de WSDL, la respuesta se debe enviar utilizando la respuesta HTTP.  
  
 Para las respuestas enviadas a través de la respuesta http, la aserción de WS\-AM es:  
  
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
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una característica mediante la que dos canales de transporte subyacentes pueden formar un canal dúplex compuesto, donde un canal se usa para los mensajes de entrada y el otro, para los de salida.En el caso del transporte HTTP, el Dúplex Compuesto proporciona dos conexiones HTTP inversas.El solicitante utiliza una conexión para enviar mensajes al respondedor y el respondedor usa la otra para devolver mensajes al solicitante.  
  
 Para las respuestas enviadas a través de solicitudes independientes http, la aserción de ws\-am es:  
  
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
  
 El uso de la siguiente aserción que tiene un asunto de extremo de directiva \[WS\-PA\] en los extremos que usan enlaces HTTP de SOAP 1.1x de WDSL 1.1 requiere dos conexiones HTTP inversas independientes que se utilizarán para los mensajes que fluyen del solicitante al respondedor y del respondedor al solicitante, respectivamente.  
  
```  
<cdp:CompositeDuplex/>  
```  
  
 La declaración anterior conduce a los siguientes requisitos en el encabezado `wsa:ReplyTo` para los mensajes de solicitud:  
  
-   R3514: los mensajes de solicitud enviados a un extremo deben tener un encabezado `ReplyTo` con la propiedad `[address]` distinta de "http:\/\/www.w3.org\/2005\/08\/addressing\/anonymous" si el extremo utiliza un enlace HTTP SOAP 1.x de WSDL 1.1 y tiene una alternativa de directivas con una aserción `wsap10:UsingAddressing` o `wsap:UsingAddressing` asociada a la `cdp:CompositeDuplex` adjunta.  
  
-   R3515: los mensajes de solicitud enviados a un extremo deben tener un encabezado `ReplyTo` con la propiedad `[address]` igual a "http:\/\/www.w3.org\/2005\/08\/addressing\/anonymous" o no deben tener un encabezado `ReplyTo`, si el extremo utiliza un enlace HTTP WSDL 1.1 SOAP 1.x y tiene una alternativa de directiva con la aserción `wsap10:UsingAddressing` y ninguna aserción `cdp:CompositeDuplex` adjunta.  
  
-   R3516: los mensajes de solicitud enviados a un extremo han de tener un encabezado `ReplyTo` con una propiedad `[address]` igual a "http:\/\/www.w3.org\/2005\/08\/addressing\/anonymous" si el extremo usa un enlace a HTTP SOAP 1.x de WSDL 1.1 y una alternativa de directivas con una aserción `wsap:UsingAddressing` y ninguna aserción `cdp:CompositeDuplex` adjunta.  
  
 La especificación WSDL de WS\-Addressing intenta describir enlaces de protocolos similares introduciendo un elemento `<wsaw:Anonymous/>` con tres valores textuales \(requerido, opcional y prohibido\) para indicar requisitos en el encabezado `wsa:ReplyTo` \(sección 3.2\).Desafortunadamente, tal definición de elemento no es especialmente utilizable como aserción en el contexto de WS\-Policy, porque requiere extensiones específicas del dominio para admitir la intersección de alternativas usando este tipo de elementos como aserción.Tal definición de elemento también indica el valor del encabezado `ReplyTo` frente al comportamiento del extremo en la conexión, que lo hace específico para el transporte HTTP.  
  
#### Definición de acción  
 WS\-Addressing 2004\/08 define un atributo `wsa:Action` para los elementos`wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`.El enlace ESDL de WS\-Addressing 1.0 \(WS\-ADDR10\-WSDL\) define un atributo similar, `wsaw10:Action`.  
  
 La única diferencia entre los dos es la semántica de patrón de Acción predeterminada descrita en la sección 3.3.2 de WS\-ADDR y la sección 4.4.4 de WS\-ADDR10\-WSDL, respectivamente.  
  
 Es razonable tener dos extremos que compartan el mismo `portType` \(o contrato, en terminología [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \) pero que usen diferentes versiones de WS\-Addressing.Pero suponiendo que esa acción esté definida por `portType` y no debería cambiar a lo largo de los extremos que implementan `portType`, se hace imposible admitir ambos patrones de acción predeterminados.  
  
 Para resolver esta controversia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite una versión única del atributo `Action`.  
  
 B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el atributo `wsaw10:Action` en elementos `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` tal y como se define en WS\-ADDR10\-WSDL para determinar el URI `Action` para los mensajes correspondientes independientemente de la versión de WS\-Addressing utilizada por el extremo.  
  
#### Uso de la referencia de extremo dentro del puerto WSDL  
 La sección 4.1 de WS\-ADDR10\-WSDL extiende el elemento `wsdl:port` para incluir el elemento secundario `<wsa10:EndpointReference…/>` para describir el extremo en términos de WS\-Addressing.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expande esta utilidad en WS\-Addressing 2004\/08, permitiendo que `<wsa:EndpointReference…/>` aparezca como un elemento secundario de `wsdl:port`.  
  
-   R3531: si un extremo tiene una directiva alternativa adjunta con una aserción de directiva `<wsaw10:UsingAddressing/>``wsdl:port, el elemento` `<wsa10:EndpointReference …/> correspondiente puede contener un elemento secundario` .  
  
-   R3532: si un `wsdl:port` contiene un elemento secundario `<wsa10:EndpointReference …/>``wsa10:EndpointReference/wsa10:Address, el valor del elemento secundario` `@address debe coincidir con el valor del atributo` `wsdl:port del elemento` `wsdl:location/` del mismo nivel.  
  
-   R3533: si un extremo tiene una directiva alternativa adjunta con una aserción de directiva `<wsap:UsingAddressing/>``wsdl:port, el elemento` `<wsa:EndpointReference …/> correspondiente puede contener un elemento secundario` .  
  
-   R3534: si un `wsdl:port` contiene un elemento secundario `<wsa:EndpointReference …/>``wsa:EndpointReference/wsa:Address, el valor del elemento secundario` `@address debe coincidir con el valor del atributo` `wsdl:port del elemento` `wsdl:location/` del mismo nivel.  
  
### Composición con WS\-Security  
 Según las secciones de consideración de seguridad en WS\-ADDR y WS\-ADDR10, se recomienda que todos los encabezados de mensajes de direccionamiento se firmen junto con el cuerpo del mensaje para enlazarlos juntos.  
  
 Cuando WS\-Security se utiliza para la protección de la integridad de mensajes, los encabezados de mensajes WS\-Addressing, así como los encabezados resultantes de parámetros o propiedades de referencia \(o ambos\) se deben firmar junto con el cuerpo del mensaje.  
  
### Ejemplos  
  
#### Mensaje unidireccional  
 En este escenario, el remitente envía un mensaje unidireccional al receptor.Se usan SOAP 1.2, HTTP 1.1 y WS\-Addressing de W3C 1.0.  
  
 La estructura del mensaje de solicitud: los encabezados del mensaje incluyen elementos `wsa10:To` y `wsa10:Action`.El cuerpo del mensaje incluye un elemento `<app:Ping>` concreto del espacio de nombres de la aplicación.  
  
 Encabezados HTTP: el destino en POST coincide con el URI en el elemento `wsa10:To` .  
  
 El encabezado Content\-Type tiene el valor de `application/soap+xml` que requiere SOAP 1.2.Se incluyen los parámetros `charset` y `action`.El parámetro `action` del encabezado Content\-Type coincide con el valor del encabezado `wsa10:Action` del mensaje.  
  
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
  
 El receptor responde con una respuesta HTTP vacía y el estado 202.Un ejemplo de la respuesta HTTP:  
  
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
  
## Mecanismo de optimización de transmisión de mensajes SOAP  
 En esta sección se describen los detalles de implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el MTOM de SOAP HTTP.La tecnología de MTOM es un mecanismo de codificación de mensajes de la misma clase que la codificación de XML\/texto tradicional o la codificación binaria de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].MTOM incluye lo siguiente:  
  
-   Una codificación de XML y un mecanismo de empaquetado descritos por \[XOP\] que optimiza elementos de información XML que contienen datos binarios codificados por base64 en partes binarias independientes.  
  
-   Una encapsulación MIME del paquete de XOP que serializa el conjunto de información XML y cada parte binaria del paquete de XOP en una parte MIME independiente.  
  
-   Una codificación XOP MIME aplicada a la envoltura de SOAP 1.x.  
  
-   Un enlace de transporte HTTP.  
  
 Es posible utilizar MTOM con transportes que no sean HTTP mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Sin embargo, en este tema nos centraremos en HTTP.  
  
 El formato MTOM reutiliza un largo conjunto de especificaciones que cubren el propio MTOM, XOP y MIME.La modularidad de este conjunto de especificaciones hace algo difícil reconstruir requisitos exactos en la semántica de procesamiento y formato.En esta sección se describe los requisitos de procesamiento y formato para enlace MTOM.  
  
### Codificación de mensajes MTOM  
  
#### Generación de mensajes MTOM  
 La sección 3.1 de \[XOP\] describe el proceso de codificación de XML con elementos de información de elementos que contienen los valores de base64 en un paquete XOP definido de manera abstracta.  
  
 La siguiente secuencia de pasos describe el proceso de codificación específico del MTOM:  
  
1.  Asegúrese de que la envoltura de SOAP que se va a codificar no contiene ningún elemento de información de elemento con un `[namespace name]` "http:\/\/www.w3.org\/2004\/08\/xop\/include" y un `[local name]``Include`.  
  
2.  Cree un paquete MIME vacío.  
  
3.  Identifique los elementos de información que se van a optimizar dentro del conjunto de información XML original.Para los elementos que se van a optimizar, los caracteres que constituyen el `[children]` del elemento de información del elemento deben tener la forma canónica de `xs:base64Binary` \(véase XSD\-2, 3.2.16 base64Binary\) y no deben contener espacios en blanco delante del contenido sin espacios en blanco, alineados con él o después de él.  
  
4.  Cree una envoltura SOAP de XOP que sea una copia de la envoltura SOAP original, pero con los elementos secundarios de cada elemento de información de elemento identificados en el paso anterior reemplazados por un elemento de información de elemento `xop:Include` construido de la siguiente manera:  
  
    1.  Transforme los caracteres reemplazados en datos binarios procesándolos como datos codificados en base64.  
  
    2.  Genere un valor del encabezado Content\-ID único que cumpla los requisitos R3133 y R3134.  
  
    3.  Genere un encabezado MIME de codificación de transferencia del contenido con el valor binario.  
  
    4.  Si el elemento de información de elemento que se optimiza \(el \[primario\] del elemento de información de elemento recientemente insertado `xop:Include`\) tiene un elemento de información de atributos `xmime:contentType`, genere un encabezado MIME de tipo de contenido con el valor del atributo `xmime:contentType`.  
  
    5.  Genere una nueva parte MIME binaria con contenido formado por datos binarios descodificados a partir de los caracteres reemplazados procesados como base64, encabezado del Content\-ID de 4b, encabezado de codificación de transferencia de contenido de 4c, encabezado de tipo de contenido si se generó en el paso 4d.  
  
    6.  Agregue un atributo `href` al elemento `xop:Include` con el valor cid: uri derivado del valor del encabezado Content\-ID generado en el paso 4b.Elimine los caracteres “\<” y “\>” envolventes, agregue caracteres de escape de URL a la cadena restante y agregue el prefijo `cid:`.El juego de caracteres mínimo siguiente se exige para que RFC1738 y RFC2396 puedan escapar.Se pueden escapar otros caracteres.  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  Cree una parte MIME de raíz con la envoltura SOAP de XOP a partir del paso 4.  
  
6.  Escriba los encabezados HTTP, incluido de tipo de contenido HTTP.  
  
7.  Escriba el paquete MIME.  
  
#### Procesamiento de mensajes MTOM  
 Procesar un mensaje MTOM es justo lo contrario al proceso descrito en la sección “Generación de mensajes MTOM":  
  
1.  Asegúrese de que la parte MIME de la raíz tiene el tipo de contenido `application/xop+xml`.  
  
2.  Construya una envoltura SOAP analizando la parte MIME de la raíz del paquete como un documento XML.El parámetro `charset` del tipo de contenido de la parte MIME de la raíz determina la codificación de caracteres.  
  
3.  Para cada elemento de información de elemento en la envoltura SOAP construida, que tiene, como único miembro de su propiedad \[elemento secundario\], un elemento de información de elemento `xop:Include`:  
  
    1.  Elimine el prefijo `cid:` y quite los caracteres de escape de todas las secuencias de escape de URI \(RFC 2396\) en el valor del atributo `@href` del elemento `xop:Include`.Encierre la cadena del resultado entre "\<" y "\>".  
  
    2.  Busque la parte MIME con el valor del encabezado de identificador de contenido que coincida con la cadena derivada en el paso 3a.  
  
    3.  Reemplace el elemento de información de elemento `xop:Include` que aparece en la propiedad `children` de cada elemento con los elementos de información de caracteres que representan la codificación de base64 canónica \(vea XSD\-2, 3.2.16 base64Binary\) del cuerpo de la entidad de la parte MIME identificada en el paso 3b \(reemplace de manera eficaz el elemento de información de elemento `xop:Include` con los datos reconstruidos a partir de la parte del paquete\).  
  
#### Encabezado de tipo de contenido HTTP  
 La siguiente es una lista de aclaraciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el formato del encabezado de tipo de contenido HTTP de un mensaje codificado en MTOM SOAP 1.x derivado a partir de los requisitos enunciados en la propia especificación MTOM y se derivan de MTOM y RFC 2387.  
  
-   R4131: un encabezado de tipo de contenido HTTP debe tener el valor de multiparte\/relacionado \(sin distinción entre mayúsculas y minúsculas\) y sus parámetros.Los nombres de parámetros no distinguen mayúsculas de minúsculas.El orden de los parámetros no importa.  
  
-   Se enumera la forma de Backus\-Naur completa \(BNF\) del encabezado de tipo de contenido para los mensajes MIME en RFC 2045, sección 5.1.  
  
-   R4132: un encabezado HTTP Content\-Type debe tener un parámetro de tipo con el valor `application/xop+xml` encerrado entre comillas tipográficas.  
  
 Aunque el requisito de utilizar las comillas tipográficas no está explícito en RFC 2387, el texto observa que todos los parámetros de tipo de medio de multiparte\/relacionado probablemente contienen caracteres reservados como "@" o "\/" y, por consiguiente, requieren las comillas tipográficas.  
  
-   R4133: un encabezado de tipo de contenido HTTP debe tener un parámetro de inicio con el valor del encabezado de identificador de contenido de la parte MIME que contiene el sobre de SOAP 1.x, que va entre comillas tipográficas.Si se omite el parámetro de inicio, la primera parte MIME debe contener la envoltura de SOAP 1.x.  
  
-   R4134: un encabezado de tipo de contenido HTTP para un mensaje codificado de MTOM de SOAP 1.1 debe incluir el parámetro de información de inicio con el valor de texto\/xml, encerrado entre comillas tipográficas.  
  
-   R4135: un encabezado de tipo de contenido HTTP para un mensaje codificado en MTOM de SOAP 1.2 debe incluir el parámetro de información de inicio con el valor de `application/soap+xml`, encerrado entre comillas tipográficas.  
  
-   R4136: encabezado de tipo de contenido HTTP para un mensaje codificado en MTOM de SOAP 1.x debe tener el parámetro de límite con el valor \(encerrado entre comillas tipográficas\) que coincide con el BNF limitador de MIME definido en RFC 2046, sección 5.1.1  
  
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
  
#### Parte del conjunto de información de MIME  
 La envoltura de SOAP 1.x se encapsula como una parte de la raíz del paquete de MIME XOP y se llama a menudo la parte `infoset`.  
  
-   R4141: la envoltura de SOAP 1.x se debe encapsular como una parte de la raíz del paquete de XOP MIME, llamada la parte `infoset` y a la que se hace referencia a partir del tipo de contenido HTTP.  
  
-   R4142: la parte de SOAP `Infoset` debe incluir los siguientes encabezados MIME: `Content-ID`, `Content-Transfer-Encoding`y `Content-Type`.  
  
 RFC 2045 define el formato del encabezado del id. de contenido como  
  
```  
"Content-ID" ":" msg-id  
```  
  
 donde `msg-id` está definido en RFC 2822 \(que reemplaza a RFC 822, al que se hace referencia en RFC 2045\) como:  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 y es efectivamente una dirección de correo electrónico encerrada entre "\<" y "\>".El prefijo y sufijo `[CFWS]` se agregaron en RFC 2822 para incluir comentarios y no deben usarse para conservar la interoperabilidad.  
  
 R4143: el valor del encabezado Content\-ID para la parte MIME del conjunto de información debe seguir la producción `msg-id` de RFC 2822 con las partes de prefijo y sufijo `[CFWS]` omitidas.  
  
 Varias implementaciones MIME redujeron los requisitos para el valor encerrado entre "\<" y "\>" para que fuese una dirección de correo electrónico y usaron `absoluteURI` encerrado entre “\<” , “\> además de la dirección de correo electrónico.Esta versión de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa valores de encabezado MIME del identificador de contenido con el formato:  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 R4144: los procesadores MTOM deberían aceptar valores de encabezado de id. de contenido que coincidan con el siguiente `msg-id` relajado.  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 MIME \(RFC 2045\) proporciona el encabezado de codificación de transferencia de contenido para comunicar la codificación del contenido de la parte MIME.El valor predeterminado definido para la codificación de transferencia de contenido es 7 bits, que no es apto para la mayoría de mensajes SOAP, por lo que el encabezado de codificación de transferencia de contenido se necesita para una mayor interoperabilidad:  
  
-   R4145: la parte del conjunto de información de SOAP debe contener el encabezado de codificación de transferencia de contenido.  
  
-   R4146: si la codificación de caracteres de la envoltura SOAP es UTF\-8, el valor del encabezado de codificación de transferencia de contenido debe ser de 8 bits.  
  
-   R4147: si la codificación de caracteres de la envoltura SOAP es UTF\-16, el valor del encabezado de codificación de transferencia de contenido debe ser binaria.  
  
-   Según la sección 5 de \[XOP\],  
  
-   R4148: la parte del conjunto de información debe contener encabezado de tipo de contenido con aplicación de tipos de medio\/xop\+xml y tipo de parámetros "texto\/xml" y juego de caracteres  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   R4149: la parte del conjunto de información de SOAP 1.2 debe contener el encabezado de tipo de contenido con el tipo de medio `application/xop+xml` y los parámetros type\="`application/soap+xml`" y `charset`.  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     Aunque XOP defina el parámetro `charset` para `application/xop+xml` como opcional, se necesita para una interoperabilidad similar a la del requisito BP 1.1 del parámetro `charset` para el tipo de medio `text/xml`.  
  
-   R41410: los parámetros `charset` y `type` deben estar presentes en el encabezado de tipo de contenido de la parte del conjunto de información de SOAP 1.x.  
  
#### Compatibilidad de extremo WCF para MTOM.  
 El propósito de MTOM es codificar un mensaje SOAP para optimizar los datos codificados en base64.A continuación se muestra una lista de restricciones:  
  
-   R4151: se puede optimizar cualquier elemento de información de elemento que contenga datos codificados en base64.  
  
-   B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] optimiza los elementos de información de elemento que contienen los datos codificados en base64 y superan los 1.024 bytes de longitud.  
  
 Un extremo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurado para utilizar MTOM siempre enviará los mensajes codificados por MTOM.Incluso cuando ninguna parte cumpla los criterios necesarios, el mensaje seguirá estando codificado por MTOM \(serializado como un paquete MIME con una parte MIME única que contiene la envoltura SOAP\).  
  
### Aserción de la WS\-Policy para MTOM  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la siguiente aserción de directivas para indicar el uso de MTOM por extremo:  
  
```  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   R4211: la aserción de directiva anterior tiene un asunto de directiva de extremo y especifica que todos los mensajes enviados a y recibidos desde el extremo se deben optimizar utilizando MTOM.  
  
-   B4212: cuando se configura para utilizar la optimización de MTOM, un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] agrega una aserción de directiva MTOM a la directiva adjunta al `wsdl:binding` correspondiente.  
  
### Composición con WS\-Security  
 MTOM es un mecanismo de codificación similar a `text/xml` y al XML binario de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].MTOM proporciona una composición natural con WS\-Security y otros protocolos WS \- \*: un mensaje protegido mediante WS\-Security puede optimizarse mediante MTOM.  
  
### Ejemplos  
  
#### Mensaje de SOAP 1.1 WCF codificado mediante MTOM  
  
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
  
#### Mensaje de SOAP 1.2 WCF codificado mediante MTOM  
 En este ejemplo, un mensaje se codifica utilizando MTOM y SOAP 1.2 que está protegido mediante WS\-Security.Las partes binarias identificadas para su codificación son el contenido de `BinarySecurityToken`, `CipherValue` de los `EncryptedData` que corresponden a la firma y al cuerpo cifrados.Observe que el `CipherValue` de la `EncryptedKey` no se identificó para la optimización mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], porque su longitud es inferior a 1.024 bytes.  
  
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