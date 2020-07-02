---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621382"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Se quita Ssl3 de TransportDefaults de WCF

#### <a name="details"></a>Detalles

Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, el protocolo SSL 3 ya no es el protocolo predeterminado para negociar una conexión segura. En la mayoría de los casos no debería afectar a las aplicaciones existentes, porque TLS 1.0 siempre se ha incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS1.0.

#### <a name="suggestion"></a>Sugerencia

Si se requiere Ssl3, use uno de los mecanismos de configuración siguientes para agregarlo a la lista de protocolos negociados.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[sección &lt;sslStreamSecurity&gt; de &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
