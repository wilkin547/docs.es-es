---
title: Prueba unitaria de Visual Basic en .NET Core con pruebas de dotnet y NUnit
description: 'Aprenda los conceptos de pruebas unitarias en .NET Core: cree una solución de Visual Basic de ejemplo paso a paso mediante NUnit.'
author: rprouse
ms.date: 12/01/2017
dev_langs:
- vb
ms.openlocfilehash: 552b60dd3937abc413c1b4410213948f3b509526
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a>Bibliotecas de .NET Core de prueba unitaria de Visual Basic con pruebas de dotnet y NUnit

Este tutorial le guía por una experiencia interactiva de creación de una solución de ejemplo paso a paso para aprender los conceptos de pruebas unitarias. Si prefiere seguir el tutorial con una solución precompilada, [vea o descargue el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) antes de comenzar. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Crear el proyecto de origen

Abra una ventana del Shell. Cree un directorio llamado *unit-testing-vb-nunit* que contenga la solución. En este directorio nuevo, ejecute [`dotnet new sln`](../tools/dotnet-new.md) para crear una solución nueva. Esta práctica permite facilitar la administración de la biblioteca de clases y del proyecto de prueba unitaria. En el directorio de la solución, cree un directorio *PrimeService*. Hasta el momento, esta es la estructura de directorios y archivos:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

Convierta *PrimeService* en el directorio actual y ejecute [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) para crear el proyecto de origen. Cambie el nombre de *Class1.VB* a *PrimeService.VB*. Para usar el desarrollo controlado por pruebas (TDD), tiene que crear una implementación de errores de la clase `PrimeService`:

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

Cambien nuevamente el directorio al directorio *unit-testing-vb-using-stest*. Ejecute [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) para agregar el proyecto de biblioteca de clases a la solución.

## <a name="install-the-nunit-project-template"></a>Instalación de la plantilla de proyecto NUnit

Debe instalar las plantillas de proyecto de prueba NUnit para poder crear un proyecto de prueba. Solo deberá hacerlo una vez en cada máquina de desarrollador en la que creará proyectos NUnit. Ejecute [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) para instalar las plantillas NUnit.

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a>Crear el proyecto de prueba

A continuación, cree el directorio *PrimeService.Tests*. En el esquema siguiente se muestra la estructura de directorios:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Convierta el directorio *PrimeService.Tests* en el directorio actual y cree un proyecto nuevo con [`dotnet new nunit -lang VB`](../tools/dotnet-new.md). Este comando crea un proyecto de prueba que usa NUnit como biblioteca de pruebas. La plantilla generada ha configurado el ejecutor de pruebas en *PrimeServiceTests.vbproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

El proyecto de prueba requiere otros paquetes para crear y ejecutar pruebas unitarias. En el paso anterior, `dotnet new` agrega NUnit y el adaptador de prueba NUnit. Ahora, agregue la biblioteca de clases `PrimeService` como otra dependencia al proyecto. Use el comando [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

Puede ver todo el archivo en el [repositorio de muestras](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) en GitHub.

Tiene el diseño de solución final siguiente:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

Ejecute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) en el directorio *unit-testing-vb-nunit*.

## <a name="creating-the-first-test"></a>Crear la primera prueba

El enfoque de TDD requiere la escritura de una prueba con errores, después la valida y finalmente repite el proceso. Quite *UnitTest1.vb* del directorio *PrimeService.Tests* y cree un archivo de Visual Basic nuevo denominado *PrimeService_IsPrimeShould.VB*. Agregue el código siguiente:

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

El atributo `<TestFixture>` indica una clase que contiene pruebas. El atributo `<Test>` indica un método que el ejecutor de pruebas ejecuta. En *unit-testing-vb-nunit*, ejecute [`dotnet test`](../tools/dotnet-test.md) para compilar las pruebas y la biblioteca de clases y luego ejecutar las pruebas. El ejecutor de pruebas de NUnit tiene el punto de entrada del programa para ejecutar las pruebas desde la consola. `dotnet test` inicia el ejecutor de pruebas con el proyecto de prueba unitaria que creó.

La prueba produce un error. Todavía no ha creado la implementación. Cree esta prueba escribiendo el código más simple en la clase `PrimeService` que funciona:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

En el directorio *unit-testing-vb-nunit*, vuelva a ejecutar `dotnet test`. El comando `dotnet test` ejecuta una compilación del proyecto `PrimeService` y luego del proyecto `PrimeService.Tests`. Después de compilar ambos proyectos, se ejecuta esta única prueba. Pasa.

## <a name="adding-more-features"></a>Agregar más características

Ahora que la prueba se ha superado, es el momento de escribir más. Hay algunos otros casos simples para números primos: 0, -1. Puede agregar esos casos como nuevas pruebas con el atributo `<Test>`, pero enseguida este proceso se hace tedioso. Hay otros atributos de xUnit que le permiten escribir un conjunto de pruebas similares.  Un atributo `<TestCase>` representa un conjunto de pruebas que ejecutan el mismo código, pero tienen diferentes argumentos de entrada. Puede usar el atributo `<TestCase>` para especificar valores para esas entradas.

En lugar de crear pruebas, aplique estos dos atributos para crear un conjunto de pruebas que pruebe algunos valores inferiores a 2, que es el número primo más bajo:

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Ejecute `dotnet test`, y dos de estas pruebas no se superarán. Para superar todas las pruebas, cambie la cláusula `if` al principio del método:

```vb
if candidate < 2
```

Puede continuar recorriendo en iteración agregando más pruebas, más teorías y más código en la biblioteca principal. Ya tiene la [versión terminada de las pruebas](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) y la [implementación completa de la biblioteca](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).

Ha creado una biblioteca pequeña y un conjunto de pruebas unitarias para esa biblioteca. Ha estructurado la solución, por lo que agregar pruebas y paquetes nuevos es parte del flujo de trabajo normal. Ha centrado la mayor parte del tiempo y del esfuerzo en resolver los objetivos de la aplicación.
