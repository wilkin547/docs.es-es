---
title: "Ejecución de pruebas unitarias selectivas"
description: "Muestra cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet."
keywords: .NET, .NET Core, prueba unitaria, prueba selectiva
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="running-selective-unit-tests"></a>Ejecución de pruebas unitarias selectivas

En los siguientes ejemplos, se utiliza `dotnet test`. Si está usando `vstest.console.exe`, reemplace `--filter ` por `--testcasefilter:`.

## <a name="mstest"></a>MSTest

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter Method` | Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`. Disponible en `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Ejecuta pruebas cuyo nombre contenga `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTestClass1`.<br>**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTestClass1` no funcionará. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTestClass1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`. |
| `dotnet test --filter Priority=3` | Ejecuta pruebas anotadas con `[Priority(3)]`.<br>**Nota:** `Priority~3` es un valor no válido, ya que no es una cadena. |

**Usar operadores condicionales | y &amp;**

| Expresión | Resultado |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTestClass1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1. |

## <a name="xunit"></a>xUnit

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`. |

En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.  Disponible en `vstest 15.1+`. |
| `dotnet test --filter Category=bvt` | Ejecuta las pruebas que tienen `[Trait("Category", "bvt")]`. |

**Usar operadores condicionales | y &amp;**

| Expresión | Resultado |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `Nightly`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `Nightly`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1. |
