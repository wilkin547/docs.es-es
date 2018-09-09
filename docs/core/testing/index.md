---
title: Pruebas unitarias en .NET Core
description: Las pruebas unitarias nunca han sido tan fáciles. Vea cómo usar la prueba unitaria en proyectos de .NET Core y .NET Standard.
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 4a1d880da796aac40da93ca2513b6163200ca3c1
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227433"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>Pruebas unitaria en .NET Core y .NET Standard

.NET Core se ha diseñado teniendo en cuenta la capacidad de prueba, así que crear pruebas unitarias para sus aplicaciones es más fácil que nunca. Este artículo presenta brevemente pruebas unitarias (y cómo se diferencian de otros tipos de pruebas). En los recursos vinculados se muestra cómo agregar un proyecto de prueba a la solución y luego ejecutar pruebas unitarias mediante la línea de comandos o Visual Studio.

.NET Core 2.0 admite [.NET Standard 2.0](../../standard/net-standard.md). Las bibliotecas que se usan para mostrar la prueba unitaria en esta sección se basan en .NET Standard y también funcionarán en otros tipos de proyecto.

A partir de .NET Core 2.0, existen plantillas de proyecto de prueba unitaria para C#, F# y Visual Basic.

## <a name="getting-started-with-testing"></a>Introducción a las pruebas

Una de las mejores formas de garantizar que una aplicación de software hace lo que sus autores pretenden que haga es contar con un conjunto de pruebas automatizadas. Existen varios tipos de pruebas de aplicaciones de software, como pruebas de integración, pruebas web, pruebas de carga y otras. Las pruebas unitarias que prueban componentes o métodos de software individuales son las pruebas de nivel más bajo. Las pruebas unitarias solo deben probar el código dentro del control del desarrollador y no deben probar los problemas de infraestructura, como bases de datos, sistemas de archivos o recursos de red. Se pueden escribir pruebas unitarias mediante [desarrollo controlado por pruebas (TDD)](http://deviq.com/test-driven-development/), o se pueden agregar al código existente para confirmar su grado de exactitud. En cualquier caso, deben ser pequeñas, con un nombre adecuado y rápidas, dado que lo ideal es que pueda ejecutar cientos de ellas antes de insertar los cambios en el repositorio de código compartido del proyecto.

> [!NOTE]
> A menudo, los desarrolladores tienen dificultades para idear buenos nombres para sus clases y métodos de prueba. Como punto de partida, el equipo de producto de ASP.NET sigue [estas convenciones](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests).

Al escribir pruebas unitarias, tenga cuidado de no introducir accidentalmente dependencias en la infraestructura. Tienden a hacerlas más lentas y frágiles, por lo que se deben reservar para pruebas de integración. Puede evitar estas dependencias ocultas en el código de aplicación siguiendo el [principio de dependencias explícitas](http://deviq.com/explicit-dependencies-principle/) y el uso de [inyección de dependencias](/aspnet/core/fundamentals/dependency-injection) para solicitar las dependencias del marco. También puede mantener sus pruebas unitarias en un proyecto aparte de sus pruebas de integración y asegurarse de que el proyecto de pruebas unitarias no tenga referencias a paquetes de infraestructura ni dependencias en ellos.

Más información sobre las pruebas unitarias en proyectos de .NET Core:

Los proyectos de prueba unitaria para .NET Core son compatibles con [C#](../../csharp/index.md), [F#](../../fsharp/index.md) y [Visual Basic](../../visual-basic/index.md). También puede elegir entre [xUnit](http://xunit.github.io), [NUnit](http://nunit.org) y [MSTest](https://github.com/Microsoft/vstest-docs).

Puede leer sobre esas combinaciones en estos tutoriales:

* Cree pruebas unitarias mediante [*xUnit* y *C#* con la CLI de .NET Core](unit-testing-with-dotnet-test.md).
* Cree pruebas unitarias mediante [*NUnit* y *C#* con la CLI de .NET Core](unit-testing-with-nunit.md).
* Cree pruebas unitarias mediante [*MSTest* y *C#* con la CLI de .NET Core](unit-testing-with-mstest.md).
* Cree pruebas unitarias mediante [*xUnit* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-dotnet-test.md).
* Cree pruebas unitarias mediante [*NUnit* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-nunit.md).
* Cree pruebas unitarias mediante [*MSTest* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-mstest.md).
* Cree pruebas unitarias mediante [*xUnit* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-dotnet-test.md).
* Cree pruebas unitarias mediante [*NUnit* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-nunit.md).
* Cree pruebas unitarias mediante [*MSTest* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-mstest.md).

Puede elegir varios lenguajes para las bibliotecas de clases y las bibliotecas de pruebas unitarias. Puede obtener información sobre cómo combinar y hacer coincidir los tutoriales mencionados anteriormente.

* Visual Studio Enterprise proporciona herramientas de pruebas fantásticas para .NET Core. Consulte [Live Unit Testing](/visualstudio/test/live-unit-testing) o [Cobertura de código](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage) para obtener más información.
* Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, consulte [Ejecución de pruebas unitarias selectivas](selective-unit-tests.md) o cómo [incluir y excluir pruebas con Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).
* El equipo de xUnit ha escrito un tutorial que muestra [cómo usar xUnit con .NET Core y Visual Studio](http://xunit.github.io/docs/getting-started-dotnet-core.html).
