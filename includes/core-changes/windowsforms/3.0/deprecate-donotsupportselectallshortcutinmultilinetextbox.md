---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937048"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="7f73c-101">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="7f73c-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="7f73c-102">El modificador de compatibilidad `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`, que se introdujo en .NET Framework 4.6.1, no se admite en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7f73c-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7f73c-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7f73c-103">Change description</span></span>

<span data-ttu-id="7f73c-104">A partir de .NET Framework 4.6.1, al seleccionar la tecla de método abreviado <kbd>Ctrl</kbd> + <kbd>A</kbd> en un control <xref:System.Windows.Forms.TextBox>, se selecciona todo el texto.</span><span class="sxs-lookup"><span data-stu-id="7f73c-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="7f73c-105">En .NET Framework 4.6 y en versiones anteriores, al seleccionar la tecla de método abreviado <kbd>Ctrl</kbd> + <kbd>A</kbd>, no se podía seleccionar todo el texto si las propiedades [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) y <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> estaban establecidas en `true`.</span><span class="sxs-lookup"><span data-stu-id="7f73c-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="7f73c-106">El modificador de compatibilidad `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` se introdujo en .NET Framework 4.6.1 para conservar el comportamiento original.</span><span class="sxs-lookup"><span data-stu-id="7f73c-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="7f73c-107">Para obtener más información, vea <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f73c-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="7f73c-108">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`.</span><span class="sxs-lookup"><span data-stu-id="7f73c-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7f73c-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7f73c-109">Version introduced</span></span>

<span data-ttu-id="7f73c-110">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="7f73c-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7f73c-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7f73c-111">Recommended action</span></span>

<span data-ttu-id="7f73c-112">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="7f73c-112">Remove the switch.</span></span> <span data-ttu-id="7f73c-113">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="7f73c-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="7f73c-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="7f73c-114">Category</span></span>

<span data-ttu-id="7f73c-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f73c-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7f73c-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7f73c-116">Affected APIs</span></span>

- <span data-ttu-id="7f73c-117">None</span><span class="sxs-lookup"><span data-stu-id="7f73c-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
