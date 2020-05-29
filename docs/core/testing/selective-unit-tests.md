---
title: Ejecución de pruebas unitarias selectivas
description: Cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet en .NET Core.
author: smadala
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: 6a6bbb0687742d1e3288d64fb88f6825dc678e28
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702979"
---
# <a name="run-selective-unit-tests"></a>Ejecución de pruebas unitarias selectivas

Con el comando [`dotnet test`](../tools/dotnet-test.md) en .NET Core, se puede usar una expresión de filtro para ejecutar pruebas selectivas. En este artículo se muestra cómo filtrar qué pruebas se ejecutan. En los siguientes ejemplos, se utiliza `dotnet test`. Si está usando `vstest.console.exe`, reemplace `--filter` por `--testcasefilter:`.

## <a name="character-escaping"></a>Escape de caracteres

El uso de filtros que incluyen el signo de exclamación `!` en `*nix` requiere el escape debido a que `!` está reservado. Por ejemplo, este filtro omite todas las pruebas si el espacio de nombres contiene IntegrationTests:

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> La barra diagonal inversa precede al signo de exclamación para indicar que es un carácter de escape `\!`.

En el caso de los valores `FullyQualifiedName` que incluyen una coma para los parámetros de tipo genérico, escape la coma con `%2C`. Por ejemplo:

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

:::zone pivot="mstest"

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod, Priority(1), TestCategory("CategoryA")]
        public void TestMethod1()
        {
        }

        [TestMethod, Priority(2)]
        public void TestMethod2()
        {
        }
    }
}
```

| Expresión | Resultado |
|--|--|
| `dotnet test --filter Method` | Ejecuta pruebas cuyo <xref:System.Reflection.Module.FullyQualifiedName> contenga `Method`. Disponible en `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Ejecuta pruebas cuyo nombre contenga `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTest1`.<br>**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTest1` no funcionará. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`. |
| `dotnet test --filter Priority=2` | Ejecuta pruebas anotadas con `[Priority(2)]`. |

Ejemplos de uso de los operadores condicionales `|` y `&`:

Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **o** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> es `"CategoryA"`.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **y** tienen un elemento <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> de `"CategoryA"`.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

Para ejecutar pruebas que tienen <xref:System.Reflection.Module.FullyQualifiedName> con `UnitTest1` **y** tienen un valor <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> de `"CategoryA"` **o** tienen un elemento <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> con una prioridad de `1`.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="xunit"

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Fact, Trait("Priority", "1"), Trait("Category", "CategoryA")]
        public void Test1()
        {
        }

        [Fact, Trait("Priority", "2")]
        public void Test2()
        {
        }
    }
}
```

| Expresión | Resultado |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`. |

En el ejemplo de código, los rasgos definidos con claves `"Category"` y `"Priority"` pueden usarse para filtrar.

| Expresión | Resultado |
|--|--|
| `dotnet test --filter XUnit` | Ejecuta pruebas cuyo <xref:System.Reflection.Module.FullyQualifiedName> contenga `XUnit`.  Disponible en `vstest 15.1+`. |
| `dotnet test --filter Category=CategoryA` | Ejecuta pruebas que tienen `[Trait("Category", "CategoryA")]`. |

Ejemplos de uso de los operadores condicionales `|` y `&`:

Para ejecutar pruebas que tienen `TestClass1` en su <xref:System.Reflection.Module.FullyQualifiedName> **o** tienen un elemento `Trait` con una clave de `"Category"` y el valor de `"CategoryA"`.

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

Para ejecutar pruebas que tienen `TestClass1` en su <xref:System.Reflection.Module.FullyQualifiedName> **y** tienen un elemento `Trait` con una clave de `"Category"` y un valor de `"CategoryA"`.

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

Para ejecutar pruebas que tienen <xref:System.Reflection.Module.FullyQualifiedName> con `TestClass1` **y** tienen un elemento `Trait` con una clave de `"Category"` y un valor de `"CategoryA"` **o** tienen un elemento `Trait` con una clave de `"Priority"` y un valor de `1`.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="nunit"

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Test, Property("Priority", 1), Category("CategoryA")]
        public void TestMethod1()
        {
        }

        [Test, Property("Priority", 2)]
        public void TestMethod2()
        {
        }
    }
}
```

| Expresión | Resultado |
|--|--|
| `dotnet test --filter Method` | Ejecuta pruebas cuyo <xref:System.Reflection.Module.FullyQualifiedName> contenga `Method`. Disponible en `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Ejecuta pruebas cuyo nombre contenga `TestMethod1`. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | Ejecuta pruebas que están en la clase `NUnitNamespace.UnitTest1`. |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | Ejecuta todas las pruebas excepto `NUnitNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Ejecuta pruebas anotadas con `[Category("CategoryA")]`. |
| `dotnet test --filter Priority=2` | Ejecuta pruebas anotadas con `[Priority(2)]`. |

Ejemplos de uso de los operadores condicionales `|` y `&`:

Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **o** tienen un elemento `Category` de `"CategoryA"`.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **y** tienen un elemento `Category` de `"CategoryA"`.

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

Para ejecutar pruebas que tienen <xref:System.Reflection.Module.FullyQualifiedName> con `UnitTest1` **y** tienen un elemento `Category` de `"CategoryA"` **o** tienen un elemento `Property` con un valor `"Priority"` de `1`.

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

Para obtener más información, vea [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).

:::zone-end

## <a name="see-also"></a>Vea también

- [dotnet test](../tools/dotnet-test.md)
- [dotnet test --filter](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Ordenación de pruebas unitarias](order-unit-tests.md)
