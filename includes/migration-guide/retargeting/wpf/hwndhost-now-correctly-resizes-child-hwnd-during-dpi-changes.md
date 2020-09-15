---
ms.openlocfilehash: 3d1dc8dec18212afd815aa3de7fc82c8a1f680dc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616314"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a><span data-ttu-id="6f1bd-101">HwndHost ahora cambia correctamente el tamaño del elemento secundario HWND durante los cambios de PPP</span><span class="sxs-lookup"><span data-stu-id="6f1bd-101">HwndHost now correctly resizes child-HWND during DPI changes</span></span>

#### <a name="details"></a><span data-ttu-id="6f1bd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6f1bd-102">Details</span></span>

<span data-ttu-id="6f1bd-103">En .NET Framework 4.7.2 y versiones anteriores, cuando WPF se ejecutaba en modo de reconocimiento por monitor, los controles hospedados en <xref:System.Windows.Interop.HwndHost> no tenían el tamaño correcto después de realizar cambios de PPP, como al mover las aplicaciones de un monitor a otro.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-103">In .NET Framework 4.7.2 and earlier versions, when WPF was run in Per-Monitor Aware mode, controls hosted within <xref:System.Windows.Interop.HwndHost> were not sized correctly after DPI changes, such as when moving applications from one monitor to another.</span></span> <span data-ttu-id="6f1bd-104">Esta corrección garantiza que los controles hospedados tienen un tamaño apropiado.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-104">This fix ensures that hosted controls are sized appropriately.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6f1bd-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6f1bd-105">Suggestion</span></span>

<span data-ttu-id="6f1bd-106">Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o versiones posteriores y debe participar en este comportamiento estableciendo [AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) en la sección `<runtime>` del archivo de configuración de aplicación en `false`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later, and it must opt-in to this behavior by setting the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) in the `<runtime>` section of the app config file to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="6f1bd-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6f1bd-107">Name</span></span>    | <span data-ttu-id="6f1bd-108">Valor</span><span class="sxs-lookup"><span data-stu-id="6f1bd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6f1bd-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6f1bd-109">Scope</span></span>   | <span data-ttu-id="6f1bd-110">Major</span><span class="sxs-lookup"><span data-stu-id="6f1bd-110">Major</span></span>       |
| <span data-ttu-id="6f1bd-111">Versión</span><span class="sxs-lookup"><span data-stu-id="6f1bd-111">Version</span></span> | <span data-ttu-id="6f1bd-112">4.8</span><span class="sxs-lookup"><span data-stu-id="6f1bd-112">4.8</span></span>         |
| <span data-ttu-id="6f1bd-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="6f1bd-113">Type</span></span>    | <span data-ttu-id="6f1bd-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6f1bd-114">Retargeting</span></span> |
