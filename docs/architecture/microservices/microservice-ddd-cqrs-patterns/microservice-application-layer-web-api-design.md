---
title: Diseñar el nivel de aplicación de microservicios y la API web
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Una breve mención de los principios SOLID para diseñar el nivel de aplicación.
ms.date: 10/08/2018
ms.openlocfilehash: 3c3b9f74e76e01deafa1f97de5d3250d57716014
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68676522"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a>Diseño del nivel de aplicación de microservicios y la API web

## <a name="use-solid-principles-and-dependency-injection"></a>Uso de principios SOLID e inserción de dependencias

Los principios SOLID son técnicas fundamentales para utilizar en cualquier aplicación moderna y crítica, como para el desarrollo de un microservicio con patrones DDD. En inglés, SOLID representa un acrónimo que agrupa cinco principios fundamentales:

- Principio de responsabilidad única

- Principio de abierto y cerrado

- Principio de sustitución de Liskov

- Principio de segregación de interfaces

- Principio de inversión de dependencias

SOLID hace referencia a la forma de diseñar los niveles internos de una aplicación o de un microservicio, así como a separar las dependencias entre ellas. No está relacionado con el dominio, sino con el diseño técnico de la aplicación. El principio final, el de inversión de dependencias, le permite desacoplar el nivel de infraestructura del resto de niveles, lo que permite una mejor implementación desacoplada de los niveles de DDD.

La inserción de dependencias (DI) es una forma de implementar el principio de inversión de dependencias. Es una técnica para lograr el acoplamiento flexible entre los objetos y sus dependencias. En lugar de crear directamente instancias de colaboradores o de usar referencias estáticas (es decir, usar new...), los objetos que una clase necesita para llevar a cabo sus acciones se proporcionan a la clase (o se "insertan" en ella). A menudo, las clases declaran sus dependencias a través de su constructor, lo que les permite seguir el principio de dependencias explícitas. Normalmente, la inserción de dependencias se basa en determinados contenedores de Inversión de control (IoC). ASP.NET Core proporciona un sencillo contenedor de IoC integrado. Aun así, usted puede usar el contenedor de IoC que prefiera, como Autofac o Ninject.

Siguiendo los principios SOLID, las clases tenderán naturalmente a ser pequeñas, a estar factorizadas correctamente y a poder probarse fácilmente. Pero, ¿cómo puede saber si se van a insertar demasiadas dependencias en sus clases? Si usa la inversión de dependencias a través del constructor, le resultará fácil saberlo con solo mirar el número de parámetros de su constructor. Si hay demasiadas dependencias, esto suele ser una señal (una [intuición de código](https://deviq.com/code-smells/)) de que su clase está intentando hacer demasiado y de que probablemente esté infringiendo el principio de responsabilidad única.

Necesitaríamos otra guía para tratar SOLID con detalle. Para esta guía solo necesita tener unos conocimientos mínimos de estos temas.

#### <a name="additional-resources"></a>Recursos adicionales

- **SOLID: SOLID: principios fundamentales de OOP** \
  <https://deviq.com/solid/>

- **Contenedores de Inversión de control y el patrón de inserción de dependencias** \
  <https://martinfowler.com/articles/injection.html>

- **Steve Smith. New es como pegamento** \
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> [Anterior](nosql-database-persistence-infrastructure.md)
> [Siguiente](microservice-application-layer-implementation-web-api.md)
