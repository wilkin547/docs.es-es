---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617293"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="47b88-101">TextBox.Text de WPF se puede desincronizar con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="47b88-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

#### <a name="details"></a><span data-ttu-id="47b88-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="47b88-102">Details</span></span>

<span data-ttu-id="47b88-103">En algunos casos, la propiedad <xref:System.Windows.Controls.TextBox.Text> refleja un valor anterior al valor de propiedad de enlace de datos si la propiedad se modifica durante una operación de escritura de enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="47b88-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47b88-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="47b88-104">Suggestion</span></span>

<span data-ttu-id="47b88-105">Esto no debería tener ningún impacto negativo.</span><span class="sxs-lookup"><span data-stu-id="47b88-105">This should have no negative impact.</span></span> <span data-ttu-id="47b88-106">Sin embargo, puede restaurar el comportamiento anterior estableciendo la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> en `false`.</span><span class="sxs-lookup"><span data-stu-id="47b88-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to `false`.</span></span>

| <span data-ttu-id="47b88-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="47b88-107">Name</span></span>    | <span data-ttu-id="47b88-108">Valor</span><span class="sxs-lookup"><span data-stu-id="47b88-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47b88-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="47b88-109">Scope</span></span>   | <span data-ttu-id="47b88-110">Borde</span><span class="sxs-lookup"><span data-stu-id="47b88-110">Edge</span></span>        |
| <span data-ttu-id="47b88-111">Versión</span><span class="sxs-lookup"><span data-stu-id="47b88-111">Version</span></span> | <span data-ttu-id="47b88-112">4.5</span><span class="sxs-lookup"><span data-stu-id="47b88-112">4.5</span></span>         |
|<span data-ttu-id="47b88-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="47b88-113">Type</span></span>|<span data-ttu-id="47b88-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="47b88-114">Retargeting</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="47b88-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="47b88-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
