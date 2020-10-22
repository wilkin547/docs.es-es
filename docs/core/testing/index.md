---
title: Pruebas en .NET
description: En este artículo se ofrece una breve introducción a conceptos de pruebas, terminología y herramientas para realizar pruebas en .NET.
author: IEvangelist
ms.author: dapine
ms.date: 10/19/2020
ms.openlocfilehash: 36e88cc059447a98931593e0535c70cbc92a2cf4
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223475"
---
# <a name="testing-in-net"></a>Pruebas en .NET

En este artículo se presenta el concepto de pruebas y se muestra cómo se pueden usar diferentes tipos de pruebas para validar código. Hay diversas herramientas disponibles para probar aplicaciones .NET, como la [CLI de .NET](#net-cli) o [Entornos de desarrollo integrado (IDE)](#ide).

## <a name="test-types"></a>Tipos de pruebas

Automatizar pruebas es un método magnífico para asegurarse de que el código de aplicación hace lo que sus autores pretenden. En este artículo se tratan las pruebas unitarias, las pruebas de integración y las pruebas de carga.

### <a name="unit-tests"></a>Pruebas unitarias

Una *prueba unitaria* es una prueba que ejercita componentes o métodos de software individuales, también conocidos como "unidad de trabajo". Estas solo deberían probar código que pueda controlar el desarrollador. No se usan para comprobar problemas con la infraestructura. Estos problemas incluyen la interacción con bases de datos, sistemas de archivos y recursos de red.

Para obtener más información sobre cómo crear pruebas unitarias, consulte [Herramientas de pruebas](#testing-tools).

### <a name="integration-tests"></a>Pruebas de integración

Una *prueba de integración* se diferencia de una prueba unitaria en que ejercita la capacidad de dos o más componentes de software de funcionar juntos, a lo que se conoce también como su "integración". Estas pruebas operan en un espectro más amplio del sistema sometido a prueba, mientras que las pruebas unitarias se centran en componentes individuales. Las pruebas de integración suelen incluir problemas con la infraestructura.

### <a name="load-tests"></a>Pruebas de carga

El objetivo de una *prueba de carga* es determinar si un sistema puede controlar una carga especificada, por ejemplo, el número de usuarios simultáneos que usan una aplicación y la capacidad de esta de controlar las interacciones de forma más responsable. Para obtener más información sobre las pruebas de carga de las aplicaciones web, consulte [Pruebas de carga y de esfuerzo de ASP.NET Core](/aspnet/core/test/load-tests).

## <a name="test-considerations"></a>Consideraciones de prueba

Tenga en cuenta que hay [procedimientos recomendados](unit-testing-best-practices.md) para la escritura de pruebas. Por ejemplo, [Desarrollo controlado por pruebas (TDD)](https://deviq.com/test-driven-development) es un proceso en el que una prueba unitaria se escribe antes que el código que debería comprobar. Este método se puede comparar a la creación del esquema de un libro antes de escribirlo. Está diseñado para ayudar a los desarrolladores a escribir código más simple, legible y eficaz.

## <a name="testing-tools"></a>Herramientas de pruebas

.NET es una plataforma de desarrollo de varios lenguajes y puede escribir diferentes tipos de prueba para [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) y [Visual Basic](../../visual-basic/index.yml). Para cada uno de estos lenguajes, puede elegir entre varios marcos de prueba.

### <a name="xunit"></a>xUnit

[xUnit](https://xunit.net) es una herramienta gratuita de pruebas unitarias centrada en la comunidad de código abierto para .NET. Escrito por el inventor original de NUnit v2, xUnit.net es la tecnología más reciente para las aplicaciones .NET de pruebas unitarias. xUnit.net funciona con ReSharper, CodeRush, TestDriven.NET y [Xamarin](/apps/xamarin). Es un proyecto de [.NET Foundation](https://dotnetfoundation.org) y funciona bajo su código de conducta.

Para obtener más información, vea los siguientes recursos:

- [Pruebas unitarias con C#](unit-testing-with-dotnet-test.md)
- [Pruebas unitarias con F#](unit-testing-fsharp-with-dotnet-test.md)
- [Pruebas unitarias con Visual Basic](unit-testing-visual-basic-with-dotnet-test.md)

### <a name="nunit"></a>NUnit

[NUnit](https://nunit.org) es un marco de pruebas unitarias para todos los lenguajes .NET. Inicialmente portada de JUnit, la versión de producción actual se ha reescrito con muchas características nuevas y compatibilidad con una amplia gama de plataformas de .NET. Es un proyecto de [.NET Foundation](https://dotnetfoundation.org).

Para obtener más información, vea los siguientes recursos:

- [Pruebas unitarias con C#](unit-testing-with-nunit.md)
- [Pruebas unitarias con F#](unit-testing-fsharp-with-nunit.md)
- [Pruebas unitarias con Visual Basic](unit-testing-visual-basic-with-nunit.md)

### <a name="mstest"></a>MSTest

[MSTest](https://github.com/Microsoft/testfx-docs) es el marco de pruebas de Microsoft para todos los lenguajes .NET. Es extensible y funciona con la CLI de .NET y Visual Studio. Para obtener más información, vea los siguientes recursos:

- [Pruebas unitarias con C#](unit-testing-with-mstest.md)
- [Pruebas unitarias con F#](unit-testing-fsharp-with-mstest.md)
- [Pruebas unitarias con Visual Basic](unit-testing-visual-basic-with-mstest.md)

### <a name="net-cli"></a>CLI de .NET

Puede ejecutar pruebas unitarias de soluciones desde la [CLI de .NET](../tools/index.md), con el comando [dotnet test](../tools/dotnet-test.md). La CLI de .NET expone una mayor parte de la funcionalidad que [Entornos de desarrollo integrado (IDE)](#ide) hace que esté disponible a través de interfaces de usuario. La CLI de .NET es multiplataforma y está disponible para su uso como parte de las canalizaciones de entrega e integración continuas. La CLI de .NET se usa con procesos con script para automatizar tareas comunes.

### <a name="ide"></a>IDE

Independientemente de si usa Visual Studio, Visual Studio para Mac o Visual Studio Code, hay interfaces de usuario gráficas para probar la funcionalidad. Hay más características disponibles para IDE que la CLI, por ejemplo, [Live Unit Testing](/visualstudio/test/live-unit-testing). Para obtener más información, consulte el apartado sobre la [inclusión y exclusión de pruebas con Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).

## <a name="see-also"></a>Vea también

Vea los siguientes artículos para más información:

- [Procedimientos recomendados para pruebas unitarias con .NET](unit-testing-best-practices.md)
- [Pruebas de integración en ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites)
- [Ejecución de pruebas unitarias selectivas](selective-unit-tests.md)
- [Empleo de cobertura de código para pruebas unitarias](unit-testing-code-coverage.md)
