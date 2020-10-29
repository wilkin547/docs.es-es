---
ms.openlocfilehash: 35041a035041fd4ad5402e1bc0dd137a74d4f949
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434926"
---
### <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="d79df-101">Las API de comunicación remota están obsoletas</span><span class="sxs-lookup"><span data-stu-id="d79df-101">Remoting APIs are obsolete</span></span>

<span data-ttu-id="d79df-102">Algunas API relacionadas con la comunicación remota se han marcado como obsoletas y generan una advertencia `SYSLIB0010` en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d79df-102">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="d79df-103">Estas API podrían eliminarse en una próxima versión de .NET.</span><span class="sxs-lookup"><span data-stu-id="d79df-103">These APIs may be removed in a future version of .NET.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d79df-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d79df-104">Change description</span></span>

<span data-ttu-id="d79df-105">Las siguientes API de comunicación remota se han marcado como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="d79df-105">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="d79df-106">API</span><span class="sxs-lookup"><span data-stu-id="d79df-106">API</span></span> | <span data-ttu-id="d79df-107">Marcada como obsoleta en...</span><span class="sxs-lookup"><span data-stu-id="d79df-107">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="d79df-108">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="d79df-108">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="d79df-109">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="d79df-109">5.0 RC1</span></span> |

<span data-ttu-id="d79df-110">En .NET Framework 2.x-4.x, los métodos <xref:System.MarshalByRefObject.GetLifetimeService> y <xref:System.MarshalByRefObject.InitializeLifetimeService> controlan la duración de las instancias implicadas con .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="d79df-110">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="d79df-111">En .NET Core 2.x-3.x, estos métodos siempre producen una <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d79df-111">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="d79df-112">En .NET 5.0 y versiones posteriores, los métodos <xref:System.MarshalByRefObject.GetLifetimeService> y <xref:System.MarshalByRefObject.InitializeLifetimeService> se han marcado como obsoletos como advertencia, pero siguen produciendo una <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d79df-112">In .NET 5.0 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="d79df-113">Se trata de un cambio solo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d79df-113">This is a compile-time only change.</span></span> <span data-ttu-id="d79df-114">No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d79df-114">There is no run-time change from previous versions of .NET Core.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d79df-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d79df-115">Reason for change</span></span>

<span data-ttu-id="d79df-116">[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) es una tecnología heredada.</span><span class="sxs-lookup"><span data-stu-id="d79df-116">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="d79df-117">Permite crear instancias de un objeto en otro proceso (potencialmente incluso en otra máquina) e interactuar con ese objeto como si fuera una instancia de objeto .NET normal en proceso.</span><span class="sxs-lookup"><span data-stu-id="d79df-117">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="d79df-118">La infraestructura de .NET Remoting solo existe en .NET Framework 2.x-4.x.</span><span class="sxs-lookup"><span data-stu-id="d79df-118">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="d79df-119">.NET Core y .NET 5.0 y versiones posteriores no tienen compatibilidad con .NET Remoting, y las API de comunicación remota o no existen o siempre producen excepciones en estos entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d79df-119">.NET Core and .NET 5.0 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="d79df-120">Para ayudar a los desarrolladores a apartarse de estas API, se están marcando como obsoletas API seleccionadas relacionadas con la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="d79df-120">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="d79df-121">Estas API podrían eliminarse por completo en una próxima versión de .NET.</span><span class="sxs-lookup"><span data-stu-id="d79df-121">These APIs may be removed entirely in a future version of .NET.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d79df-122">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d79df-122">Version introduced</span></span>

<span data-ttu-id="d79df-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d79df-123">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d79df-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d79df-124">Recommended action</span></span>

- <span data-ttu-id="d79df-125">Considere la posibilidad de usar servicios REST basados en WCF o HTTP para comunicarse con objetos de otras aplicaciones o entre máquinas.</span><span class="sxs-lookup"><span data-stu-id="d79df-125">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="d79df-126">Para obtener más información, vea [Tecnologías de .NET Framework no disponibles en .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="d79df-126">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="d79df-127">Si tiene que seguir usando las API obsoletas, puede suprimir la advertencia `SYSLIB0010` en el código.</span><span class="sxs-lookup"><span data-stu-id="d79df-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="d79df-128">También puede suprimir la advertencia en el archivo del proyecto, lo que la deshabilita en todos los archivos de código fuente del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d79df-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="d79df-129">La supresión de `SYSLIB0010` solo deshabilita las advertencias de obsolescencia de la API de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="d79df-129">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="d79df-130">No se deshabilita ninguna otra advertencia.</span><span class="sxs-lookup"><span data-stu-id="d79df-130">It does not disable any other warnings.</span></span> <span data-ttu-id="d79df-131">Además, no cambia el comportamiento codificado en tiempo de ejecución de producir siempre una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="d79df-131">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="d79df-132">Categoría</span><span class="sxs-lookup"><span data-stu-id="d79df-132">Category</span></span>

<span data-ttu-id="d79df-133">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="d79df-133">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d79df-134">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d79df-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
