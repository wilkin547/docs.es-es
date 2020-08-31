---
ms.openlocfilehash: a635e2ed6a735b5234c92fd8f5ffa1685fe9373e
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558193"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="64504-101">Retirada del paquete Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="64504-101">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="64504-102">No se crearán nuevas versiones del [paquete Microsoft.DotNet.PlatformAbstractions de NuGet](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/).</span><span class="sxs-lookup"><span data-stu-id="64504-102">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

#### <a name="change-description"></a><span data-ttu-id="64504-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="64504-103">Change description</span></span>

<span data-ttu-id="64504-104">Anteriormente, junto a las nuevas versiones de .NET Core, también se producían nuevas versiones de la biblioteca <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="64504-104">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="64504-105">En el futuro, no se agregarán funcionalidades nuevas a la biblioteca ni se publicarán nuevas versiones principales.</span><span class="sxs-lookup"><span data-stu-id="64504-105">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="64504-106">No obstante, las versiones existentes de la biblioteca seguirán funcionando y recibirán mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="64504-106">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="64504-107">La biblioteca <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> se superpone a las API que ya están establecidas en los espacios de nombres System.\*</span><span class="sxs-lookup"><span data-stu-id="64504-107">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="64504-108">Además, algunas API <xref:Microsoft.DotNet.PlatformAbstractions> no se diseñaron con el mismo nivel de escrutinio y compatibilidad a largo plazo que el resto de las API System.\* .</span><span class="sxs-lookup"><span data-stu-id="64504-108">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="64504-109">Por ejemplo, <xref:Microsoft.DotNet.PlatformAbstractions> usa la enumeración `Platform` para describir la plataforma actual del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="64504-109">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="64504-110">Este diseño de enumeración se rechazó explícitamente cuando se diseñó la API <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> con el fin de admitir plataformas nuevas y favorecer la flexibilidad en el futuro.</span><span class="sxs-lookup"><span data-stu-id="64504-110">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="64504-111">Los escenarios habilitados por la biblioteca <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> ahora son posibles sin la enumeración.</span><span class="sxs-lookup"><span data-stu-id="64504-111">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="64504-112">Las versiones existentes seguirán funcionando, incluso en .NET 5.0 y versiones posteriores, y recibirán mantenimiento junto con las versiones anteriores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="64504-112">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="64504-113">No obstante, no se agregarán nuevas funcionalidades a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="64504-113">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="64504-114">En cambio, las otras bibliotecas y API sí recibirán nuevas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="64504-114">Instead, new functionality will be added to other libraries and APIs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="64504-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="64504-115">Version introduced</span></span>

<span data-ttu-id="64504-116">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="64504-116">5.0 Preview 6</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64504-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="64504-117">Recommended action</span></span>

- <span data-ttu-id="64504-118">Puede seguir usando versiones anteriores de la biblioteca si cumplen sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="64504-118">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="64504-119">En caso de que las versiones anteriores no satisfagan sus necesidades, reemplace los usos de las API `PlatformAbstractions` por las opciones de reemplazo recomendadas.</span><span class="sxs-lookup"><span data-stu-id="64504-119">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="64504-120">API `PlatformAbstractions`</span><span class="sxs-lookup"><span data-stu-id="64504-120">`PlatformAbstractions` API</span></span> | <span data-ttu-id="64504-121">Reemplazo recomendado</span><span class="sxs-lookup"><span data-stu-id="64504-121">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="64504-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> y <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="64504-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="64504-123">La finalidad de la mayoría de los casos de uso de `RuntimeEnvironment.OperatingSystem` y `RuntimeEnvironment.OperatingSystemVersion` es de visualización (por ejemplo, mostrar a un usuario el registro y la telemetría).</span><span class="sxs-lookup"><span data-stu-id="64504-123">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="64504-124">No se recomienda tomar decisiones en tiempo de ejecución basadas en una versión del sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="64504-124">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="64504-125">Ahora, <xref:System.Environment.OSVersion?displayProperty=nameWithType> [devuelve la versión correcta](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version) para los sistemas operativos Windows y macOS.</span><span class="sxs-lookup"><span data-stu-id="64504-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now [returns the correct version](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version) for Windows and macOS operating systems.</span></span> <span data-ttu-id="64504-126">En cambio, para la mayoría de las distribuciones de UNIX, no queda tan claro lo que se considera "versión del sistema operativo".</span><span class="sxs-lookup"><span data-stu-id="64504-126">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="64504-127">Por ejemplo, podría ser la versión del kernel de Linux o podría ser la versión de distribución.</span><span class="sxs-lookup"><span data-stu-id="64504-127">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="64504-128">En la mayoría de las plataformas UNIX, <xref:System.Environment.OSVersion?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> devuelven la versión devuelta por `uname`.</span><span class="sxs-lookup"><span data-stu-id="64504-128">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="64504-129">Para obtener el nombre y la versión de la distribución de Linux, lo recomendado es leer el archivo */etc/os-release*.</span><span class="sxs-lookup"><span data-stu-id="64504-129">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

#### <a name="category"></a><span data-ttu-id="64504-130">Categoría</span><span class="sxs-lookup"><span data-stu-id="64504-130">Category</span></span>

<span data-ttu-id="64504-131">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="64504-131">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64504-132">API afectadas</span><span class="sxs-lookup"><span data-stu-id="64504-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
