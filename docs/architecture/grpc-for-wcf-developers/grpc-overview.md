---
title: Información general de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre el conjunto de principios que definen el desarrollo de gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: 99e1bdb1f49469f444044027c3ac5d927f9cab13
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938408"
---
# <a name="grpc-overview"></a>Información general de gRPC

Después de examinar el Genesis de ambos Windows Communication Foundation (WCF) y gRPC en el último capítulo, en este capítulo se consideran algunas de las características clave de gRPC y cómo se comparan con WCF.

ASP.NET Core 3,0 es la primera versión de ASP.NET que admite de forma nativa gRPC como ciudadano de primera clase, donde Microsoft Teams contribuye a la implementación oficial de .NET de gRPC. Se recomienda para compilar aplicaciones distribuidas con .NET que pueden interoperar con todos los demás Marcos y lenguajes de programación principales.

## <a name="key-principles"></a>Principios fundamentales

Como se describe en el capítulo 1, Google quería usar la introducción de HTTP/2 para reemplazar Stubby, su infraestructura RPC interna de uso general. gRPC, basado en Stubby, ahora puede aprovechar las ventajas de la normalización y extender su aplicabilidad a la informática móvil, la nube y el Internet de las cosas.

Para lograr esta estandarización, [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) estableció un conjunto de principios que controlarían gRPC. En la siguiente lista se muestran las más relevantes, que se ocupan principalmente de maximizar la accesibilidad y la facilidad de uso:

- **Gratis y abierto** : todos los artefactos deben ser de código abierto, con licencias que no restringen a los desarrolladores la adopción de gRPC.
- **Cobertura y simplicidad** : gRPC debe estar disponible en cada plataforma popular y lo suficientemente sencillo como para compilar en cualquier plataforma.
- **Interoperabilidad y alcance** : debe ser posible usar gRPC en cualquier red, independientemente del ancho de banda o la latencia, mediante el uso de los estándares de red ampliamente disponibles.
- **Uso general y rendimiento** : el marco de trabajo debe ser utilizable por una amplia gama de casos de uso posibles, sin poner en peligro el rendimiento.
- **Streaming** : el protocolo debe proporcionar semántica de streaming para grandes conjuntos de valores o mensajería asincrónica.
- **Intercambio de metadatos** : el protocolo permite que los datos no empresariales, como los tokens de autenticación, se controlen por separado de los datos empresariales reales.
- **Códigos de estado estandarizados** : la variabilidad de los códigos de error debe reducirse para que las decisiones de control de errores sean más claras. Cuando se requiere un control de errores más completo, se debe proporcionar un mecanismo para administrar el comportamiento en el intercambio de metadatos.

>[!div class="step-by-step"]
>[Anterior](introduction.md)
>[Siguiente](approach.md)
