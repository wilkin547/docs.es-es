---
title: 'Cambio importante: Las API de caché global de ensamblados están obsoletas'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde las API que controlan la GAC generan un error o no realizan ninguna operación.
ms.date: 11/01/2020
ms.openlocfilehash: 39c7b092b06754a28723693c0147b7ec3a0b705e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257484"
---
# <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="4e9e9-103">Las API de caché global de ensamblados están obsoletas</span><span class="sxs-lookup"><span data-stu-id="4e9e9-103">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="4e9e9-104">.NET Core y .NET 5 y versiones posteriores eliminan el concepto de caché global de ensamblados (GAC) presente en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-104">.NET Core and .NET 5 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="4e9e9-105">Por lo tanto, todas las API de .NET Core y .NET 5+ que se ocupan de GAC producen errores o no hacen nada.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-105">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="4e9e9-106">Para ayudar a los desarrolladores a apartarse de estas API, algunas relacionadas con GAC se han marcado como obsoletas y generan una advertencia `SYSLIB0005` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-106">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="4e9e9-107">Estas API podrían eliminarse en una próxima versión de .NET.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-107">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="4e9e9-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="4e9e9-108">Change description</span></span>

<span data-ttu-id="4e9e9-109">Las siguientes API se han marcado como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-109">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="4e9e9-110">API</span><span class="sxs-lookup"><span data-stu-id="4e9e9-110">API</span></span> | <span data-ttu-id="4e9e9-111">Marcada como obsoleta en...</span><span class="sxs-lookup"><span data-stu-id="4e9e9-111">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="4e9e9-112">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="4e9e9-112">5.0 RC1</span></span> |

<span data-ttu-id="4e9e9-113">En .NET Framework 2.x-4.x, la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache> devuelve `true` si el ensamblado consultado se ha cargado desde GAC y `false` si se ha cargado desde otra ubicación en el disco.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-113">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="4e9e9-114">En .NET Core 2.x-3.x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> siempre devuelve `false`, lo que refleja que GAC no existe en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-114">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="4e9e9-115">En .NET 5 y versiones posteriores, la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache> sigue devolviendo `false`.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-115">In .NET 5 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="4e9e9-116">Pero el captador de propiedad también se ha marcado como obsoleto para indicar a los autores de llamadas que deben dejar de acceder a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-116">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="4e9e9-117">Las bibliotecas y aplicaciones no deben usar la API <xref:System.Reflection.Assembly.GlobalAssemblyCache> para realizar determinaciones sobre el comportamiento en tiempo de ejecución, ya que siempre devuelve `false` en .NET Core y .NET 5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-117">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="4e9e9-118">Se trata de un cambio solo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-118">This is a compile-time only change.</span></span> <span data-ttu-id="4e9e9-119">No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-119">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4e9e9-120">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="4e9e9-120">Reason for change</span></span>

<span data-ttu-id="4e9e9-121">La caché global de ensamblados (GAC) no existe como concepto en .NET Core y .NET 5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-121">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5 and later versions.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4e9e9-122">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4e9e9-122">Version introduced</span></span>

<span data-ttu-id="4e9e9-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4e9e9-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4e9e9-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4e9e9-124">Recommended action</span></span>

- <span data-ttu-id="4e9e9-125">Si la aplicación consulta a la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache>, considere la posibilidad de eliminar la llamada.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-125">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="4e9e9-126">Si usa el valor <xref:System.Reflection.Assembly.GlobalAssemblyCache> para elegir entre un flujo de "ensamblado en GAC" frente a un flujo de "ensamblado no en GAC" en tiempo de ejecución, vuelva a considerar si el flujo sigue teniendo sentido para una aplicación .NET Core o .NET 5.0+.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-126">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="4e9e9-127">Si tiene que seguir usando las API obsoletas, puede suprimir la advertencia `SYSLIB0005` en el código.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="4e9e9-128">También puede suprimir la advertencia en el archivo del proyecto, lo que la deshabilita en todos los archivos de código fuente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="4e9e9-129">La supresión de `SYSLIB0005` solo deshabilita la advertencia de obsolescencia <xref:System.Reflection.Assembly.GlobalAssemblyCache>.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-129">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="4e9e9-130">No se deshabilita ninguna otra advertencia.</span><span class="sxs-lookup"><span data-stu-id="4e9e9-130">It does not disable any other warnings.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4e9e9-131">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4e9e9-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
