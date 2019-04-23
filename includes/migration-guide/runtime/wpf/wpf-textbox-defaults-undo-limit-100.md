---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235794"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="1ddbc-101">Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión</span><span class="sxs-lookup"><span data-stu-id="1ddbc-101">WPF TextBox defaults to undo limit of 100</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1ddbc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ddbc-102">Details</span></span>|<span data-ttu-id="1ddbc-103">En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).</span><span class="sxs-lookup"><span data-stu-id="1ddbc-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>|
|<span data-ttu-id="1ddbc-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1ddbc-104">Suggestion</span></span>|<span data-ttu-id="1ddbc-105">Si el límite de 100 para la fase de reversión es demasiado bajo, se puede establecer de forma explícita con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>.</span><span class="sxs-lookup"><span data-stu-id="1ddbc-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>|
|<span data-ttu-id="1ddbc-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1ddbc-106">Scope</span></span>|<span data-ttu-id="1ddbc-107">Borde</span><span class="sxs-lookup"><span data-stu-id="1ddbc-107">Edge</span></span>|
|<span data-ttu-id="1ddbc-108">Versión</span><span class="sxs-lookup"><span data-stu-id="1ddbc-108">Version</span></span>|<span data-ttu-id="1ddbc-109">4.5</span><span class="sxs-lookup"><span data-stu-id="1ddbc-109">4.5</span></span>|
|<span data-ttu-id="1ddbc-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="1ddbc-110">Type</span></span>|<span data-ttu-id="1ddbc-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1ddbc-111">Runtime</span></span>|
|<span data-ttu-id="1ddbc-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1ddbc-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
