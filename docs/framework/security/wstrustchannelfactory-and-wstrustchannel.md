---
title: WSTrustChannelFactory y WSTrustChannel
ms.date: 03/30/2017
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
author: BrucePerlerMS
ms.openlocfilehash: d129775137759cf7f006ce6501279978f4ab2595
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633171"
---
# <a name="wstrustchannelfactory-and-wstrustchannel"></a>WSTrustChannelFactory y WSTrustChannel
Si ya está familiarizado con Windows Communication Foundation (WCF), sabe que un cliente WCF ya reconoce la federación. Al configurar un cliente WCF con <xref:System.ServiceModel.WSFederationHttpBinding> o un enlace personalizado similar, puede habilitar la autenticación federada en un servicio.

 WCF obtiene el token emitido por el servicio de token de seguridad (STS) en segundo plano y utiliza este token para autenticar en el servicio. La limitación principal de este enfoque es que no hay visibilidad en las comunicaciones del cliente con el servidor. WCF genera automáticamente el token de seguridad de solicitud (RST) para el STS en función de los parámetros de token emitidos en el enlace. Esto significa que el cliente no puede cambiar los parámetros de RST por solicitud, inspeccionar la respuesta de token de seguridad de solicitud (RSTR) para obtener información como notificaciones de presentación ni almacenar en la memoria caché el token para su uso futuro.

 En la actualidad, el cliente WCF es adecuado para escenarios de federación básicos. Sin embargo, uno de los escenarios principales que Windows Identity Foundation (WIF) admite requiere el control sobre el RST en un nivel que WCF no permite con facilidad. Por consiguiente, WIF agrega características que ofrecen un mayor control sobre la comunicación con el STS.

 WIF admite los escenarios de federación siguientes:

- Mediante un cliente WCF sin dependencias de WIF para autenticar en un servicio federado

- Habilitando WIF en un cliente WCF para insertar un elemento ActAs u OnBehalfOf en el RST para el STS

- Mediante WIF solo para obtener un token del STS y habilitar a continuación un cliente WCF para autenticar con este token. Para más información, vea el ejemplo [ClaimsAwareWebService](https://go.microsoft.com/fwlink/?LinkID=248406).

 El primer escenario no necesita explicación: Los clientes WCF existentes seguirán funcionando con confianza de WIF y STS. En este tema se describen los dos escenarios restantes.

## <a name="enhancing-an-existing-wcf-client-with-actas--onbehalfof"></a>Mejorar un cliente de WCF existente con ActAs/OnBehalfOf
En un escenario de delegación de identidad típico, un cliente llama a un servicio de nivel intermedio, que a su vez llama a un servicio back-end. El servicio de nivel intermedio actúa como el cliente o en su nombre.

> [!TIP]
> ¿Cuál es la diferencia entre ActAs y OnBehalfOf?
>
> Desde el punto de vista del protocolo WS-Trust:
>
> 1. Un elemento RST ActAs indica que el solicitante desea un token que contiene notificaciones acerca de dos entidades distintas: el solicitante y una entidad externa representada por el token en el elemento ActAs.
> 2. Un elemento RST OnBehalfOf indica que el solicitante desea un token que contenga notificaciones solo acerca de una entidad: la entidad externa representada por el token en el elemento OnBehalfOf.
>
> La característica ActAs se usa normalmente en escenarios que requieren delegación compuesta, donde el destinatario final del token emitido puede inspeccionar la cadena de delegación completa y ver no solo al cliente sino también a todos los intermediarios. Esto permite realizar el control de acceso, la auditoría y otras actividades relacionadas basadas en la cadena de delegación de identidad completa. La característica ActAs se utiliza normalmente en sistemas de varios niveles para autenticar y pasar información acerca de identidades entre los niveles sin tener que pasar esta información en la capa de lógica de negocios o aplicación.
>
> La característica OnBehalfOf se utiliza en escenarios donde solo es importante la identidad del cliente original y es en la práctica igual que la característica de suplantación de identidad disponible en Windows. Cuando se utiliza OnBehalfOf, el destinatario final del token emitido solo puede ver notificaciones acerca del cliente original y no se conserva la información sobre los intermediarios. Un patrón común donde se utiliza la característica OnBehalfOf es el patrón de proxy donde el cliente no puede tener acceso al STS directamente, sino que se comunica en su lugar a través de una puerta de enlace de proxy. La puerta de enlace de proxy autentica al llamador y coloca la información sobre el llamador en el elemento OnBehalfOf del mensaje de RST que envía a continuación al STS real para su procesamiento. El token resultante contiene solo las notificaciones relacionadas con el cliente del proxy, lo que hace que el proxy sea completamente transparente para el receptor del token emitido. Tenga en cuenta que WIF no admite \<wsse:SecurityTokenReference> ni \<wsa:EndpointReferences> como elemento secundario de \<wst:OnBehalfOf>. La especificación WS-Trust permite tres maneras de identificar el solicitante original (en nombre del cual está actuando el proxy). Estos son:
>
> - Referencia del token de seguridad. Una referencia a un token, en el mensaje, o posiblemente recuperado fuera de banda.
> - Referencia de punto de conexión. Se utiliza como clave para buscar datos, de nuevo fuera de banda.
> - Token de seguridad. Identifica el solicitante original directamente.
>
> WIF solo admite tokens de seguridad, cifrados o no cifrados, como elemento secundario directo de \<wst:OnBehalfOf>.

 Esta información se ofrece a un emisor de WS-Trust mediante los elementos de token ActAs y OnBehalfOf en el RST.

 WCF expone un punto de extensibilidad en el enlace que permite que los elementos XML arbitrarios se agreguen al RST. Sin embargo, dado que el punto de extensibilidad está asociado al enlace, los escenarios que requieren que el contenido de RST varíe en cada llamada deben volver a crear el cliente para cada llamada, lo que disminuye el rendimiento. WIF utiliza métodos de extensión de la clase `ChannelFactory` para permitir que los desarrolladores adjunten cualquier token que se obtiene fuera de banda al RST. En el ejemplo de código siguiente se muestra cómo utilizar un token que representa al cliente (como un X.509, un nombre de usuario o un token del lenguaje de marcado de aserción de seguridad (SAML)) y adjuntarlo al RST que se envía al emisor.

```csharp
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>(clientSamlToken);
serviceChannel.Hello("Hi!");
```

 WIF proporciona las siguientes ventajas:

- El RST se puede modificar por canal; por consiguiente, los servicios de nivel medio no tienen que volver a crear el generador de canales para cada cliente, lo que mejora el rendimiento.

- Esto funciona con los clientes WCF existentes, lo que hace posible una ruta de acceso de actualización sencilla para los servicios de nivel medio de WCF existentes que desean habilitar la semántica de delegación de identidad.

 Sin embargo, todavía no hay visibilidad en la comunicación del cliente con el STS. Examinaremos esto en el tercer escenario.

## <a name="communicating-directly-with-an-issuer-and-using-the-issued-token-to-authenticate"></a>Comunicación directa con un emisor y uso del token emitido para autenticar
Para algunos escenarios avanzados, la mejora de un cliente WCF no es suficiente. Los desarrolladores que solo usan WCF suelen utilizar contratos de entrada y salida de mensajes y controlan el análisis del cliente de la respuesta del emisor de manera manual.

WIF presenta las clases <xref:System.ServiceModel.Security.WSTrustChannelFactory> y <xref:System.ServiceModel.Security.WSTrustChannel> para permitir al cliente comunicarse directamente con un emisor de WS-Trust. Las clases <xref:System.ServiceModel.Security.WSTrustChannelFactory> y <xref:System.ServiceModel.Security.WSTrustChannel> permiten a los objetos RSTR y RST fuertemente tipados fluir entre el cliente y el emisor, como se muestra en el siguiente ejemplo de código.

```csharp
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory(stsBinding, stsAddress);
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);
rst.AppliesTo = new EndpointAddress(serviceAddress);
RequestSecurityTokenResponse rstr = null;
SecurityToken token = channel.Issue(rst, out rstr);
```

Observe que el parámetro `out` del método <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> permite el acceso al RSTR para la inspección del cliente.

Hasta ahora, solo ha visto cómo obtener un token. El token que se devuelve del objeto <xref:System.ServiceModel.Security.WSTrustChannel> es un `GenericXmlSecurityToken` que contiene toda la información necesaria para la autenticación en un usuario de confianza. En el ejemplo de código siguiente se muestra la forma de utilizar este token.

```csharp
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token );
serviceChannel.Hello("Hi!");
```

El método de extensión <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> del objeto `ChannelFactory` indica a WIF que ha obtenido un token fuera de banda y que debe detener la llamada de WCF normal al emisor y utilizar en su lugar el token que obtuvo para autenticar al usuario de confianza. Esto tiene las ventajas siguientes:

- Proporciona control completo sobre el proceso de emisión de tokens.

- Admite escenarios de ActAs/OnBehalfOf estableciendo directamente estas propiedades en el RST de salida.

- Permite tomar decisiones de confianza dinámicas en el cliente en función del contenido de RSTR.

- Permite almacenar en la memoria caché y reutilizar el token que se devuelve del método <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A>.

- <xref:System.ServiceModel.Security.WSTrustChannelFactory> y <xref:System.ServiceModel.Security.WSTrustChannel> permiten controlar la semántica de almacenamiento en caché del canal, errores y recuperación según los procedimientos recomendados de WCF.

## <a name="see-also"></a>Vea también

- [Características de WIF](../../../docs/framework/security/wif-features.md)
