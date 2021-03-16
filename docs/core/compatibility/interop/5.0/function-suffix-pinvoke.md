---
title: 'Cambio importante: No se incluye el sondeo del sufijo A/W en plataformas que no son de Windows'
description: Obtenga información sobre el cambio de interoperabilidad en .NET 5, donde los sufijos ya no se agregan a los nombres de exportación de función durante el sondeo de P/Invoke en plataformas que no son de Windows.
ms.date: 08/13/2020
ms.openlocfilehash: 924cbcb6c432e2f7c52c7218d48a938b61306c9c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256626"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="69ea3-103">No se incluye el sondeo del sufijo A/W en plataformas que no son de Windows</span><span class="sxs-lookup"><span data-stu-id="69ea3-103">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="69ea3-104">Los runtimes de .NET ya no agregan un sufijo `A` o `W` a los nombres de exportación de funciones durante el sondeo de P/Invoke en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="69ea3-104">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="69ea3-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="69ea3-105">Version introduced</span></span>

<span data-ttu-id="69ea3-106">5.0</span><span class="sxs-lookup"><span data-stu-id="69ea3-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="69ea3-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="69ea3-107">Change description</span></span>

<span data-ttu-id="69ea3-108">[Windows tiene la convención](/windows/win32/intl/conventions-for-function-prototypes) de agregar un sufijo `A` o `W` a los nombres de función de Windows SDK. Estos prefijos corresponden a la página de códigos de Windows y a las versiones de Unicode respectivamente.</span><span class="sxs-lookup"><span data-stu-id="69ea3-108">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="69ea3-109">En versiones anteriores de .NET, los runtimes de CoreCLR y Mono agregan un sufijo `A` o `W` al nombre de la exportación durante la detección de exportación para P/Invokes *en todas las plataformas*.</span><span class="sxs-lookup"><span data-stu-id="69ea3-109">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="69ea3-110">En .NET 5 y versiones posteriores, se agrega un sufijo `A` o `W` al nombre de la exportación durante la detección de exportación *solo en Windows*.</span><span class="sxs-lookup"><span data-stu-id="69ea3-110">In .NET 5 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="69ea3-111">En las plataformas UNIX, no se agrega el sufijo.</span><span class="sxs-lookup"><span data-stu-id="69ea3-111">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="69ea3-112">La semántica de los runtimes en la plataforma de Windows no se modifica.</span><span class="sxs-lookup"><span data-stu-id="69ea3-112">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="69ea3-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="69ea3-113">Reason for change</span></span>

<span data-ttu-id="69ea3-114">Este cambio se ha realizado para simplificar el sondeo entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="69ea3-114">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="69ea3-115">Es algo de lo que no habría que preocuparse, ya que las plataformas que no son de Windows no contienen esta semántica.</span><span class="sxs-lookup"><span data-stu-id="69ea3-115">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="69ea3-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="69ea3-116">Recommended action</span></span>

<span data-ttu-id="69ea3-117">Para mitigar el cambio, puede agregar manualmente el sufijo deseado en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="69ea3-117">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="69ea3-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="69ea3-118">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a><span data-ttu-id="69ea3-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="69ea3-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->
