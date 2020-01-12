---
title: Prueba unitaria de C# con NUnit y .NET Core
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit.'
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 1ea17d9f830d8ac20e2bad79eebab5db767e0af8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714226"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>Prueba unitaria de C# con NUnit y .NET Core

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.
- Un editor de texto o un editor de código de su elección.

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-using-nunit* que contenga la solución. En este directorio nuevo, ejecute el comando siguiente para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba:

```dotnetcli
dotnet new sln
```
 
A continuación, cree un directorio *PrimeService*. En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute el siguiente comando para crear el proyecto de origen:

```dotnetcli
dotnet new classlib
```

Cambie el nombre de *Class1.cs* a *PrimeService.cs*. Creará una implementación de errores de la clase `PrimeService`:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

Cambie nuevamente el directorio a *unit-testing-using-nunit*. Ejecute el siguiente comando para agregar el proyecto de biblioteca de clases a la solución:

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *PrimeService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con el comando siguiente:

```dotnetcli
dotnet new nunit
```

El comando [dotnet new](../tools/dotnet-new.md) crea un proyecto de prueba que usa NUnit como la biblioteca de pruebas. La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeService.Tests.csproj*:

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. En el paso anterior, `dotnet new` agrega el SDK de prueba de Microsoft, el marco de pruebas de NUnit y el adaptador de prueba de NUnit. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

En el esquema siguiente se muestra el diseño de solución final:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

Ejecute el comando siguiente en el directorio *unit-testing-using-nunit*:

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>Crear la primera prueba

Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso. En el directorio *PrimeService.Tests*, cambie el nombre del archivo *UnitTest1.cs* por *PrimeService_IsPrimeShould.cs* y reemplace todo su contenido por el código siguiente:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        [Test]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            PrimeService primeService = CreatePrimeService();
            var result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
        
        /*
        More tests
        */
        
        private PrimeService CreatePrimeService()
        {
             return new PrimeService();
        }
    }
}
```

El atributo `[TestFixture]` indica una clase que contiene pruebas unitarias. El atributo `[Test]` indica que un método es un método de prueba.

Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

La prueba produce un error. Todavía no ha creado la implementación. Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first.");
}
```

En el directorio *unit-testing-using-nunit*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay otros casos simples para números primos: 0, -1. Puede agregar pruebas nuevas con el atributo `[Test]`, pero enseguida este proceso se hace tedioso. Hay otros atributos de NUnit que le permiten escribir un conjunto de pruebas similares.  Un atributo `[TestCase]` se usa para crear un conjunto de pruebas que ejecutan el mismo código pero tienen diferentes argumentos de entrada. Puede usar el atributo `[TestCase]` para especificar valores para esas entradas.

En lugar de crear pruebas, aplique este atributo para crear una sola prueba controlada por datos. La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método `Main` en el archivo *PrimeService.cs*:

```csharp
if (candidate < 2)
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.
