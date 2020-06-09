---
title: Divulgación de información
ms.date: 03/30/2017
ms.assetid: 4064c89f-afa6-444a-aa7e-807ef072131c
ms.openlocfilehash: a58ac4dd3715052031c7fb5c1da480c0d01396ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596869"
---
# <a name="information-disclosure"></a>Divulgación de información

La divulgación de información permite a un atacante ganar valiosa información sobre un sistema. Por consiguiente, siempre considere qué información divulga y si un usuario malintencionado puede utilizarla. A continuación se muestra una lista de los posibles ataques de divulgación de información y proporciona métodos paliativos para cada uno de ellos.

## <a name="message-security-and-http"></a>Seguridad de mensajes y HTTP

Si utiliza la seguridad del nivel de mensaje sobre una capa de transporte HTTP, sea consciente de que la seguridad del nivel de mensaje no protege los encabezados HTTP. La única manera de proteger los encabezados HTTP consiste en utilizar transporte HTTPS en lugar de HTTP. El transporte HTTPS hace que se cifre el mensaje completo, incluidos los encabezados HTTP, mediante el protocolo Secure Sockets Layer (SSL).

## <a name="policy-information"></a>Información de directiva

Es importante proteger la directiva, sobre todo en escenarios de federación donde confidenciales requisitos de tokens emitidos o información sobre el emisor del token se exponen en la directiva. En estos casos, la recomendación es proteger el punto de conexión de la directiva del servicio federado para evitar que los atacantes obtengan información sobre el servicio, como el tipo de demandas que colocar en el token emitido o redirigir a los clientes a emisores de tokens malintencionados. Por ejemplo, un atacante podría detectar pares de nombre de usuario/contraseña reconfigurando la cadena de confianza federada para finalizar en un emisor que ejecutó un ataque de tipo “man-in-the-middle”. También se recomienda que los clientes federados que obtienen sus enlaces a través de la recuperación de directivas comprueben que confían en los emisores en la cadena de confianza federada obtenida. Para obtener más información sobre los escenarios de Federación, vea [Federación](federation.md).

## <a name="memory-dumps-can-reveal-claim-information"></a>Los volcados de memoria pueden revelar información de la demanda

Cuando se produce un error en una aplicación, los archivos de registro, como los generados por Dr. Watson, puede contener información de la demanda. Esta información no se debería exportar a otras entidades, como equipos de compatibilidad; de lo contrario, se exporta también la información de la demanda que contiene los datos privados. Esto se puede paliar si no se envían los archivos de registro a entidades desconocidas.

## <a name="endpoint-addresses"></a>Direcciones de extremo

Una dirección de punto de conexión contiene la información necesaria para comunicarse con un punto de conexión. La seguridad de SOAP debe incluir la dirección completa en los mensajes de negociación de seguridad que se intercambian para negociar una clave simétrica entre un cliente y un servidor. Dado que la negociación de seguridad es un proceso previo al arranque, los encabezados de dirección no se pueden cifrar durante este proceso. Por consiguiente, la dirección no debería contener datos confidenciales; de lo contrario, conduce a ataques de divulgación de la información.

## <a name="certificates-transferred-unencrypted"></a>Certificados transferidos sin cifrar

Al utilizar un certificado X.509 para autenticar un cliente, el certificado se transfiere de manera abierta, dentro del encabezado SOAP. Considere esto como una divulgación potencial de la información de identificación personal (PII). Éste no es un problema para el modo `TransportWithMessageCredential`, donde se cifra el mensaje completo con seguridad de nivel de transporte.

## <a name="service-references"></a>Referencias del servicio

Una referencia de servicio es una referencia a otro servicio. Por ejemplo, un servicio puede pasar una referencia de servicio a un cliente en el curso de una operación. La referencia de servicio también se usa con un *Comprobador de identidad de confianza*, un componente interno que garantiza la identidad de la entidad de seguridad de destino antes de revelar información como datos de aplicación o credenciales al destino. Si la identidad de confianza remota no se puede comprobar o es incorrecta, el remitente debería garantizar que no se divulgó ningún dato que se podría poner en peligro a la aplicación o el usuario.

Entre las mitigaciones se encuentran las siguientes:

- Se supone que las referencias de servicio son de confianza. Tenga cuidado al transferir instancias de referencias de servicio para asegurarse de que no se han manipulado.

- Algunas aplicaciones pueden mostrar una experiencia de usuario que permite el establecimiento interactivo de confianza según los datos de la referencia de servicio y los datos de confianza demostrados por el host remoto. WCF proporciona puntos de extensibilidad para este tipo de instalaciones, pero el usuario debe implementarlas.

## <a name="ntlm"></a>NTLM

De manera predeterminada, en el entorno de dominio de Windows, la autenticación de Windows utiliza el protocolo Kerberos para autenticar y autorizar a los usuarios. Si el protocolo Kerberos no se puede utilizar por alguna razón, NT LAN Manager (NTLM) se utiliza a modo de reserva. Este comportamiento se puede deshabilitar estableciendo la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> en `false`. Entre los problemas que se deben tener en cuenta al permitir NTLM se incluyen:

- NTLM expone el nombre de usuario del cliente. Si es necesario mantener el nombre de usuario  forma confidencial, establezca la propiedad `AllowNTLM` del enlace en `false`.

- NTLM no proporciona autenticación de servidor. Por consiguiente, el cliente no puede asegurar que se esté comunicando con el servicio adecuado al utilizar NTLM como protocolo de autenticación.

### <a name="specifying-client-credentials-or-invalid-identity-forces-ntlm-usage"></a>Especificar credenciales de cliente o una identidad no válida fuerza el uso de NTLM

Al crear un cliente, especificar las credenciales del cliente sin un nombre de dominio o especificar una identidad de servidor no válida, hace que NTLM sea utilizado en lugar del protocolo Kerberos (si la propiedad `AllowNtlm` está establecida en `true`). Dado que NTLM no hace la autenticación de servidor, se puede divulgar información de manera potencial.

Por ejemplo, es posible especificar credenciales de cliente de Windows sin un nombre de dominio, tal y como se muestra en el siguiente código de Visual C#.

```csharp
MyChannelFactory.Credentials.Windows.ClientCredential = new System.Net.NetworkCredential("username", "password");
```

El código no especifica un nombre de dominio y, por consiguiente, se utilizará NTLM.

Si se especifica el dominio, pero se especifica un nombre principal de servicio no válido mediante la característica de identidad de punto de conexión, se usará NTLM. Para obtener más información sobre cómo se especifica la identidad del punto de conexión, consulte [identidad del servicio y autenticación](service-identity-and-authentication.md).

## <a name="see-also"></a>Vea también

- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Elevación de privilegios](elevation-of-privilege.md)
- [Denegación de servicio](denial-of-service.md)
- [Alteración de datos](tampering.md)
- [Escenarios no admitidos](unsupported-scenarios.md)
- [Ataques por repetición](replay-attacks.md)
