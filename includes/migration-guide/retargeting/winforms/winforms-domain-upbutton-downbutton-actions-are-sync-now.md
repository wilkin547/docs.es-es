---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606266"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="935a3-101">Las acciones upbutton y downbutton de Domain de WinForm ahora están sincronizadas</span><span class="sxs-lookup"><span data-stu-id="935a3-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="935a3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="935a3-102">Details</span></span>

<span data-ttu-id="935a3-103">En .NET Framework 4.7.1 y versiones anteriores, se omite la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> del control <xref:System.Windows.Forms.DomainUpDown> cuando el texto del control está presente y el desarrollador tiene que usar la acción <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> en el control antes de usar la acción <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="935a3-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="935a3-104">A partir de .NET Framework 4.7.2, las acciones <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> funcionan de manera independiente en este escenario y permanecen sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="935a3-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="935a3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="935a3-105">Suggestion</span></span>

<span data-ttu-id="935a3-106">Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="935a3-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="935a3-107">La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="935a3-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="935a3-108">Se recompila para tener .NET Framework 4.7.2 como destino.</span><span class="sxs-lookup"><span data-stu-id="935a3-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="935a3-109">Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="935a3-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="935a3-110">No participa en el comportamiento de desplazamiento heredado mediante la adición del [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="935a3-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="935a3-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="935a3-111">Name</span></span>    | <span data-ttu-id="935a3-112">Valor</span><span class="sxs-lookup"><span data-stu-id="935a3-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="935a3-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="935a3-113">Scope</span></span>   | <span data-ttu-id="935a3-114">Borde</span><span class="sxs-lookup"><span data-stu-id="935a3-114">Edge</span></span>        |
| <span data-ttu-id="935a3-115">Versión</span><span class="sxs-lookup"><span data-stu-id="935a3-115">Version</span></span> | <span data-ttu-id="935a3-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="935a3-116">4.7.2</span></span>       |
| <span data-ttu-id="935a3-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="935a3-117">Type</span></span>    | <span data-ttu-id="935a3-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="935a3-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="935a3-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="935a3-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
