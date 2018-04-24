---
title: Prueba unitaria de C# con NUnit y .NET Core
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y NUnit.'
keywords: NUnit,. NET y .NET Core
author: rprouse
ms.date: 12/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.openlocfilehash: b29912a58511305202a18e8da4ae57700605867a
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>Prueba unitaria de C# con NUnit y .NET Core

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-using-nunit* que contenga la solución. En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba. A continuación, cree un directorio *PrimeService*. En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen. Cambie el nombre de *Class1.cs* a *PrimeService.cs*. Para usar el desarrollo controlado por pruebas (TDD), tiene que crear una implementación de errores de la clase `PrimeService`:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first");
        }
    }
}
```

Cambie nuevamente el directorio a *unit-testing-using-nunit*. Ejecute [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.

## <a name="install-the-nunit-project-template"></a>Instalación de la plantilla de proyecto NUnit

Debe instalar las plantillas de proyecto de prueba NUnit para poder crear un proyecto de prueba. Solo deberá hacerlo una vez en cada máquina de desarrollador en la que creará proyectos NUnit. Ejecute [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) para instalar las plantillas NUnit.

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *PrimeService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new nunit`](../tools/dotnet-new.md). Este comando de dotnet nuevo crea un proyecto de prueba que usa NUnit como la biblioteca de pruebas. La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. En el paso anterior, `dotnet new` agrega el SDK de prueba de Microsoft, el marco de pruebas de NUnit y el adaptador de prueba de NUnit. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

En el esquema siguiente se muestra el diseño de solución final:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-dotnet-test*.

## <a name="creating-the-first-test"></a>Crear la primera prueba

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
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
    throw new NotImplementedException("Please create a test first");
}
```

En el directorio *unit-testing-using-nunit*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregar pruebas nuevas con el atributo `[Test]`, pero enseguida este proceso se hace tedioso. Hay otros atributos de NUnit que le permiten escribir un conjunto de pruebas similares.  Un atributo `[TestCase]` se usa para crear un conjunto de pruebas que ejecutan el mismo código pero tienen diferentes argumentos de entrada. Puede usar el atributo `[TestCase]` para especificar valores para esas entradas.

En lugar de crear pruebas, aplique este atributo para crear una sola prueba controlada por datos. La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método:

```csharp
if (candidate < 2)
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.
