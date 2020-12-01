---
ms.openlocfilehash: 9544b65f31772d0f4cee918528a73171fec4de99
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032051"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="46dbf-101">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="46dbf-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="46dbf-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> tiene un valor predeterminado de `false` en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46dbf-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="46dbf-103">En .NET Framework, su valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="46dbf-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="46dbf-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="46dbf-104">Change description</span></span>

<span data-ttu-id="46dbf-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> permite iniciar una aplicación directamente, por ejemplo, con código como `Process.Start("mspaint.exe")` que inicia Paint.</span><span class="sxs-lookup"><span data-stu-id="46dbf-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="46dbf-106">También permite iniciar indirectamente una aplicación asociada si <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="46dbf-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="46dbf-107">En .NET Framework, el valor predeterminado de <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> es `true`, lo que significa que código como `Process.Start("mytextfile.txt")` iniciaría el Bloc de notas, si ha asociado archivos *.txt* con ese editor.</span><span class="sxs-lookup"><span data-stu-id="46dbf-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="46dbf-108">Para evitar el inicio indirecto de una aplicación en .NET Framework, debe establecer explícitamente <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> en `false`.</span><span class="sxs-lookup"><span data-stu-id="46dbf-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="46dbf-109">En .NET Core, el valor predeterminado de <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="46dbf-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="46dbf-110">Esto significa que, de forma predeterminada, las aplicaciones asociadas no se inician cuando se llama a `Process.Start`.</span><span class="sxs-lookup"><span data-stu-id="46dbf-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="46dbf-111">Este cambio se introdujo en .NET Core por motivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="46dbf-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="46dbf-112">Normalmente, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> se usa para iniciar una aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="46dbf-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="46dbf-113">Iniciar una aplicación directamente no implica el uso del shell de Windows e incurrir en el costo de rendimiento asociado.</span><span class="sxs-lookup"><span data-stu-id="46dbf-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="46dbf-114">Para que este caso predeterminado sea más rápido, .NET Core cambia el valor predeterminado de <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> por `false`.</span><span class="sxs-lookup"><span data-stu-id="46dbf-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="46dbf-115">Puede optar por la ruta de acceso más lenta si lo necesita.</span><span class="sxs-lookup"><span data-stu-id="46dbf-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="46dbf-116">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="46dbf-116">Version introduced</span></span>

<span data-ttu-id="46dbf-117">2.1</span><span class="sxs-lookup"><span data-stu-id="46dbf-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="46dbf-118">En versiones anteriores de .NET Core, no se implementaba `UseShellExecute` para Windows.</span><span class="sxs-lookup"><span data-stu-id="46dbf-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="46dbf-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="46dbf-119">Recommended action</span></span>

<span data-ttu-id="46dbf-120">Si la aplicación se basa en el comportamiento anterior, llame a <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> con <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> establecido en `true` en el objeto <xref:System.Diagnostics.ProcessStartInfo>.</span><span class="sxs-lookup"><span data-stu-id="46dbf-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="46dbf-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="46dbf-121">Category</span></span>

<span data-ttu-id="46dbf-122">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="46dbf-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="46dbf-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="46dbf-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
