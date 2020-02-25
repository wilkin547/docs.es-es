---
title: 'Cifrado y seguridad de red: gRPC para desarrolladores de WCF'
description: Algunas notas sobre la seguridad de red y el cifrado en gRPC
ms.date: 09/02/2019
ms.openlocfilehash: f8a7aeaf2a65e4ff56ac33d728e40f09a436f7a6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542785"
---
# <a name="encryption-and-network-security"></a>Cifrado y seguridad de red

El modelo de seguridad de red para Windows Communication Foundation (WCF) es amplio y complejo. Incluye seguridad de nivel de transporte mediante HTTPS o TLS a través de TCP, y seguridad de nivel de mensaje mediante la especificación de WS-Security para cifrar mensajes individuales.

gRPC deja redes seguras en el protocolo HTTP/2 subyacente, que se puede proteger mediante el uso de certificados TLS.

Los exploradores Web insisten en el uso de conexiones TLS para HTTP/2, pero la mayoría de los clientes de programación, incluido. La `HttpClient`de red, puede usar HTTP/2 a través de conexiones no cifradas. `HttpClient` requiere el cifrado de forma predeterminada, pero puede invalidarlo mediante un modificador <xref:System.AppContext>.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

En el caso de las API públicas, siempre debe usar las conexiones TLS y proporcionar certificados válidos para los servicios de una autoridad SSL adecuada. [LetsEncrypt](https://letsencrypt.org) proporciona certificados SSL gratis y automatizados, y la mayoría de la infraestructura de hospedaje es compatible actualmente con el estándar LetsEncrypt con complementos o extensiones comunes.

En el caso de los servicios internos a través de una red corporativa, debería considerar el uso de TLS para proteger el tráfico de red hacia y desde los servicios de gRPC.

Si necesita usar TLS explícito entre servicios que se ejecutan en Kubernetes, considere la posibilidad de usar una entidad de certificación en clúster y un controlador de administrador de certificados como [CERT-Manager](https://docs.cert-manager.io/en/latest/). Después, puede asignar automáticamente certificados a los servicios en el momento de la implementación.

>[!div class="step-by-step"]
>[Anterior](channel-credentials.md)
>[Siguiente](grpc-in-production.md)
