---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420438"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a><span data-ttu-id="b1667-101">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="b1667-101">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>

<span data-ttu-id="b1667-102">Al leer la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de los procesos que el código no ha iniciado, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="b1667-102">Reading the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start throws an <xref:System.InvalidOperationException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b1667-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b1667-103">Change description</span></span>

<span data-ttu-id="b1667-104">En .NET Framework, el acceso a la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> para los procesos que el código no inició devuelve un objeto <xref:System.Diagnostics.ProcessStartInfo> ficticio.</span><span class="sxs-lookup"><span data-stu-id="b1667-104">In .NET Framework, accessing the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start returns a dummy <xref:System.Diagnostics.ProcessStartInfo> object.</span></span> <span data-ttu-id="b1667-105">El objeto ficticio contiene los valores predeterminados de todas sus propiedades excepto <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span><span class="sxs-lookup"><span data-stu-id="b1667-105">The dummy object contains default values for all of its properties except <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span></span>

<span data-ttu-id="b1667-106">A partir de .NET Core 1,0, si lee la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de un proceso que no se inició (es decir, mediante la llamada a <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="b1667-106">Starting in .NET Core 1.0, if you read the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for a process that you didn't start (that is, by calling <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), an <xref:System.InvalidOperationException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b1667-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b1667-107">Version introduced</span></span>

<span data-ttu-id="b1667-108">1.0</span><span class="sxs-lookup"><span data-stu-id="b1667-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b1667-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b1667-109">Recommended action</span></span>

<span data-ttu-id="b1667-110">No acceda a la propiedad <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> de los procesos que el código no ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="b1667-110">Do not access the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start.</span></span> <span data-ttu-id="b1667-111">Por ejemplo, no lea esta propiedad de los procesos devueltos por <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1667-111">For example, don't read this property for processes returned by <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="b1667-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="b1667-112">Category</span></span>

<span data-ttu-id="b1667-113">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="b1667-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b1667-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b1667-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
