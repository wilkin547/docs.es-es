---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620713"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="1c0a7-101">Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión</span><span class="sxs-lookup"><span data-stu-id="1c0a7-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="1c0a7-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1c0a7-102">Details</span></span>

<span data-ttu-id="1c0a7-103">En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).</span><span class="sxs-lookup"><span data-stu-id="1c0a7-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c0a7-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1c0a7-104">Suggestion</span></span>

<span data-ttu-id="1c0a7-105">Si el límite de 100 para la fase de reversión es demasiado bajo, se puede establecer de forma explícita con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>.</span><span class="sxs-lookup"><span data-stu-id="1c0a7-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="1c0a7-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="1c0a7-106">Name</span></span>    | <span data-ttu-id="1c0a7-107">Valor</span><span class="sxs-lookup"><span data-stu-id="1c0a7-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c0a7-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1c0a7-108">Scope</span></span>   |<span data-ttu-id="1c0a7-109">Borde</span><span class="sxs-lookup"><span data-stu-id="1c0a7-109">Edge</span></span>|
|<span data-ttu-id="1c0a7-110">Versión</span><span class="sxs-lookup"><span data-stu-id="1c0a7-110">Version</span></span>|<span data-ttu-id="1c0a7-111">4.5</span><span class="sxs-lookup"><span data-stu-id="1c0a7-111">4.5</span></span>|
|<span data-ttu-id="1c0a7-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c0a7-112">Type</span></span>|<span data-ttu-id="1c0a7-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1c0a7-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1c0a7-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1c0a7-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
