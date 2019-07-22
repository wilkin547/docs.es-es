---
ms.openlocfilehash: d75eff2d2a43ab4488577014ec43a9826b2b2924
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237855"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Se quita Ssl3 de TransportDefaults de WCF

|   |   |
|---|---|
|Detalles|Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, el protocolo SSL 3 ya no es el protocolo predeterminado para negociar una conexión segura. En la mayoría de los casos no debería afectar a las aplicaciones existentes, porque TLS 1.0 siempre se ha incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS1.0.|
|Sugerencia|Si se requiere Ssl3, use uno de los mecanismos de configuración siguientes para agregarlo a la lista de protocolos negociados.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[sección &lt;sslStreamSecurity&gt; de &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
