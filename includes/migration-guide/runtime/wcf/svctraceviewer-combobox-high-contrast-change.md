---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770833"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="5faa9-101">Cambio de contraste alto de ComboBox svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="5faa9-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="5faa9-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5faa9-102">Details</span></span>

<span data-ttu-id="5faa9-103">En la [herramienta Service Trace Viewer de Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), los controles ComboBox no se mostraban en el color correcto en ciertos temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="5faa9-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="5faa9-104">El problema se ha corregido en .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="5faa9-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="5faa9-105">Sin embargo, debido a los requisitos de compatibilidad con versiones anteriores del SDK de .NET Framework, la corrección no era visible para los clientes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5faa9-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="5faa9-106">.NET 4.8 manifiesta este cambio agregando los siguientes [modificadores de configuración AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) al archivo svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="5faa9-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a><span data-ttu-id="5faa9-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5faa9-107">Suggestion</span></span>

<span data-ttu-id="5faa9-108">Si no quiere que se produzca el cambio de comportamiento de contraste alto, puede deshabilitarlo mediante la eliminación de la siguiente sección del archivo svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="5faa9-108">If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| <span data-ttu-id="5faa9-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5faa9-109">Name</span></span>    | <span data-ttu-id="5faa9-110">Valor</span><span class="sxs-lookup"><span data-stu-id="5faa9-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="5faa9-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5faa9-111">Scope</span></span>   | <span data-ttu-id="5faa9-112">Borde</span><span class="sxs-lookup"><span data-stu-id="5faa9-112">Edge</span></span>    |
| <span data-ttu-id="5faa9-113">Versión</span><span class="sxs-lookup"><span data-stu-id="5faa9-113">Version</span></span> | <span data-ttu-id="5faa9-114">4.8</span><span class="sxs-lookup"><span data-stu-id="5faa9-114">4.8</span></span>     |
| <span data-ttu-id="5faa9-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="5faa9-115">Type</span></span>    | <span data-ttu-id="5faa9-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5faa9-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5faa9-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5faa9-117">Affected APIs</span></span>

<span data-ttu-id="5faa9-118">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="5faa9-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
