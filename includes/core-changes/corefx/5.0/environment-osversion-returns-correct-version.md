---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558194"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="153e6-101">Environment.OSVersion devuelve la versión correcta del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="153e6-101">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="153e6-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="153e6-102"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

#### <a name="change-description"></a><span data-ttu-id="153e6-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="153e6-103">Change description</span></span>

<span data-ttu-id="153e6-104">En versiones anteriores de .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve una versión del sistema operativo que puede ser incorrecta cuando una aplicación se ejecuta en modo de compatibilidad de Windows.</span><span class="sxs-lookup"><span data-stu-id="153e6-104">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="153e6-105">Para más información, vea [Notas de la función GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="153e6-105">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="153e6-106">A partir de .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="153e6-106">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="153e6-107">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="153e6-107">Reason for change</span></span>

<span data-ttu-id="153e6-108">Los usuarios de esta propiedad esperan que devuelva la versión real del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="153e6-108">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="153e6-109">La mayoría de las aplicaciones .NET no especifican su versión compatible en el manifiesto de aplicación y, por tanto, obtienen la versión admitida predeterminada del host dotnet.</span><span class="sxs-lookup"><span data-stu-id="153e6-109">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="153e6-110">Como resultado, la corrección de compatibilidad no suele ser significativa para la aplicación que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="153e6-110">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="153e6-111">Cuando Windows lanza una nueva versión y todavía se está usando un host dotnet anterior, estas aplicaciones pueden obtener una versión incorrecta del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="153e6-111">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="153e6-112">La devolución de la versión real está más alineada con las expectativas de los desarrolladores de esta API.</span><span class="sxs-lookup"><span data-stu-id="153e6-112">Returning the actual version is more inline with developers' expectations of this API.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="153e6-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="153e6-113">Version introduced</span></span>

<span data-ttu-id="153e6-114">5.0</span><span class="sxs-lookup"><span data-stu-id="153e6-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="153e6-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="153e6-115">Recommended action</span></span>

<span data-ttu-id="153e6-116">Revise y pruebe cualquier código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para asegurarse de que se comporta como espera.</span><span class="sxs-lookup"><span data-stu-id="153e6-116">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

#### <a name="category"></a><span data-ttu-id="153e6-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="153e6-117">Category</span></span>

<span data-ttu-id="153e6-118">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="153e6-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="153e6-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="153e6-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
