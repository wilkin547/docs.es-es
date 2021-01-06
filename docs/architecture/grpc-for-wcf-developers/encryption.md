---
title: 'Cifrado y seguridad de red: gRPC para desarrolladores de WCF'
description: Algunas notas sobre la seguridad de red y el cifrado en gRPC
ms.date: 12/15/2020
ms.openlocfilehash: 0735158ed69ce425c4f00eed6c42689b888a1885
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938629"
---
# <a name="encryption-and-network-security"></a>Cifrado y seguridad de red

El modelo de seguridad de red para Windows Communication Foundation (WCF) es amplio y complejo. Incluye seguridad de nivel de transporte mediante HTTPS o TLS a través de TCP, y seguridad de nivel de mensaje mediante el WS-Security especificación para cifrar mensajes individuales.

gRPC deja redes seguras en el protocolo HTTP/2 subyacente, que se puede proteger mediante el uso de certificados TLS.

Los exploradores Web insisten en el uso de conexiones TLS para HTTP/2, pero la mayoría de los clientes de programación, incluido. La red `HttpClient` , puede usar http/2 a través de conexiones no cifradas. `HttpClient` requiere el cifrado de forma predeterminada, pero puede invalidar este comportamiento mediante un <xref:System.AppContext> modificador.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

En el caso de las API públicas, siempre debe usar las conexiones TLS y proporcionar certificados válidos para los servicios de una autoridad SSL adecuada. [LetsEncrypt](https://letsencrypt.org) proporciona certificados SSL gratis y automatizados, y la mayoría de la infraestructura de hospedaje es compatible actualmente con el estándar LetsEncrypt con complementos o extensiones comunes.

En el caso de los servicios internos a través de una red corporativa, debería considerar el uso de TLS para proteger el tráfico de red hacia y desde los servicios de gRPC.

Si necesita usar TLS explícito entre servicios que se ejecutan en Kubernetes, considere la posibilidad de usar una entidad de certificación en clúster y un controlador de administrador de certificados como [CERT-Manager](https://docs.cert-manager.io/en/latest/). Después, puede asignar automáticamente certificados a los servicios en el momento de la implementación.

>[!div class="step-by-step"]
>[Anterior](channel-credentials.md)
>[Siguiente](grpc-in-production.md)
