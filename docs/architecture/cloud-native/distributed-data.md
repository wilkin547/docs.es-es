---
title: Datos distribuidos
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Datos distribuidos para aplicaciones nativas en la nube
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841814"
---
# <a name="distributed-data-for-cloud-native-apps"></a>Datos distribuidos para aplicaciones nativas en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Al construir un sistema nativo de la nube que consta de muchos microservicios independientes, el modo en que piensa en los cambios de almacenamiento de datos.

Las aplicaciones monolíticas tradicionales favorecen un almacén de datos centralizado que se muestra en la figura 5-1.

![Base de datos monolítica única](./media/single-monolithic-database.png)

**Figura 5-1**. Base de datos monolítica única

En la ilustración anterior, observe cómo todos los componentes de la aplicación consumen una única base de datos relacional.

Este enfoque ofrece muchas ventajas. Es sencillo consultar los datos repartidos en varias tablas y resulta sencillo implementar [transacciones ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) que garanticen la coherencia de los datos. Siempre termina con *coherencia inmediata*: todas las actualizaciones de datos o ninguna de ellas.

Los sistemas nativos en la nube favorecen una arquitectura de datos que se muestra en la figura 5-2 en la que cada microservicio posee y encapsula sus propios datos.

![Varias bases de datos entre microservicios](./media/data-across-microservices.png)

**Figura 5-2**. Varias bases de datos entre microservicios

Tenga en cuenta que, en la figura anterior, cada microservicio posee y encapsula el almacén de datos de ti y solo expone datos al mundo exterior desde su API pública.

Este modelo permite que cada microservicio evolucione de forma independiente sin tener que coordinar los cambios del esquema de datos con otros microservicios. Cada microservicio es gratuito para implementar el tipo de almacén de datos (base de datos relacional, base de datos de documentos, almacén de clave-valor) que mejor se adapte a sus necesidades. En tiempo de ejecución, cada microservicio puede escalar sus datos en consecuencia. Esto se muestra en la figura 5-3:

![Persistencia de datos de Polyglot](./media/polyglot-data-persistence.png)

**Figura 5-3**. Persistencia de datos de Polyglot

Observe cómo en la figura anterior el catálogo de productos y los microservicios de inventario adoptan bases de datos relacionales, el microservicio de pedidos, una base de datos de documentos NoSql y el microservicio de carro de la compra, que es un almacén de pares de clave-valor externo. Mientras que las bases de datos relacionales siguen siendo relevantes para los microservicios con datos complejos, las bases de datos NoSQL han adquirido una popularidad considerable, lo que proporciona una adaptación, una búsqueda rápida y una alta disponibilidad. Su naturaleza sin esquema permite a los desarrolladores salir de una arquitectura de clases de datos con tipo y ORM que hacen que los cambios sean costosos y lentos.

>[!div class="step-by-step"]
>[Anterior](service-mesh-communication-infrastructure.md)
>[Siguiente](data-patterns.md)
