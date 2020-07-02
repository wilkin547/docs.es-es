---
ms.openlocfilehash: fb9436ec9e525afb497033775e34b6b636ced22d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621443"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a>Servicios de WCF que usan NETTCP con seguridad SSL y autenticación de certificados MD5

#### <a name="details"></a>Detalles

.NET Framework 4.6 añade TLS 1.1 y TLS 1.2 a la lista de protocolos predeterminados de SSL de WCF. Cuando los equipos cliente y servidor tienen .NET Framework 4.6 o una versión posterior instalada, se usa TLS 1.2 para la negociación. TLS 1.2 no admite la autenticación de certificados MD5. Como consecuencia, si un cliente utiliza un certificado MD5, el cliente de WCF no se podrá conectar al servicio WCF.

#### <a name="suggestion"></a>Sugerencia

Puede evitar este problema para que el cliente WCF pueda conectarse a un servidor WCF realizando alguno de los siguientes procedimientos:

- Actualizar el certificado para que no use el algoritmo MD5. Esta es la solución recomendada.
- Si la vinculación no se configura dinámicamente en el código fuente, actualice el archivo de configuración de la aplicación para usar TLS 1.1 o una versión anterior del protocolo. Esto le permite seguir usando un certificado con el algoritmo hash MD5.

> [!WARNING]
> Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.

El archivo de configuración siguiente realiza esta tarea:

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- Si la vinculación se configura dinámicamente en el código fuente, actualice la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> para usar TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versión anterior del protocolo en el código fuente.

> [!WARNING]
> Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.

| NOMBRE    | Valor   |
|:--------|:--------|
| Ámbito   | Secundaria   |
| Versión | 4.6     |
| Tipo    | Tiempo de ejecución |
