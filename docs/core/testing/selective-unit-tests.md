---
title: Ejecución de pruebas unitarias selectivas
description: Cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet en .NET Core.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543513"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="e7d6a-103">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="e7d6a-103">Running selective unit tests</span></span>

<span data-ttu-id="e7d6a-104">Con el comando `dotnet test` en .NET Core, se puede usar una expresión de filtro para ejecutar pruebas selectivas.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="e7d6a-105">En este artículo se muestra cómo filtrar qué pruebas se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="e7d6a-106">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="e7d6a-107">Si está usando `vstest.console.exe`, reemplace `--filter` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d6a-108">El uso de filtros que incluyen el signo de exclamación (!) en `*nix` requiere el escape debido a que `!` está reservado.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="e7d6a-109">Por ejemplo, este filtro omite todas las pruebas si el espacio de nombres contiene IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="e7d6a-110">Observe la barra diagonal inversa que precede al signo de exclamación.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="e7d6a-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="e7d6a-111">MSTest</span></span>

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

| <span data-ttu-id="e7d6a-112">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-112">Expression</span></span> | <span data-ttu-id="e7d6a-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="e7d6a-114">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="e7d6a-115">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="e7d6a-116">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="e7d6a-117">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="e7d6a-118">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTest1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="e7d6a-119">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="e7d6a-120">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="e7d6a-121">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="e7d6a-122">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="e7d6a-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="e7d6a-123">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-123">Expression</span></span> | <span data-ttu-id="e7d6a-124">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="e7d6a-125">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="e7d6a-126">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="e7d6a-127">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="e7d6a-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="e7d6a-128">xUnit</span></span>

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

| <span data-ttu-id="e7d6a-129">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-129">Expression</span></span> | <span data-ttu-id="e7d6a-130">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="e7d6a-131">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="e7d6a-132">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="e7d6a-133">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="e7d6a-134">En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="e7d6a-135">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-135">Expression</span></span> | <span data-ttu-id="e7d6a-136">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="e7d6a-137">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="e7d6a-138">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="e7d6a-139">Ejecuta las pruebas que tienen `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="e7d6a-140">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="e7d6a-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="e7d6a-141">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-141">Expression</span></span> | <span data-ttu-id="e7d6a-142">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="e7d6a-143">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="e7d6a-144">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="e7d6a-145">Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="e7d6a-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="e7d6a-146">NUnit</span></span>

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

| <span data-ttu-id="e7d6a-147">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-147">Expression</span></span> | <span data-ttu-id="e7d6a-148">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="e7d6a-149">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="e7d6a-150">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="e7d6a-151">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="e7d6a-152">Ejecuta pruebas que están en la clase `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="e7d6a-153">Ejecuta todas las pruebas excepto `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="e7d6a-154">Ejecuta pruebas anotadas con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="e7d6a-155">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="e7d6a-156">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="e7d6a-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="e7d6a-157">Expresión</span><span class="sxs-lookup"><span data-stu-id="e7d6a-157">Expression</span></span> | <span data-ttu-id="e7d6a-158">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7d6a-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="e7d6a-159">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="e7d6a-160">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="e7d6a-161">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="e7d6a-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
