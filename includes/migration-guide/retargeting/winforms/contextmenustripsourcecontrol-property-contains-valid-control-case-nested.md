---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614883"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="6e760-101">La propiedad ContextMenuStrip.SourceControl contiene un control válido en el caso de controles ToolStripMenuItem anidados</span><span class="sxs-lookup"><span data-stu-id="6e760-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="6e760-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e760-102">Details</span></span>

<span data-ttu-id="6e760-103">En .NET Framework 4.7.1 y versiones anteriores, la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> devuelve NULL de forma incorrecta cuando el usuario abre el menú desde controles <xref:System.Windows.Forms.ToolStripMenuItem> anidados.</span><span class="sxs-lookup"><span data-stu-id="6e760-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="6e760-104">En .NET Framework 4.7.2 y versiones posteriores, la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> siempre se establece en el control de origen real.</span><span class="sxs-lookup"><span data-stu-id="6e760-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6e760-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6e760-105">Suggestion</span></span>

<span data-ttu-id="6e760-106">**Cómo participar o no en estos cambios** Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6e760-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="6e760-107">La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e760-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="6e760-108">Tiene como destino .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="6e760-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="6e760-109">Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6e760-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="6e760-110">Tiene como destino .NET Framework 4.7.1 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) siguiente a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6e760-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="6e760-111">En las aplicaciones destinadas a .NET Framework 4.7.2 o una versión posterior, y en las que se quiere conservar el comportamiento heredado, se puede participar en el uso del valor de control de origen heredado si se establece explícitamente este modificador de AppContext en `true`.</span><span class="sxs-lookup"><span data-stu-id="6e760-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="6e760-112">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e760-112">Name</span></span>    | <span data-ttu-id="6e760-113">Valor</span><span class="sxs-lookup"><span data-stu-id="6e760-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6e760-114">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6e760-114">Scope</span></span>   | <span data-ttu-id="6e760-115">Borde</span><span class="sxs-lookup"><span data-stu-id="6e760-115">Edge</span></span>        |
| <span data-ttu-id="6e760-116">Versión</span><span class="sxs-lookup"><span data-stu-id="6e760-116">Version</span></span> | <span data-ttu-id="6e760-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="6e760-117">4.7.2</span></span>       |
| <span data-ttu-id="6e760-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e760-118">Type</span></span>    | <span data-ttu-id="6e760-119">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6e760-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6e760-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6e760-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
