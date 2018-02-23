---
title: "Diseñar el nivel de aplicación de microservicios y la API web"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Diseñar el nivel de aplicación de microservicios y la API web"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c166e0286d0769e24a6361037eb6c4694fb821ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Diseñar el nivel de aplicación de microservicios y la API web

## <a name="using-solid-principles-and-dependency-injection"></a>Uso de principios SOLID e inserción de dependencias

Los principios SOLID son técnicas fundamentales para utilizar en cualquier aplicación moderna y crítica, como para el desarrollo de un microservicio con patrones DDD. En inglés, SOLID representa un acrónimo que agrupa cinco principios fundamentales:

-   Principio de responsabilidad única

-   Principio de abierto y cerrado

-   Principio de sustitución de Liskov

-   Principio de segregación de inversión

-   Principio de inversión de dependencias

SOLID hace referencia a la forma de diseñar los niveles internos de una aplicación o de un microservicio, así como a separar las dependencias entre ellas. No está relacionado con el dominio, sino con el diseño técnico de la aplicación. El principio final, el de inversión de dependencias, le permite desacoplar el nivel de infraestructura del resto de niveles, lo que permite una mejor implementación desacoplada de los niveles de DDD.

La inversión de dependencias es una forma de implementar el principio de inversión de dependencias. Es una técnica para lograr el acoplamiento flexible entre los objetos y sus dependencias. En lugar de crear directamente instancias de colaboradores o de usar referencias estáticas, los objetos que una clase necesita para llevar a cabo sus acciones se proporcionan (o se "insertan") a dicha clase. A menudo, las clases declaran sus dependencias a través de su constructor, lo que les permite seguir el principio de dependencias explícitas. Normalmente la inversión de dependencias está basada en determinados contenedores de Inversión de control (IoC). ASP.NET Core proporciona un sencillo contenedor de IoC integrado. Aun así, usted puede usar el contenedor de IoC que prefiera, como Autofac o Ninject.

Siguiendo los principios SOLID, las clases tenderán naturalmente a ser pequeñas, a estar factorizadas correctamente y a poder probarse fácilmente. Pero, ¿cómo puede saber si se van a insertar demasiadas dependencias en sus clases? Si usa la inversión de dependencias a través del constructor, le resultará fácil saberlo con solo mirar el número de parámetros de su constructor. Si hay demasiadas dependencias, esto suele ser una señal (una [intuición de código](http://deviq.com/code-smells/)) de que su clase está intentando hacer demasiado y de que probablemente esté infringiendo el principio de responsabilidad única.

Necesitaríamos otra guía para tratar SOLID con detalle. Para esta guía solo necesita tener unos conocimientos mínimos de estos temas.

#### <a name="additional-resources"></a>Recursos adicionales

-   **SOLID: Fundamental OOP Principles** (SOLID: principios fundamentales de OOP)
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **Inversion of Control Containers and the Dependency Injection pattern** (Inversión del patrón de contenedores de control y de inserción de dependencias)
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. New is Glue** (La novedad es el pegamento)
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Anterior] (nosql-database-persistence-infrastructure.md) [Siguiente] (microservice-application-layer-implementation-web-api.md)
