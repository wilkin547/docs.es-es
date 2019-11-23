---
title: Información general de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre el conjunto de principios que definen el desarrollo de gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: a92fe7ca2f8e17126025362fcc3c190024ebf7d3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967763"
---
# <a name="grpc-overview"></a>Información general de gRPC

Después de examinar el Genesis de WCF y gRPC en el último capítulo, en este capítulo se considerarán algunas de las características clave de gRPC y cómo se comparan con WCF.

ASP.NET Core 3,0 es la primera versión de ASP.NET que admite de forma nativa gRPC como ciudadano de primera clase, donde Microsoft Teams contribuye a la implementación oficial de .NET de gRPC. Se recomienda como el mejor método para compilar aplicaciones distribuidas con .NET que pueden interoperar con todos los demás Marcos y lenguajes de programación principales.

## <a name="key-principles"></a>Principios clave

Como se describe en el capítulo 1, Google quería usar la introducción de HTTP/2 para reemplazar Stubby, su infraestructura RPC interna de uso general. gRPC, basado en Stubby, ahora puede aprovechar la estandarización y ampliar su aplicabilidad a la informática móvil, la nube y el Internet de las cosas.

Para lograr esto, [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) estableció un conjunto de principios que controlarían gRPC. En la siguiente lista se muestran las más relevantes, que se ocupan principalmente de maximizar la accesibilidad y la facilidad de uso:

- **Gratis y abierto** : todos los artefactos deben ser de código abierto con licencias que no restrinjan a los desarrolladores la adopción de gRPC.
- **Cobertura y simplicidad** : gRPC debe estar disponible en cada plataforma popular y lo suficientemente simple como para compilar en cualquier plataforma.
- **Interoperabilidad y alcance** : debe ser posible usar gRPC en cualquier red, sin tener en consideración el ancho de banda o la latencia, utilizando los estándares de red ampliamente disponibles.
- Uso **General y rendimiento** : el marco de trabajo debe ser utilizable por una amplia gama de casos de uso posibles sin poner en peligro el rendimiento.
- **Streaming** : el protocolo debe proporcionar semántica de streaming para grandes conjuntos de datos o mensajería asincrónica.
- **Intercambio de metadatos** : el protocolo permite que los datos no empresariales, como los tokens de autenticación, se controlen por separado de los datos empresariales reales.
- **Códigos de estado estandarizados** : la variabilidad de los códigos de error debe reducirse para que las decisiones de control de errores sean más claras y, si se requiere un control de errores más completo, se debe proporcionar un mecanismo para administrar esto dentro del intercambio de metadatos.

>[!div class="step-by-step"]
>[Anterior](introduction.md)
>[Siguiente](approach.md)
