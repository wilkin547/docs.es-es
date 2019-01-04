---
title: Ejecución de pruebas unitarias selectivas
description: Cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet en .NET Core.
author: smadala
ms.date: 03/22/2017
ms.custom: seodec18
ms.openlocfilehash: 2ec6dc770f33acc4acea79e60cf6f9c33f1077d8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239948"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="8f996-103">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="8f996-103">Running selective unit tests</span></span>

<span data-ttu-id="8f996-104">Con el comando `dotnet test` en .NET Core, se puede usar una expresión de filtro para ejecutar pruebas selectivas.</span><span class="sxs-lookup"><span data-stu-id="8f996-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="8f996-105">En este artículo se muestra cómo filtrar qué pruebas se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="8f996-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="8f996-106">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="8f996-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="8f996-107">Si está usando `vstest.console.exe`, reemplace `--filter ` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="8f996-107">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="8f996-108">MSTest</span><span class="sxs-lookup"><span data-stu-id="8f996-108">MSTest</span></span>

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

| <span data-ttu-id="8f996-109">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-109">Expression</span></span> | <span data-ttu-id="8f996-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-110">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="8f996-111">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="8f996-111">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="8f996-112">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="8f996-112">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="8f996-113">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-113">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="8f996-114">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-114">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="8f996-115">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTest1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="8f996-115">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="8f996-116">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-116">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="8f996-117">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="8f996-117">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="8f996-118">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="8f996-118">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="8f996-119">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="8f996-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8f996-120">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-120">Expression</span></span> | <span data-ttu-id="8f996-121">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="8f996-122">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8f996-122">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="8f996-123">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8f996-123">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8f996-124">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="8f996-124">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="8f996-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="8f996-125">xUnit</span></span>

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

| <span data-ttu-id="8f996-126">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-126">Expression</span></span> | <span data-ttu-id="8f996-127">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="8f996-128">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="8f996-129">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="8f996-130">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="8f996-131">En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="8f996-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="8f996-132">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-132">Expression</span></span> | <span data-ttu-id="8f996-133">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="8f996-134">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="8f996-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="8f996-135">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="8f996-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="8f996-136">Ejecuta las pruebas que tienen `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="8f996-136">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="8f996-137">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="8f996-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8f996-138">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-138">Expression</span></span> | <span data-ttu-id="8f996-139">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="8f996-140">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8f996-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="8f996-141">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8f996-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8f996-142">Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="8f996-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="8f996-143">NUnit</span><span class="sxs-lookup"><span data-stu-id="8f996-143">NUnit</span></span>

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

| <span data-ttu-id="8f996-144">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-144">Expression</span></span> | <span data-ttu-id="8f996-145">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-145">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="8f996-146">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="8f996-146">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="8f996-147">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="8f996-147">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="8f996-148">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-148">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="8f996-149">Ejecuta pruebas que están en la clase `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-149">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="8f996-150">Ejecuta todas las pruebas excepto `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="8f996-150">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="8f996-151">Ejecuta pruebas anotadas con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="8f996-151">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="8f996-152">Ejecuta pruebas anotadas con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="8f996-152">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="8f996-153">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="8f996-153">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="8f996-154">Expresión</span><span class="sxs-lookup"><span data-stu-id="8f996-154">Expression</span></span> | <span data-ttu-id="8f996-155">Resultado</span><span class="sxs-lookup"><span data-stu-id="8f996-155">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="8f996-156">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8f996-156">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="8f996-157">Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="8f996-157">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="8f996-158">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="8f996-158">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
