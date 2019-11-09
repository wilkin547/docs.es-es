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
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="b49ae-103">Datos distribuidos para aplicaciones nativas en la nube</span><span class="sxs-lookup"><span data-stu-id="b49ae-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b49ae-104">Al construir un sistema nativo de la nube que consta de muchos microservicios independientes, el modo en que piensa en los cambios de almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="b49ae-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="b49ae-105">Las aplicaciones monolíticas tradicionales favorecen un almacén de datos centralizado que se muestra en la figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="b49ae-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![Base de datos monolítica única](./media/single-monolithic-database.png)

<span data-ttu-id="b49ae-107">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="b49ae-107">**Figure 5-1**.</span></span> <span data-ttu-id="b49ae-108">Base de datos monolítica única</span><span class="sxs-lookup"><span data-stu-id="b49ae-108">Single monolithic database</span></span>

<span data-ttu-id="b49ae-109">En la ilustración anterior, observe cómo todos los componentes de la aplicación consumen una única base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="b49ae-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="b49ae-110">Este enfoque ofrece muchas ventajas.</span><span class="sxs-lookup"><span data-stu-id="b49ae-110">There are many benefits to this approach.</span></span> <span data-ttu-id="b49ae-111">Es sencillo consultar los datos repartidos en varias tablas y resulta sencillo implementar [transacciones ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) que garanticen la coherencia de los datos.</span><span class="sxs-lookup"><span data-stu-id="b49ae-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="b49ae-112">Siempre termina con *coherencia inmediata*: todas las actualizaciones de datos o ninguna de ellas.</span><span class="sxs-lookup"><span data-stu-id="b49ae-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="b49ae-113">Los sistemas nativos en la nube favorecen una arquitectura de datos que se muestra en la figura 5-2 en la que cada microservicio posee y encapsula sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="b49ae-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![Varias bases de datos entre microservicios](./media/data-across-microservices.png)

<span data-ttu-id="b49ae-115">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="b49ae-115">**Figure 5-2**.</span></span> <span data-ttu-id="b49ae-116">Varias bases de datos entre microservicios</span><span class="sxs-lookup"><span data-stu-id="b49ae-116">Multiple databases across microservices</span></span>

<span data-ttu-id="b49ae-117">Tenga en cuenta que, en la figura anterior, cada microservicio posee y encapsula el almacén de datos de ti y solo expone datos al mundo exterior desde su API pública.</span><span class="sxs-lookup"><span data-stu-id="b49ae-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="b49ae-118">Este modelo permite que cada microservicio evolucione de forma independiente sin tener que coordinar los cambios del esquema de datos con otros microservicios.</span><span class="sxs-lookup"><span data-stu-id="b49ae-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="b49ae-119">Cada microservicio es gratuito para implementar el tipo de almacén de datos (base de datos relacional, base de datos de documentos, almacén de clave-valor) que mejor se adapte a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="b49ae-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="b49ae-120">En tiempo de ejecución, cada microservicio puede escalar sus datos en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b49ae-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="b49ae-121">Esto se muestra en la figura 5-3:</span><span class="sxs-lookup"><span data-stu-id="b49ae-121">This is shown in Figure 5-3:</span></span>

![Persistencia de datos de Polyglot](./media/polyglot-data-persistence.png)

<span data-ttu-id="b49ae-123">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="b49ae-123">**Figure 5-3**.</span></span> <span data-ttu-id="b49ae-124">Persistencia de datos de Polyglot</span><span class="sxs-lookup"><span data-stu-id="b49ae-124">Polyglot data persistence</span></span>

<span data-ttu-id="b49ae-125">Observe cómo en la figura anterior el catálogo de productos y los microservicios de inventario adoptan bases de datos relacionales, el microservicio de pedidos, una base de datos de documentos NoSql y el microservicio de carro de la compra, que es un almacén de pares de clave-valor externo.</span><span class="sxs-lookup"><span data-stu-id="b49ae-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="b49ae-126">Mientras que las bases de datos relacionales siguen siendo relevantes para los microservicios con datos complejos, las bases de datos NoSQL han adquirido una popularidad considerable, lo que proporciona una adaptación, una búsqueda rápida y una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b49ae-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="b49ae-127">Su naturaleza sin esquema permite a los desarrolladores salir de una arquitectura de clases de datos con tipo y ORM que hacen que los cambios sean costosos y lentos.</span><span class="sxs-lookup"><span data-stu-id="b49ae-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b49ae-128">[Anterior](service-mesh-communication-infrastructure.md)
>[Siguiente](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="b49ae-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
