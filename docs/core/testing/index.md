---
title: Pruebas unitarias en .NET Core
description: Pruebas unitarias en .NET Core
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 815ac74c-4bd9-4a94-a87c-78288b27c0e2
translationtype: Human Translation
ms.sourcegitcommit: 095ebad90e3f0b188d208d22f6f16b9552f8ea86
ms.openlocfilehash: ca9d57a3ef3382c4957de5edb55959f1a3f13ee0
ms.lasthandoff: 03/06/2017

---

# <a name="unit-testing-in-net-core"></a>Pruebas unitarias en .NET Core

Por [Steve Smith](http://ardalis.com) y [Bill Wagner](https://github.com/BillWagner).

.NET Core se ha diseñado teniendo en cuenta la capacidad de prueba, así que crear pruebas unitarias para sus aplicaciones es más fácil que nunca. Este artículo presenta brevemente pruebas unitarias (y cómo se diferencian de otros tipos de pruebas).
En los recursos vinculados se muestra cómo agregar un proyecto de prueba a la solución y luego ejecutar pruebas unitarias mediante la línea de comandos o Visual Studio.

## <a name="getting-started-with-testing"></a>Introducción a las pruebas
 
Una de las mejores formas de garantizar que una aplicación de software hace lo que sus autores pretenden que haga es contar con un conjunto de pruebas automatizadas. Existen muchos tipos diferentes de pruebas de aplicaciones de software, como pruebas de integración, pruebas web, pruebas de carga y muchas otras. En el nivel más bajo están las pruebas unitarias, que prueban componentes o métodos de software individuales. Las pruebas unitarias solo deben probar el código dentro del control del desarrollador y no deben probar los problemas de infraestructura, como bases de datos, sistemas de archivos o recursos de red. Se pueden escribir pruebas unitarias mediante [desarrollo controlado por pruebas (TDD)](http://deviq.com/test-driven-development/), o se pueden agregar al código existente para confirmar su grado de exactitud. En cualquier caso, deben ser pequeñas, con un nombre adecuado y rápidas, dado que lo ideal será que pueda ejecutar cientos de ellas antes de insertar los cambios en el repositorio de código compartido del proyecto.

> [!NOTE]
> A menudo, los desarrolladores tienen dificultades para idear buenos nombres para sus clases y métodos de prueba. Como punto de partida, el equipo de producto de ASP.NET sigue [estas convenciones](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests).

Al escribir pruebas unitarias, tenga cuidado de no introducir accidentalmente dependencias en la infraestructura. Tienden a hacerlas más lentas y frágiles, por lo que se deben reservar para pruebas de integración. Puede evitar estas dependencias ocultas en el código de aplicación siguiendo el [principio de dependencias explícitas](http://deviq.com/explicit-dependencies-principle/) y el uso de [inyección de dependencias](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection) para solicitar las dependencias del marco. También puede mantener sus pruebas unitarias en un proyecto aparte de sus pruebas de integración y asegurarse de que el proyecto de pruebas unitarias no tenga referencias a paquetes de infraestructura ni dependencias en ellos.

Más información sobre las pruebas unitarias en proyectos de .NET Core:

Pruebe este [tutorial de creación de pruebas unitarias con xUnit y la CLI de .NET](unit-testing-with-dotnet-test.md). 

El equipo de XUnit ha escrito un tutorial que muestra [cómo usar xUnit con .NET Core y Visual Studio](http://xunit.github.io/docs/getting-started-dotnet-core.html).

Si prefiere usar MSTest, pruebe el [tutorial de creación de pruebas unitarias con MSTest y la CLI de .NET](unit-testing-with-mstest.md).

