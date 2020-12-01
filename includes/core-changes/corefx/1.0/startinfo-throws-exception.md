---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032062"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a><span data-ttu-id="cddfc-101">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="cddfc-101">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>

<span data-ttu-id="cddfc-102">Al leer la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de los procesos que el código no ha iniciado, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="cddfc-102">Reading the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start throws an <xref:System.InvalidOperationException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cddfc-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="cddfc-103">Change description</span></span>

<span data-ttu-id="cddfc-104">En .NET Framework, el acceso a la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> para los procesos que el código no inició devuelve un objeto <xref:System.Diagnostics.ProcessStartInfo> ficticio.</span><span class="sxs-lookup"><span data-stu-id="cddfc-104">In .NET Framework, accessing the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start returns a dummy <xref:System.Diagnostics.ProcessStartInfo> object.</span></span> <span data-ttu-id="cddfc-105">El objeto ficticio contiene los valores predeterminados de todas sus propiedades excepto <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span><span class="sxs-lookup"><span data-stu-id="cddfc-105">The dummy object contains default values for all of its properties except <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span></span>

<span data-ttu-id="cddfc-106">A partir de .NET Core 1,0, si lee la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de un proceso que no se inició (es decir, mediante la llamada a <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="cddfc-106">Starting in .NET Core 1.0, if you read the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for a process that you didn't start (that is, by calling <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), an <xref:System.InvalidOperationException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cddfc-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="cddfc-107">Version introduced</span></span>

<span data-ttu-id="cddfc-108">1.0</span><span class="sxs-lookup"><span data-stu-id="cddfc-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cddfc-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="cddfc-109">Recommended action</span></span>

<span data-ttu-id="cddfc-110">No acceda a la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de los procesos que el código no ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="cddfc-110">Do not access the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start.</span></span> <span data-ttu-id="cddfc-111">Por ejemplo, no lea esta propiedad de los procesos devueltos por <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cddfc-111">For example, don't read this property for processes returned by <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="cddfc-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="cddfc-112">Category</span></span>

<span data-ttu-id="cddfc-113">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="cddfc-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cddfc-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cddfc-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
