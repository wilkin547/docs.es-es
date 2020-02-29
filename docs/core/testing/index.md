---
title: Pruebas unitaria en .NET Core y .NET Standard
description: En este artículo se proporciona información general breve de las pruebas unitarias para los proyectos de .NET Core y .NET Standard.
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 1263bfe337b9d6609c0ca7df70aa299a61a7f1a0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157406"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>Pruebas unitaria en .NET Core y .NET Standard

.NET Core facilita la creación de pruebas unitarias. En este artículo se presentan las pruebas unitarias y se indican las diferencias con otros tipos de pruebas. En los recursos vinculados al final de la página se muestra cómo agregar un proyecto de prueba a una solución. Una vez que haya configurado el proyecto de prueba, podrá ejecutar las pruebas unitarias con la línea de comandos o con Visual Studio.

Si está realizando pruebas con un proyecto de **ASP.NET Core**, consulte [Pruebas de integración en ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites).

.NET Core 2.0 y versiones posteriores admiten [.NET Standard 2.0](../../standard/net-standard.md), cuyas bibliotecas usaremos para mostrar las pruebas unitarias.

Puede usar plantillas de proyecto de prueba unitaria integradas de .NET Core 2.0 y versiones posteriores para C#, F# y Visual Basic como punto inicial para su proyecto personal.

## <a name="what-are-unit-tests"></a>¿Qué son las pruebas unitarias?

Automatizar pruebas es un método magnífico para asegurarse de que una aplicación de software hace lo que sus autores pretenden. Hay varios tipos de pruebas para aplicaciones de software. Estas incluyen pruebas de integración, pruebas web y pruebas de carga, entre otras. Con las **pruebas unitarias** se comprueban componentes y métodos de software individuales. Estas solo deberían probar código que pueda controlar el desarrollador. No se deberían usar para comprobar problemas con la infraestructura. Estos problemas incluyen los relacionados con bases de datos, el sistema de archivos o recursos de red.

Además, es recomendable que tenga en cuenta que hay procedimientos recomendados para la escritura de pruebas. Por ejemplo, [Test Driven Development (TTD)](https://deviq.com/test-driven-development/) es un proceso en el que una prueba unitaria se escribe antes que el código que debería comprobar. Este método se puede comparar a la creación del esquema de un libro antes de escribirlo. Está diseñado para ayudar a los desarrolladores a escribir código más simple, legible y eficaz.

> [!NOTE]
> El equipo de ASP.NET sigue [estas convenciones](https://github.com/dotnet/aspnetcore/wiki/Engineering-guidelines#unit-tests-and-functional-tests) para ayudar a los desarrolladores a asignar buenos nombres a clases de prueba y métodos.

No intente incluir dependencias en la infraestructura al escribir pruebas unitarias. Estas vuelven las pruebas lentas y frágiles, por lo que deberían reservarse para pruebas de integración. Puede evitar esas dependencias en su aplicación si sigue el [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/) (Principio de dependencias explícitas) y usando la [Inserción de dependencias](/aspnet/core/fundamentals/dependency-injection). También puede mantener las pruebas unitarias en un proyecto separado de las pruebas de integración. Esto asegurará que el proyecto de pruebas unitarias no tiene referencias a paquetes de infraestructura ni dependencias de estos.

## <a name="next-steps"></a>Pasos siguientes

Puede encontrar más información sobre las pruebas unitarias en proyectos de .NET Core:

Los proyectos de pruebas unitarias de .NET Core son compatibles con los siguientes lenguajes:

- [C#](../../csharp/index.yml)
- [F#](../../fsharp/index.yml)
- [Visual Basic](../../visual-basic/index.yml)

También puede elegir entre las siguientes opciones:

- [xUnit](https://xunit.github.io)
- [NUnit](https://nunit.org)
- [MSTest](https://github.com/Microsoft/testfx-docs)

Puede obtener más información en los siguientes tutoriales:

- Cree pruebas unitarias mediante [*xUnit* y *C#* con la CLI de .NET Core](unit-testing-with-dotnet-test.md).
- Cree pruebas unitarias mediante [*NUnit* y *C#* con la CLI de .NET Core](unit-testing-with-nunit.md).
- Cree pruebas unitarias mediante [*MSTest* y *C#* con la CLI de .NET Core](unit-testing-with-mstest.md).
- Cree pruebas unitarias mediante [*xUnit* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-dotnet-test.md).
- Cree pruebas unitarias mediante [*NUnit* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-nunit.md).
- Cree pruebas unitarias mediante [*MSTest* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-mstest.md).
- Cree pruebas unitarias mediante [*xUnit* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-dotnet-test.md).
- Cree pruebas unitarias mediante [*NUnit* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-nunit.md).
- Cree pruebas unitarias mediante [*MSTest* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-mstest.md).

Puede obtener más información en los siguientes artículos:

- Visual Studio Enterprise proporciona herramientas de pruebas fantásticas para .NET Core. Consulte [Live Unit Testing](/visualstudio/test/live-unit-testing) o [Cobertura de código](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage) para obtener más información.
- Para obtener más información sobre cómo ejecutar pruebas unitarias, vea [Ejecución de pruebas unitarias selectivas](selective-unit-tests.md) o [Incluir y excluir proyectos de prueba y métodos de prueba](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).
- [Cómo usar xUnit con .NET Core y Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html).
