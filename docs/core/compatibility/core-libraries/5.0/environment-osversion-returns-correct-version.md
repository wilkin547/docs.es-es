---
title: 'Cambio importante: Environment.OSVersion devuelve la versión correcta del sistema operativo'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde Environment.OSVersion devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760286"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="7a919-103">Environment.OSVersion devuelve la versión correcta del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7a919-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="7a919-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo en lugar de, por ejemplo, el sistema operativo seleccionado para la compatibilidad de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7a919-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="7a919-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7a919-105">Change description</span></span>

<span data-ttu-id="7a919-106">En versiones anteriores de .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve una versión del sistema operativo que puede ser incorrecta cuando una aplicación se ejecuta en modo de compatibilidad de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a919-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="7a919-107">Para más información, vea [Notas de la función GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="7a919-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="7a919-108">A partir de .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> devuelve la versión real del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7a919-108">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7a919-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7a919-109">Reason for change</span></span>

<span data-ttu-id="7a919-110">Los usuarios de esta propiedad esperan que devuelva la versión real del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7a919-110">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="7a919-111">La mayoría de las aplicaciones .NET no especifican su versión compatible en el manifiesto de aplicación y, por tanto, obtienen la versión admitida predeterminada del host dotnet.</span><span class="sxs-lookup"><span data-stu-id="7a919-111">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="7a919-112">Como resultado, la corrección de compatibilidad no suele ser significativa para la aplicación que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="7a919-112">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="7a919-113">Cuando Windows lanza una nueva versión y todavía se está usando un host dotnet anterior, estas aplicaciones pueden obtener una versión incorrecta del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7a919-113">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="7a919-114">La devolución de la versión real está más alineada con las expectativas de los desarrolladores de esta API.</span><span class="sxs-lookup"><span data-stu-id="7a919-114">Returning the actual version is more inline with developers' expectations of this API.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7a919-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7a919-115">Version introduced</span></span>

<span data-ttu-id="7a919-116">5.0</span><span class="sxs-lookup"><span data-stu-id="7a919-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7a919-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7a919-117">Recommended action</span></span>

<span data-ttu-id="7a919-118">Revise y pruebe cualquier código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para asegurarse de que se comporta como espera.</span><span class="sxs-lookup"><span data-stu-id="7a919-118">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7a919-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7a919-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
