---
title: "Diseñar la capa de aplicación de microservicio y API de Web"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar la capa de aplicación de microservicio y API de Web"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Diseñar la capa de aplicación de microservicio y API de Web

## <a name="using-solid-principles-and-dependency-injection"></a>Uso de principios sólidos e inyección de dependencia

Principios sólidos son técnicas críticas que se usará en las aplicaciones modernas y críticas, como el desarrollo de un microservicio con patrones DDD. SÓLIDO es un acrónimo que grupos cinco los principios fundamentales:

-   Principio de responsabilidad única

-   Principio abierto/cerrado

-   Sustitución de Liskov

-   Principio de segregación de inversión

-   Principio de la inversión de dependencia

SÓLIDO es más acerca de cómo diseñar la aplicación o capas de microservicio interno y separar las dependencias entre ellos. No está relacionado con el dominio, pero diseño técnico de la aplicación. La entidad de seguridad final, el principio de la inversión de dependencia (DI), le permite desacoplar el nivel de infraestructura del resto de las capas, lo que permite una mejor implementación desacoplada de las capas DDD.

DI es una manera de implementar el principio de inversión de dependencia. Es una técnica para lograr el acoplamiento flexible entre los objetos y sus dependencias. En lugar de crear directamente instancias de colaboradores, o mediante las referencias estáticas, los objetos que necesita una clase para realizar sus acciones se proporcionan a (o "inyectar") la clase. A menudo, las clases declarará sus dependencias a través de su constructor, lo que les permite seguir el principio de dependencias explícitas. DI normalmente está basada en determinados contenedores de inversión de Control (IoC). ASP.NET Core proporciona un contenedor de IoC sencillo integrado, pero también puede usar el contenedor de IoC favoritos, como Autofac o Ninject.

Siguiendo los principios sólidos, las clases tenderán naturalmente sea pequeño, correctamente factorizada y probados fácilmente. Pero, ¿cómo puede saber si hay demasiadas dependencias que se va a se insertan en las clases? Si usas DI a través del constructor, resultará fácil detectar que con solo mirar el número de parámetros para el constructor. Si hay demasiadas dependencias, esto suele ser un inicio de sesión (una [código olor](http://deviq.com/code-smells/)) que está intentando hacer demasiado la clase y, probablemente se infringe el principio de responsabilidad única.

Tardaría otra guía para cubrir sólido en detalle. Por lo tanto, esta guía requiere tener solo un conocimiento mínimo de estos temas.

#### <a name="additional-resources"></a>Recursos adicionales

-   **SÓLIDO: Principios de programación orientada a objetos fundamentales**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **Inversión de contenedores de controles y el modelo de inserción de dependencias**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. Es una novedad adherencia**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Anterior] (nosql-base de datos de persistencia-infrastructure.md) [siguiente] (microservice-application-layer-implementation-web-api.md)
