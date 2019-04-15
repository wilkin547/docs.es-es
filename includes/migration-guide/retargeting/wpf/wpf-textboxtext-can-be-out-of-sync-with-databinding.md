---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234782"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="b9618-101">TextBox.Text de WPF se puede desincronizar con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="b9618-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b9618-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b9618-102">Details</span></span>|<span data-ttu-id="b9618-103">En algunos casos, la propiedad <xref:System.Windows.Controls.TextBox.Text> refleja un valor anterior al valor de propiedad de enlace de datos si la propiedad se modifica durante una operación de escritura de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="b9618-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="b9618-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b9618-104">Suggestion</span></span>|<span data-ttu-id="b9618-105">Esto no debería tener ningún impacto negativo.</span><span class="sxs-lookup"><span data-stu-id="b9618-105">This should have no negative impact.</span></span> <span data-ttu-id="b9618-106">Sin embargo, puede restaurar el comportamiento anterior estableciendo la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="b9618-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="b9618-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b9618-107">Scope</span></span>|<span data-ttu-id="b9618-108">Borde</span><span class="sxs-lookup"><span data-stu-id="b9618-108">Edge</span></span>|
|<span data-ttu-id="b9618-109">Versión</span><span class="sxs-lookup"><span data-stu-id="b9618-109">Version</span></span>|<span data-ttu-id="b9618-110">4.5</span><span class="sxs-lookup"><span data-stu-id="b9618-110">4.5</span></span>|
|<span data-ttu-id="b9618-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9618-111">Type</span></span>|<span data-ttu-id="b9618-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="b9618-112">Retargeting</span></span>|
|<span data-ttu-id="b9618-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b9618-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
