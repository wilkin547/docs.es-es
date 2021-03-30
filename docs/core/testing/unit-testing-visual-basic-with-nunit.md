---
title: Prueba unitaria de Visual Basic en .NET Core con dotnet test y NUnit
description: 'Aprenda los conceptos de pruebas unitarias en .NET Core: cree una solución de Visual Basic de ejemplo paso a paso mediante NUnit.'
author: rprouse
ms.date: 10/04/2018
ms.openlocfilehash: 11334951d41c5cca24fcfb4853569e503cff97c5
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874906"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a>Bibliotecas de .NET Core de prueba unitaria de Visual Basic con pruebas de dotnet y NUnit

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/main/core/getting-started/unit-testing-vb-nunit/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.
- Un editor de texto o un editor de código de su elección.

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-vb-nunit* que contenga la solución. En este directorio nuevo, ejecute el comando siguiente para crear un archivo de solución nuevo para la biblioteca de clases y el proyecto de prueba:

```dotnetcli
dotnet new sln
```

A continuación, cree un directorio *PrimeService*. En el esquema siguiente se muestra la estructura de archivos hasta el momento:

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute el siguiente comando para crear el proyecto de origen:

```dotnetcli
dotnet new classlib -lang VB
```

Cambie el nombre de *Class1.VB* a *PrimeService.VB*. Creará una implementación de errores de la clase `PrimeService`:

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first.")
        End Function
    End Class
End Namespace
```

Cambien nuevamente el directorio al directorio *unit-testing-vb-using-mstest*. Ejecute el siguiente comando para agregar el proyecto de biblioteca de clases a la solución:

```dotnetcli
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *PrimeService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con el comando siguiente:

```dotnetcli
dotnet new nunit -lang VB
```

El comando [dotnet new](../tools/dotnet-new.md) crea un proyecto de prueba que usa NUnit como la biblioteca de pruebas. La plantilla generada ha configurado el ejecutor de pruebas en el archivo *PrimeServiceTests.vbproj*:

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) en GitHub.

Tiene el diseño de solución final siguiente:

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

Ejecute el comando siguiente en el directorio *unit-testing-vb-nunit*:

```dotnetcli
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a>Crear la primera prueba

Escribirá una prueba de errores, la aprobará y, luego, repetirá el proceso. En el directorio *PrimeService.Tests*, cambie el nombre del archivo *UnitTest1.vb* por *PrimeService_IsPrimeShould.VB* y reemplace todo su contenido por el código siguiente:

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

El atributo `<TestFixture>` indica una clase que contiene pruebas. El atributo `<Test>` indica un método que el ejecutor de pruebas ejecuta. En *unit-testing-vb-nunit*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

La prueba produce un error. Todavía no ha creado la implementación. Cree esta prueba que se supera escribiendo el código más simple en la clase `PrimeService` que funciona:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

En el directorio *unit-testing-vb-nunit*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregar esos casos como nuevas pruebas con el atributo `<Test>`, pero enseguida este proceso se hace tedioso. Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.  Un atributo `<TestCase>` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada. Puede usar el atributo `<TestCase>` para especificar valores para esas entradas.

En lugar de crear pruebas, aplique estos dos atributos para crear un conjunto de pruebas que pruebe algunos valores inferiores a 2, que es el número primo más bajo:

[!code-vb[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método `Main` en el archivo *PrimeService.cs*:

```vb
if candidate < 2
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/main/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.
