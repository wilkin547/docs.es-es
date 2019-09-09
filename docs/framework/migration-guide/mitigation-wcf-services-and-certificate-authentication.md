---
title: 'Mitigación: Servicios WCF y autenticación de certificados'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fcb4de714c8a0f1f2c61f3a12815a5a0a3ddc83
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70789825"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a>Mitigación: Servicios WCF y autenticación de certificados

.NET Framework 4.6 agrega TLS 1.1 y TLS 1.2 a la lista predeterminada de protocolos SSL de WCF. Cuando los equipos cliente y servidor tienen .NET Framework 4.6 o posterior instalado, se usa TLS 1.2 para la negociación.

## <a name="impact"></a>Impacto

TLS 1.2 no admite la autenticación de certificado MD5. Como resultado, si un cliente utiliza un certificado SSL que utiliza MD5 para el algoritmo hash, el cliente WCF no se puede conectar al servicio WCF. Para más información, vea [Mitigación: Servicios WCF y autenticación de certificados](mitigation-wcf-services-and-certificate-authentication.md).

## <a name="mitigation"></a>Mitigación

Puede evitar este problema para que el cliente WCF pueda conectarse a un servidor WCF realizando alguno de los siguientes procedimientos:

- Actualizar el certificado para que no use el algoritmo MD5. Esta es la solución recomendada.

- Si la vinculación no se configura dinámicamente en el código fuente, actualice el archivo de configuración de la aplicación para usar TLS 1.1 o una versión anterior del protocolo. Esto le permite seguir usando un certificado con el algoritmo hash MD5.

  > [!CAUTION]
  > Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.

  El archivo de configuración siguiente realiza esta tarea:

  ```xml
  <configuration>
      <system.serviceModel>
          <bindings>
              <netTcpBinding>
                  <binding>
                      <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                          <transport clientCredentialType="None|Windows|Certificate"
                                              protectionLevel="None|Sign|EncryptAndSign"
                                              sslProtocols="Ssl3|Tls1|Tls11">
                          </transport>
                      </security>
                  </binding>
              </netTcpBinding>
          </bindings>
      </system.ServiceModel>
  </configuration>
  ```

- Si la vinculación se configura dinámicamente en el código fuente, actualice la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> para usar TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versión anterior del protocolo en el código fuente.

  > [!CAUTION]
  > Esta solución no es recomendable, puesto que se considera que el algoritmo hash MD5 no es seguro.

## <a name="see-also"></a>Vea también

- [Cambios en el runtime](runtime-changes-in-the-net-framework-4-6.md)
