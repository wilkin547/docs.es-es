---
title: 'Cambio importante: Las API de comunicación remota están obsoletas'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde algunas API relacionadas con la comunicación remota están marcadas como obsoletas y generan una advertencia con un identificador de diagnóstico personalizado.
ms.date: 11/01/2020
ms.openlocfilehash: 3c4f7cd200cadd11321da60f2b4a0d191497aae8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257175"
---
# <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="65192-103">Las API de comunicación remota están obsoletas</span><span class="sxs-lookup"><span data-stu-id="65192-103">Remoting APIs are obsolete</span></span>

<span data-ttu-id="65192-104">Algunas API relacionadas con la comunicación remota se han marcado como obsoletas y generan una advertencia `SYSLIB0010` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="65192-104">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="65192-105">Estas API podrían eliminarse en una próxima versión de .NET.</span><span class="sxs-lookup"><span data-stu-id="65192-105">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="65192-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="65192-106">Change description</span></span>

<span data-ttu-id="65192-107">Las siguientes API de comunicación remota se han marcado como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="65192-107">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="65192-108">API</span><span class="sxs-lookup"><span data-stu-id="65192-108">API</span></span> | <span data-ttu-id="65192-109">Marcada como obsoleta en...</span><span class="sxs-lookup"><span data-stu-id="65192-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="65192-110">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="65192-110">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="65192-111">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="65192-111">5.0 RC1</span></span> |

<span data-ttu-id="65192-112">En .NET Framework 2.x-4.x, los métodos <xref:System.MarshalByRefObject.GetLifetimeService> y <xref:System.MarshalByRefObject.InitializeLifetimeService> controlan la duración de las instancias implicadas con .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="65192-112">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="65192-113">En .NET Core 2.x-3.x, estos métodos siempre producen una <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="65192-113">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="65192-114">En .NET 5 y versiones posteriores, los métodos <xref:System.MarshalByRefObject.GetLifetimeService> y <xref:System.MarshalByRefObject.InitializeLifetimeService> se han marcado como obsoletos como advertencia, pero siguen produciendo una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="65192-114">In .NET 5 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="65192-115">Se trata de un cambio solo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="65192-115">This is a compile-time only change.</span></span> <span data-ttu-id="65192-116">No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="65192-116">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="65192-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="65192-117">Reason for change</span></span>

<span data-ttu-id="65192-118">[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) es una tecnología heredada.</span><span class="sxs-lookup"><span data-stu-id="65192-118">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="65192-119">Permite crear instancias de un objeto en otro proceso (potencialmente incluso en otra máquina) e interactuar con ese objeto como si fuera una instancia de objeto .NET normal en proceso.</span><span class="sxs-lookup"><span data-stu-id="65192-119">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="65192-120">La infraestructura de .NET Remoting solo existe en .NET Framework 2.x-4.x.</span><span class="sxs-lookup"><span data-stu-id="65192-120">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="65192-121">.NET Core y .NET 5 y versiones posteriores no tienen compatibilidad con .NET Remoting, y las API de comunicación remota o no existen o siempre producen excepciones en estos entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="65192-121">.NET Core and .NET 5 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="65192-122">Para ayudar a los desarrolladores a apartarse de estas API, se están marcando como obsoletas API seleccionadas relacionadas con la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="65192-122">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="65192-123">Estas API podrían eliminarse por completo en una próxima versión de .NET.</span><span class="sxs-lookup"><span data-stu-id="65192-123">These APIs may be removed entirely in a future version of .NET.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="65192-124">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="65192-124">Version introduced</span></span>

<span data-ttu-id="65192-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="65192-125">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="65192-126">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="65192-126">Recommended action</span></span>

- <span data-ttu-id="65192-127">Considere la posibilidad de usar servicios REST basados en WCF o HTTP para comunicarse con objetos de otras aplicaciones o entre máquinas.</span><span class="sxs-lookup"><span data-stu-id="65192-127">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="65192-128">Para obtener más información, vea [Tecnologías de .NET Framework no disponibles en .NET Core](../../../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="65192-128">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="65192-129">Si tiene que seguir usando las API obsoletas, puede suprimir la advertencia `SYSLIB0010` en el código.</span><span class="sxs-lookup"><span data-stu-id="65192-129">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="65192-130">También puede suprimir la advertencia en el archivo del proyecto, lo que la deshabilita en todos los archivos de código fuente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="65192-130">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="65192-131">La supresión de `SYSLIB0010` solo deshabilita las advertencias de obsolescencia de la API de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="65192-131">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="65192-132">No se deshabilita ninguna otra advertencia.</span><span class="sxs-lookup"><span data-stu-id="65192-132">It does not disable any other warnings.</span></span> <span data-ttu-id="65192-133">Además, no cambia el comportamiento codificado en tiempo de ejecución de producir siempre una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="65192-133">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="65192-134">API afectadas</span><span class="sxs-lookup"><span data-stu-id="65192-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
