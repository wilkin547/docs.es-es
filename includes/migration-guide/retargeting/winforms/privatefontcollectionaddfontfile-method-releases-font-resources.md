---
ms.openlocfilehash: 6ee290f6722480778381376f588e16877894f232
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606946"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="7c3ad-101">El método PrivateFontCollection.AddFontFile libera los recursos de fuente</span><span class="sxs-lookup"><span data-stu-id="7c3ad-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

#### <a name="details"></a><span data-ttu-id="7c3ad-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="7c3ad-102">Details</span></span>

<span data-ttu-id="7c3ad-103">En .NET Framework 4.7.1 y versiones anteriores, la clase <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> no libera los recursos de fuentes GDI+ después de que se elimine <xref:System.Drawing.Text.PrivateFontCollection> para los objetos <xref:System.Drawing.Font> que se agregaron a esta colección con el método <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="7c3ad-104">En .NET Framework 4.7.2 y versiones posteriores, <xref:System.Drawing.Text.FontCollection.Dispose%2A> libera las fuentes GDI+ que se agregaron a la colección como archivos.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7c3ad-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="7c3ad-105">Suggestion</span></span>

<span data-ttu-id="7c3ad-106">**Cómo participar o no en estos cambios** Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="7c3ad-107">La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="7c3ad-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="7c3ad-108">Se recompila para tener .NET Framework 4.7.2 como destino.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="7c3ad-109">Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="7c3ad-110">Tiene como destino .NET Framework 4.7.1 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="7c3ad-111">En las aplicaciones destinadas a .NET Framework 4.7.2 o una versión posterior, y en las que se quiere conservar el comportamiento heredado, se puede participar en no liberar los recursos de fuente si se establece explícitamente este modificador de AppContext en `true`.</span><span class="sxs-lookup"><span data-stu-id="7c3ad-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="7c3ad-112">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7c3ad-112">Name</span></span>    | <span data-ttu-id="7c3ad-113">Valor</span><span class="sxs-lookup"><span data-stu-id="7c3ad-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7c3ad-114">Ámbito</span><span class="sxs-lookup"><span data-stu-id="7c3ad-114">Scope</span></span>   | <span data-ttu-id="7c3ad-115">Borde</span><span class="sxs-lookup"><span data-stu-id="7c3ad-115">Edge</span></span>        |
| <span data-ttu-id="7c3ad-116">Versión</span><span class="sxs-lookup"><span data-stu-id="7c3ad-116">Version</span></span> | <span data-ttu-id="7c3ad-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="7c3ad-117">4.7.2</span></span>       |
| <span data-ttu-id="7c3ad-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="7c3ad-118">Type</span></span>    | <span data-ttu-id="7c3ad-119">Redestinación</span><span class="sxs-lookup"><span data-stu-id="7c3ad-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7c3ad-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7c3ad-120">Affected APIs</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
