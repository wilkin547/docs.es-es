---
title: Ejecución de pruebas unitarias selectivas
description: Cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet en .NET Core.
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728179"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="55e8a-103">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="55e8a-103">Run selective unit tests</span></span>

<span data-ttu-id="55e8a-104">Con el comando `dotnet test` en .NET Core, se puede usar una expresión de filtro para ejecutar pruebas selectivas.</span><span class="sxs-lookup"><span data-stu-id="55e8a-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="55e8a-105">En este artículo se muestra cómo filtrar qué pruebas se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="55e8a-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="55e8a-106">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="55e8a-107">Si está usando `vstest.console.exe`, reemplace `--filter` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="55e8a-108">Escape de caracteres</span><span class="sxs-lookup"><span data-stu-id="55e8a-108">Character escaping</span></span>

<span data-ttu-id="55e8a-109">El uso de filtros que incluyen el signo de exclamación (!) en `*nix` requiere el escape debido a que `!` está reservado.</span><span class="sxs-lookup"><span data-stu-id="55e8a-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="55e8a-110">Por ejemplo, este filtro omite todas las pruebas si el espacio de nombres contiene IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="55e8a-111">Observe la barra diagonal inversa que precede al signo de exclamación.</span><span class="sxs-lookup"><span data-stu-id="55e8a-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="55e8a-112">En el caso de los valores `FullyQualifiedName` que incluyen una coma para los parámetros de tipo genérico, escape la coma con `%2C`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="55e8a-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="55e8a-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="55e8a-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="55e8a-114">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="55e8a-115">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-115">Expression</span></span> | <span data-ttu-id="55e8a-116">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="55e8a-117">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="55e8a-118">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="55e8a-119">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="55e8a-120">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="55e8a-121">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTest1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="55e8a-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="55e8a-122">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="55e8a-123">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="55e8a-124">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="55e8a-125">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="55e8a-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="55e8a-126">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-126">Expression</span></span> | <span data-ttu-id="55e8a-127">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="55e8a-128">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="55e8a-129">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="55e8a-130">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="55e8a-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="55e8a-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="55e8a-131">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="55e8a-132">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-132">Expression</span></span> | <span data-ttu-id="55e8a-133">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="55e8a-134">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="55e8a-135">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="55e8a-136">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="55e8a-137">En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="55e8a-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="55e8a-138">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-138">Expression</span></span> | <span data-ttu-id="55e8a-139">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="55e8a-140">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="55e8a-141">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="55e8a-142">Ejecuta pruebas que tienen `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="55e8a-143">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="55e8a-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="55e8a-144">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-144">Expression</span></span> | <span data-ttu-id="55e8a-145">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="55e8a-146">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="55e8a-147">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="55e8a-148">Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="55e8a-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="55e8a-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="55e8a-149">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="55e8a-150">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-150">Expression</span></span> | <span data-ttu-id="55e8a-151">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="55e8a-152">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="55e8a-153">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="55e8a-154">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="55e8a-155">Ejecuta pruebas que están en la clase `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="55e8a-156">Ejecuta todas las pruebas excepto `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="55e8a-157">Ejecuta pruebas anotadas con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="55e8a-158">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="55e8a-159">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="55e8a-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="55e8a-160">Expresión</span><span class="sxs-lookup"><span data-stu-id="55e8a-160">Expression</span></span> | <span data-ttu-id="55e8a-161">Resultado</span><span class="sxs-lookup"><span data-stu-id="55e8a-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="55e8a-162">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="55e8a-163">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e8a-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="55e8a-164">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="55e8a-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="55e8a-165">Para obtener más información, vea [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="55e8a-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
