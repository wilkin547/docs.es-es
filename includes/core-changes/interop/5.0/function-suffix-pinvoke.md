---
ms.openlocfilehash: e128bdb5735b3e4844356ad4807cc092f6f2b105
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062435"
---
### <a name="no-aw-suffix-probing-on-non-windows-platforms"></a><span data-ttu-id="37fd5-101">No se incluye el sondeo del sufijo A/W en plataformas que no son de Windows</span><span class="sxs-lookup"><span data-stu-id="37fd5-101">No A/W suffix probing on non-Windows platforms</span></span>

<span data-ttu-id="37fd5-102">Los runtimes de .NET ya no agregan un sufijo `A` o `W` a los nombres de exportación de funciones durante el sondeo de P/Invoke en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="37fd5-102">The .NET runtimes no longer add an `A` or `W` suffix to function export names during probing for P/Invokes on non-Windows platforms.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="37fd5-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="37fd5-103">Version introduced</span></span>

<span data-ttu-id="37fd5-104">5.0 (versión preliminar 4)</span><span class="sxs-lookup"><span data-stu-id="37fd5-104">5.0 Preview 4</span></span>

#### <a name="change-description"></a><span data-ttu-id="37fd5-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="37fd5-105">Change description</span></span>

<span data-ttu-id="37fd5-106">[Windows tiene la convención](/windows/win32/intl/conventions-for-function-prototypes) de agregar un sufijo `A` o `W` a los nombres de función de Windows SDK. Estos prefijos corresponden a la página de códigos de Windows y a las versiones de Unicode respectivamente.</span><span class="sxs-lookup"><span data-stu-id="37fd5-106">[Windows has a convention](/windows/win32/intl/conventions-for-function-prototypes) of adding an `A` or `W` suffix to Windows SDK function names, which correspond to the Windows code page and Unicode versions, respectively.</span></span>

<span data-ttu-id="37fd5-107">En versiones anteriores de .NET, los runtimes de CoreCLR y Mono agregan un sufijo `A` o `W` al nombre de la exportación durante la detección de exportación para P/Invokes *en todas las plataformas*.</span><span class="sxs-lookup"><span data-stu-id="37fd5-107">In previous versions of .NET, both the CoreCLR and Mono runtimes add an `A` or `W` suffix to the export name during export discovery for P/Invokes *on all platforms*.</span></span>

<span data-ttu-id="37fd5-108">En .NET 5,0 y versiones posteriores, se agrega un sufijo `A` o `W` al nombre de la exportación durante la detección de exportación *solo en Windows*.</span><span class="sxs-lookup"><span data-stu-id="37fd5-108">In .NET 5.0 and later versions, an `A` or `W` suffix is added to the export name during export discovery *on Windows only*.</span></span> <span data-ttu-id="37fd5-109">En las plataformas UNIX, no se agrega el sufijo.</span><span class="sxs-lookup"><span data-stu-id="37fd5-109">On Unix platforms, the suffix is not added.</span></span> <span data-ttu-id="37fd5-110">La semántica de los runtimes en la plataforma de Windows no se modifica.</span><span class="sxs-lookup"><span data-stu-id="37fd5-110">The semantics of both runtimes on the Windows platform remain unchanged.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="37fd5-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="37fd5-111">Reason for change</span></span>

<span data-ttu-id="37fd5-112">Este cambio se ha realizado para simplificar el sondeo entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="37fd5-112">This change was made to simplify cross-platform probing.</span></span> <span data-ttu-id="37fd5-113">Es algo de lo que no habría que preocuparse, ya que las plataformas que no son de Windows no contienen esta semántica.</span><span class="sxs-lookup"><span data-stu-id="37fd5-113">It's overhead that shouldn't be incurred, given that non-Windows platforms don't contain this semantic.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="37fd5-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="37fd5-114">Recommended action</span></span>

<span data-ttu-id="37fd5-115">Para mitigar el cambio, puede agregar manualmente el sufijo deseado en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="37fd5-115">To mitigate the change, you can manually add the desired suffix on non-Windows platforms.</span></span> <span data-ttu-id="37fd5-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37fd5-116">For example:</span></span>

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

#### <a name="category"></a><span data-ttu-id="37fd5-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="37fd5-117">Category</span></span>

<span data-ttu-id="37fd5-118">Interop</span><span class="sxs-lookup"><span data-stu-id="37fd5-118">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="37fd5-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="37fd5-119">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

-->
