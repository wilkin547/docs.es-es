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
# <a name="run-selective-unit-tests"></a><span data-ttu-id="4b259-103">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="4b259-103">Run selective unit tests</span></span>

<span data-ttu-id="4b259-104">Con el comando [`dotnet test`](../tools/dotnet-test.md) en .NET Core, se puede usar una expresión de filtro para ejecutar pruebas selectivas.</span><span class="sxs-lookup"><span data-stu-id="4b259-104">With the [`dotnet test`](../tools/dotnet-test.md) command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="4b259-105">En este artículo se muestra cómo filtrar qué pruebas se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="4b259-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="4b259-106">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="4b259-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="4b259-107">Si está usando `vstest.console.exe`, reemplace `--filter` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="4b259-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="4b259-108">Escape de caracteres</span><span class="sxs-lookup"><span data-stu-id="4b259-108">Character escaping</span></span>

<span data-ttu-id="4b259-109">El uso de filtros que incluyen el signo de exclamación `!` en `*nix` requiere el escape debido a que `!` está reservado.</span><span class="sxs-lookup"><span data-stu-id="4b259-109">Using filters that include exclamation mark `!` on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="4b259-110">Por ejemplo, este filtro omite todas las pruebas si el espacio de nombres contiene IntegrationTests:</span><span class="sxs-lookup"><span data-stu-id="4b259-110">For example, this filter skips all tests if the namespace contains IntegrationTests:</span></span>

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> <span data-ttu-id="4b259-111">La barra diagonal inversa precede al signo de exclamación para indicar que es un carácter de escape `\!`.</span><span class="sxs-lookup"><span data-stu-id="4b259-111">The backslash precedes the exclamation mark to indicate it is an escaped character `\!`.</span></span>

<span data-ttu-id="4b259-112">En el caso de los valores `FullyQualifiedName` que incluyen una coma para los parámetros de tipo genérico, escape la coma con `%2C`.</span><span class="sxs-lookup"><span data-stu-id="4b259-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="4b259-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b259-113">For example:</span></span>

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

| <span data-ttu-id="4b259-114">Expresión</span><span class="sxs-lookup"><span data-stu-id="4b259-114">Expression</span></span> | <span data-ttu-id="4b259-115">Resultado</span><span class="sxs-lookup"><span data-stu-id="4b259-115">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="4b259-116">Ejecuta pruebas cuyo <xref:System.Reflection.Module.FullyQualifiedName> contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="4b259-116">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="4b259-117">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="4b259-117">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="4b259-118">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-118">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="4b259-119">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-119">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="4b259-120">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTest1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="4b259-120">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="4b259-121">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-121">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="4b259-122">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="4b259-122">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="4b259-123">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="4b259-123">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="4b259-124">Ejemplos de uso de los operadores condicionales `|` y `&`:</span><span class="sxs-lookup"><span data-stu-id="4b259-124">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="4b259-125">Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **o** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> es `"CategoryA"`.</span><span class="sxs-lookup"><span data-stu-id="4b259-125">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> is `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="4b259-126">Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **y** tienen un elemento <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> de `"CategoryA"`.</span><span class="sxs-lookup"><span data-stu-id="4b259-126">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="4b259-127">Para ejecutar pruebas que tienen <xref:System.Reflection.Module.FullyQualifiedName> con `UnitTest1` **y** tienen un valor <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> de `"CategoryA"` **o** tienen un elemento <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> con una prioridad de `1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-127">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"` **or** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> with a priority of `1`.</span></span>

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

| <span data-ttu-id="4b259-128">Expresión</span><span class="sxs-lookup"><span data-stu-id="4b259-128">Expression</span></span> | <span data-ttu-id="4b259-129">Resultado</span><span class="sxs-lookup"><span data-stu-id="4b259-129">Result</span></span> |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="4b259-130">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-130">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="4b259-131">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-131">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="4b259-132">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-132">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="4b259-133">En el ejemplo de código, los rasgos definidos con claves `"Category"` y `"Priority"` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="4b259-133">In the code example, the defined traits with keys `"Category"` and `"Priority"` can be used for filtering.</span></span>

| <span data-ttu-id="4b259-134">Expresión</span><span class="sxs-lookup"><span data-stu-id="4b259-134">Expression</span></span> | <span data-ttu-id="4b259-135">Resultado</span><span class="sxs-lookup"><span data-stu-id="4b259-135">Result</span></span> |
|--|--|
| `dotnet test --filter XUnit` | <span data-ttu-id="4b259-136">Ejecuta pruebas cuyo <xref:System.Reflection.Module.FullyQualifiedName> contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="4b259-136">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `XUnit`.</span></span>  <span data-ttu-id="4b259-137">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="4b259-137">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="4b259-138">Ejecuta pruebas que tienen `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="4b259-138">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="4b259-139">Ejemplos de uso de los operadores condicionales `|` y `&`:</span><span class="sxs-lookup"><span data-stu-id="4b259-139">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="4b259-140">Para ejecutar pruebas que tienen `TestClass1` en su <xref:System.Reflection.Module.FullyQualifiedName> **o** tienen un elemento `Trait` con una clave de `"Category"` y el valor de `"CategoryA"`.</span><span class="sxs-lookup"><span data-stu-id="4b259-140">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

<span data-ttu-id="4b259-141">Para ejecutar pruebas que tienen `TestClass1` en su <xref:System.Reflection.Module.FullyQualifiedName> **y** tienen un elemento `Trait` con una clave de `"Category"` y un valor de `"CategoryA"`.</span><span class="sxs-lookup"><span data-stu-id="4b259-141">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

<span data-ttu-id="4b259-142">Para ejecutar pruebas que tienen <xref:System.Reflection.Module.FullyQualifiedName> con `TestClass1` **y** tienen un elemento `Trait` con una clave de `"Category"` y un valor de `"CategoryA"` **o** tienen un elemento `Trait` con una clave de `"Priority"` y un valor de `1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-142">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `TestClass1` **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"` **or** have a `Trait` with a key of `"Priority"` and value of `1`.</span></span>

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

| <span data-ttu-id="4b259-143">Expresión</span><span class="sxs-lookup"><span data-stu-id="4b259-143">Expression</span></span> | <span data-ttu-id="4b259-144">Resultado</span><span class="sxs-lookup"><span data-stu-id="4b259-144">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="4b259-145">Ejecuta pruebas cuyo <xref:System.Reflection.Module.FullyQualifiedName> contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="4b259-145">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="4b259-146">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="4b259-146">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="4b259-147">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-147">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="4b259-148">Ejecuta pruebas que están en la clase `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-148">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="4b259-149">Ejecuta todas las pruebas excepto `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-149">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="4b259-150">Ejecuta pruebas anotadas con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="4b259-150">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="4b259-151">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="4b259-151">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="4b259-152">Ejemplos de uso de los operadores condicionales `|` y `&`:</span><span class="sxs-lookup"><span data-stu-id="4b259-152">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="4b259-153">Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **o** tienen un elemento `Category` de `"CategoryA"`.</span><span class="sxs-lookup"><span data-stu-id="4b259-153">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="4b259-154">Para ejecutar pruebas que tienen `UnitTest1` en su <xref:System.Reflection.Module.FullyQualifiedName> **y** tienen un elemento `Category` de `"CategoryA"`.</span><span class="sxs-lookup"><span data-stu-id="4b259-154">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="4b259-155">Para ejecutar pruebas que tienen <xref:System.Reflection.Module.FullyQualifiedName> con `UnitTest1` **y** tienen un elemento `Category` de `"CategoryA"` **o** tienen un elemento `Property` con un valor `"Priority"` de `1`.</span><span class="sxs-lookup"><span data-stu-id="4b259-155">To run tests that have either a <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a `Category` of `"CategoryA"` **or** have a `Property` with a `"Priority"` of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

<span data-ttu-id="4b259-156">Para obtener más información, vea [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="4b259-156">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

:::zone-end

## <a name="see-also"></a><span data-ttu-id="4b259-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b259-157">See also</span></span>

- [<span data-ttu-id="4b259-158">dotnet test</span><span class="sxs-lookup"><span data-stu-id="4b259-158">dotnet test</span></span>](../tools/dotnet-test.md)
- [<span data-ttu-id="4b259-159">dotnet test --filter</span><span class="sxs-lookup"><span data-stu-id="4b259-159">dotnet test --filter</span></span>](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a><span data-ttu-id="4b259-160">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4b259-160">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4b259-161">Ordenación de pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="4b259-161">Order unit tests</span></span>](order-unit-tests.md)
