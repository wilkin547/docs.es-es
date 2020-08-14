---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556237"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="208e4-101">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="208e4-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="208e4-102">El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, incorporado en .NET Framework 4.7.2, no se admite en Windows Forms en .NET Core ni .NET 5.0 y posterior.</span><span class="sxs-lookup"><span data-stu-id="208e4-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="208e4-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="208e4-103">Change description</span></span>

<span data-ttu-id="208e4-104">A partir de .NET Framework 4.7.2, el modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` permite al desarrollador omitir el nuevo comportamiento de la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, que ahora devuelve una referencia al control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="208e4-104">Starting with .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="208e4-105">El comportamiento anterior de la propiedad era devolver `null`.</span><span class="sxs-lookup"><span data-stu-id="208e4-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="208e4-106">Para obtener más información, vea [Elemento \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="208e4-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="208e4-107">En .NET Core y .NET 5.0 y posterior no se admite el modificador `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`.</span><span class="sxs-lookup"><span data-stu-id="208e4-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="208e4-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="208e4-108">Version introduced</span></span>

<span data-ttu-id="208e4-109">3.0</span><span class="sxs-lookup"><span data-stu-id="208e4-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="208e4-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="208e4-110">Recommended action</span></span>

<span data-ttu-id="208e4-111">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="208e4-111">Remove the switch.</span></span> <span data-ttu-id="208e4-112">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="208e4-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="208e4-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="208e4-113">Category</span></span>

<span data-ttu-id="208e4-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="208e4-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="208e4-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="208e4-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
