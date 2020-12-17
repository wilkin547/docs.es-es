---
title: 'Cambio importante: Environment.OSVersion devuelve la versión correcta del sistema operativo'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde Environment.OSVersion devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.
ms.date: 11/01/2020
ms.openlocfilehash: c810d9a7a028a0c60c30d69e78a9b9c695d933ef
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009526"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="20e62-103">Environment.OSVersion devuelve la versión correcta del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="20e62-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="20e62-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="20e62-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="20e62-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="20e62-105">Change description</span></span>

<span data-ttu-id="20e62-106">En versiones anteriores de .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve una versión del sistema operativo que puede ser incorrecta cuando una aplicación se ejecuta en modo de compatibilidad de Windows.</span><span class="sxs-lookup"><span data-stu-id="20e62-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="20e62-107">Para más información, vea [Notas de la función GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="20e62-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span> <span data-ttu-id="20e62-108">En macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión subyacente del kernel de Darwin.</span><span class="sxs-lookup"><span data-stu-id="20e62-108">On macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the underlying Darwin kernel version.</span></span>

<span data-ttu-id="20e62-109">A partir de .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo para Windows y macOS.</span><span class="sxs-lookup"><span data-stu-id="20e62-109">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system for Windows and macOS.</span></span>

<span data-ttu-id="20e62-110">En la tabla siguiente se muestra la diferencia en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="20e62-110">The following table shows the difference in behavior.</span></span>

|  | <span data-ttu-id="20e62-111">Versiones anteriores de .NET</span><span class="sxs-lookup"><span data-stu-id="20e62-111">Previous .NET versions</span></span> | <span data-ttu-id="20e62-112">.NET 5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="20e62-112">.NET 5+</span></span> |
|--|------------------------|---------|
| <span data-ttu-id="20e62-113">Windows</span><span class="sxs-lookup"><span data-stu-id="20e62-113">Windows</span></span> | <span data-ttu-id="20e62-114">6.2.9200.0</span><span class="sxs-lookup"><span data-stu-id="20e62-114">6.2.9200.0</span></span> | <span data-ttu-id="20e62-115">10.0.19042.0</span><span class="sxs-lookup"><span data-stu-id="20e62-115">10.0.19042.0</span></span> |
| <span data-ttu-id="20e62-116">macOS</span><span class="sxs-lookup"><span data-stu-id="20e62-116">macOS</span></span> | <span data-ttu-id="20e62-117">19.6.0.0</span><span class="sxs-lookup"><span data-stu-id="20e62-117">19.6.0.0</span></span> | <span data-ttu-id="20e62-118">10.15.7</span><span class="sxs-lookup"><span data-stu-id="20e62-118">10.15.7</span></span> |

## <a name="reason-for-change"></a><span data-ttu-id="20e62-119">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="20e62-119">Reason for change</span></span>

<span data-ttu-id="20e62-120">Los usuarios de esta propiedad esperan que devuelva la versión real del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="20e62-120">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="20e62-121">La mayoría de las aplicaciones .NET no especifican su versión compatible en el manifiesto de aplicación y, por tanto, obtienen la versión admitida predeterminada del host dotnet.</span><span class="sxs-lookup"><span data-stu-id="20e62-121">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="20e62-122">Como resultado, la corrección de compatibilidad no suele ser significativa para la aplicación que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="20e62-122">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="20e62-123">Cuando Windows lanza una nueva versión y todavía se está usando un host dotnet anterior, estas aplicaciones pueden obtener una versión incorrecta del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="20e62-123">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="20e62-124">La devolución de la versión real está más alineada con las expectativas de los desarrolladores de esta API.</span><span class="sxs-lookup"><span data-stu-id="20e62-124">Returning the actual version is more inline with developers' expectations of this API.</span></span>

<span data-ttu-id="20e62-125">Con la introducción de <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType> y <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> en .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> ha cambiado a fin de ser coherente para Windows y macOS.</span><span class="sxs-lookup"><span data-stu-id="20e62-125">With the introduction of <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType>, and <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> was changed to be consistent for Windows and macOS.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="20e62-126">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="20e62-126">Version introduced</span></span>

<span data-ttu-id="20e62-127">5.0</span><span class="sxs-lookup"><span data-stu-id="20e62-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="20e62-128">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="20e62-128">Recommended action</span></span>

<span data-ttu-id="20e62-129">Revise y pruebe cualquier código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para asegurarse de que se comporta como espera.</span><span class="sxs-lookup"><span data-stu-id="20e62-129">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="20e62-130">API afectadas</span><span class="sxs-lookup"><span data-stu-id="20e62-130">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
