---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615771"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="5cbd1-101">Icon.ToBitmap convierte correctamente los iconos con marcos PNG en objetos de mapa de bits</span><span class="sxs-lookup"><span data-stu-id="5cbd1-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

#### <a name="details"></a><span data-ttu-id="5cbd1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5cbd1-102">Details</span></span>

<span data-ttu-id="5cbd1-103">A partir de las aplicaciones destinadas a .NET Framework 4.6, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> convierte correctamente los iconos con marcos PNG en objetos Bitmap.</span><span class="sxs-lookup"><span data-stu-id="5cbd1-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.</span></span><p/><span data-ttu-id="5cbd1-104">En las aplicaciones destinadas a .NET Framework 4.5.2 y versiones anteriores, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera una excepción <xref:System.ArgumentOutOfRangeException> si el objeto Icon tiene marcos PNG.</span><span class="sxs-lookup"><span data-stu-id="5cbd1-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.</span></span><p/><span data-ttu-id="5cbd1-105">Este cambio afecta a las aplicaciones que se vuelven a compilar para tener como destino .NET Framework 4.6 y que implementan un control especial para <xref:System.ArgumentOutOfRangeException> que se genera cuando un objeto Icon tiene marcos PNG.</span><span class="sxs-lookup"><span data-stu-id="5cbd1-105">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="5cbd1-106">Cuando se ejecuta en .NET Framework 4.6, la conversión es correcta, ya no se genera un <xref:System.ArgumentOutOfRangeException> y, por tanto, ya no se invoca el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="5cbd1-106">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5cbd1-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5cbd1-107">Suggestion</span></span>

<span data-ttu-id="5cbd1-108">Si no quiere este comportamiento, puede conservar el comportamiento anterior agregando el elemento siguiente a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="5cbd1-108">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the `<runtime>` section of your app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

<span data-ttu-id="5cbd1-109">Si el archivo app.config ya contiene el elemento `AppContextSwitchOverrides`, el valor nuevo se debe combinar con el atributo value de esta forma:</span><span class="sxs-lookup"><span data-stu-id="5cbd1-109">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the value attribute like this:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="5cbd1-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="5cbd1-110">Name</span></span>    | <span data-ttu-id="5cbd1-111">Valor</span><span class="sxs-lookup"><span data-stu-id="5cbd1-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5cbd1-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5cbd1-112">Scope</span></span>   | <span data-ttu-id="5cbd1-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="5cbd1-113">Minor</span></span>       |
| <span data-ttu-id="5cbd1-114">Versión</span><span class="sxs-lookup"><span data-stu-id="5cbd1-114">Version</span></span> | <span data-ttu-id="5cbd1-115">4.6</span><span class="sxs-lookup"><span data-stu-id="5cbd1-115">4.6</span></span>         |
| <span data-ttu-id="5cbd1-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="5cbd1-116">Type</span></span>    | <span data-ttu-id="5cbd1-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="5cbd1-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5cbd1-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5cbd1-118">Affected APIs</span></span>

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
