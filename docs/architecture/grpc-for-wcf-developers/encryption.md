---
title: 'Cifrado y seguridad de red: gRPC para desarrolladores de WCF'
description: Algunas notas sobre la seguridad de red y el cifrado en gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 67ee1ffaf00ea0cc6b771ede9f49b6a691af0968
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841622"
---
# <a name="encryption-and-network-security"></a>Cifrado y seguridad de red

El modelo de seguridad de red de WCF es amplio y complejo, incluida la seguridad de nivel de transporte mediante HTTPS o TLS a través de TCP, y la seguridad de nivel de mensaje mediante la especificación WS-Security para cifrar mensajes individuales.

gRPC deja redes seguras en el protocolo HTTP/2 subyacente, que se puede proteger mediante certificados TLS normales.

Los exploradores Web insisten en el uso de conexiones TLS para HTTP/2, pero la mayoría de los clientes de programación, incluido. La `HttpClient`de red, puede usar HTTP/2 a través de conexiones no cifradas. `HttpClient` *requiere* cifrado de forma predeterminada, pero puede invalidarlo mediante un modificador de <xref:System.AppContext>.

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

En el caso de las API públicas, siempre debe usar las conexiones TLS y proporcionar certificados válidos para los servicios de una autoridad SSL adecuada. [LetsEncrypt](https://letsencrypt.org) proporcionan certificados SSL gratuitos y automatizados, y la mayoría de la infraestructura de hospedaje es compatible actualmente con el estándar LetsEncrypt con complementos o extensiones comunes.

En el caso de los servicios internos a través de una red corporativa, debería considerar el uso de TLS para proteger el tráfico de red hacia y desde los servicios de gRPC.

En general, la comunicación entre los microservicios de un clúster como Kubernetes o Docker Swarm se cifra automáticamente mediante el nivel de red del contenedor, por lo que no es necesario implementar TLS en servicios que se ejecutan exclusivamente en dicho clúster. Habrá más información sobre este tema en la sección "malla de servicio" del siguiente capítulo.

Si necesita usar TLS explícito entre servicios que se ejecutan en Kubernetes, considere la posibilidad de usar una entidad de certificación en clúster y un controlador de administrador de certificados como [CERT-Manager](https://docs.cert-manager.io/en/latest/) para asignar certificados automáticamente a los servicios en el momento de la implementación.

>[!div class="step-by-step"]
>[Anterior](channel-credentials.md)
>[Siguiente](grpc-in-production.md)
