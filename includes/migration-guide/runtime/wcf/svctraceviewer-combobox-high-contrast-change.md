---
ms.openlocfilehash: 06f4186e8f233f5c769dfc5e05d2de5eacd9b053
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622091"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="b5a04-101">Cambio de contraste alto de ComboBox svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="b5a04-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="b5a04-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b5a04-102">Details</span></span>

<span data-ttu-id="b5a04-103">En la [herramienta Service Trace Viewer de Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), los controles ComboBox no se mostraban en el color correcto en ciertos temas de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="b5a04-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="b5a04-104">El problema se ha corregido en .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="b5a04-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="b5a04-105">Sin embargo, debido a los requisitos de compatibilidad con versiones anteriores del SDK de .NET Framework, la corrección no era visible para los clientes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5a04-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="b5a04-106">.NET 4.8 manifiesta este cambio agregando los siguientes [modificadores de configuración AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) al archivo svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="b5a04-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a><span data-ttu-id="b5a04-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b5a04-107">Suggestion</span></span>

<ul><li><span data-ttu-id="b5a04-108">Cómo no participar en el cambio: si no desea que se produzca el cambio de comportamiento de contraste alto, puede deshabilitarlo mediante la eliminación de la siguiente sección del archivo svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="b5a04-108">How to opt out of the change If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span></li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b5a04-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b5a04-109">Name</span></span>    | <span data-ttu-id="b5a04-110">Valor</span><span class="sxs-lookup"><span data-stu-id="b5a04-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b5a04-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b5a04-111">Scope</span></span>   |<span data-ttu-id="b5a04-112">Borde</span><span class="sxs-lookup"><span data-stu-id="b5a04-112">Edge</span></span>|
|<span data-ttu-id="b5a04-113">Versión</span><span class="sxs-lookup"><span data-stu-id="b5a04-113">Version</span></span>|<span data-ttu-id="b5a04-114">4.8</span><span class="sxs-lookup"><span data-stu-id="b5a04-114">4.8</span></span>|
|<span data-ttu-id="b5a04-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="b5a04-115">Type</span></span>|<span data-ttu-id="b5a04-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b5a04-116">Runtime</span></span>|
