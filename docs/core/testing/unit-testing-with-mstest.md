---
title: Prueba unitaria de C# con MSTest y .NET Core
description: 'Aprenda los conceptos de pruebas unitarias en C# y .NET Core: cree paso a paso una solución de ejemplo mediante pruebas de dotnet y MSTest.'
author: ncarandini
ms.author: wiwagn
ms.date: 10/21/2020
ms.openlocfilehash: e2c3326778d7fc1a492062cff4f2d2ad4a61ac18
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874893"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a>Prueba unitaria de C# con MSTest y .NET Core

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="create-the-source-project"></a>Creación del proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-using-mstest* que contenga la solución. En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba. A continuación, cree un directorio *PrimeService*. En el esquema siguiente se muestra la estructura de directorios y archivos hasta el momento:

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib`](../tools/dotnet-new.md) para crear el proyecto de origen. Cambie el nombre de *Class1.cs* a *PrimeService.cs*. Creará una implementación de errores de la clase `PrimeService`:

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

Cambie nuevamente el directorio al directorio *unit-testing-using-mstest*. Ejecute [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.

## <a name="create-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *PrimeService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new mstest`](../tools/dotnet-new.md). Este comando de dotnet nuevo crea un proyecto de prueba que usa MSTest como la biblioteca de pruebas. La plantilla generada configura el ejecutor de pruebas en el archivo *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. `dotnet new` en el paso anterior agregó el SDK de MSTest, el marco de prueba de MSTest y el ejecutor de MSTest. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) en GitHub.

En el esquema siguiente se muestra el diseño de solución final:

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-using-mstest*.

## <a name="create-the-first-test"></a>Creación de la primera prueba

Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso. Quite *UnitTest1.cs* del directorio *PrimeService.Tests* y cree un nuevo archivo de C# denominado *PrimeService_IsPrimeShould.cs* con el siguiente contenido:

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        [TestMethod]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var primeService = new PrimeService();
            bool result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

El [atributo TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) indica una clase que contiene pruebas unitarias. El [atributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indica que un método es un método de prueba.

Guarde este archivo y ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de MSTest tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

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

En el directorio *unit-testing-using-mstest*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="add-more-features"></a>Adición de más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregar pruebas nuevas con el [atributo TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), pero este proceso enseguida se hace tedioso. Hay otros atributos de MSTest que le permiten escribir un conjunto de pruebas similares.  Un [atributo DataTestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada. Puede usar el [atributo DataRow](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) para especificar valores para esas entradas.

En lugar de crear pruebas nuevas, aplique estos dos atributos para crear una sola prueba controlada por datos. La prueba controlada por datos es un método que prueba varios valores menores que dos, que es el número primo menor:

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-mstest/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método:

```csharp
if (candidate < 2)
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [Usar el marco de trabajo MSTest en pruebas unitarias](/visualstudio/test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests)
- [Documentos del marco de pruebas de MSTest V2](https://github.com/Microsoft/testfx-docs)
