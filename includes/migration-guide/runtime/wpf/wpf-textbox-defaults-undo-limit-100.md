---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496483"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="85c78-101">Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión</span><span class="sxs-lookup"><span data-stu-id="85c78-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="85c78-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="85c78-102">Details</span></span>

<span data-ttu-id="85c78-103">En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).</span><span class="sxs-lookup"><span data-stu-id="85c78-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85c78-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="85c78-104">Suggestion</span></span>

<span data-ttu-id="85c78-105">Si el límite de 100 para la fase de reversión es demasiado bajo, se puede establecer de forma explícita con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>.</span><span class="sxs-lookup"><span data-stu-id="85c78-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="85c78-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="85c78-106">Name</span></span>    | <span data-ttu-id="85c78-107">Valor</span><span class="sxs-lookup"><span data-stu-id="85c78-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85c78-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="85c78-108">Scope</span></span>   |<span data-ttu-id="85c78-109">Borde</span><span class="sxs-lookup"><span data-stu-id="85c78-109">Edge</span></span>|
|<span data-ttu-id="85c78-110">Versión</span><span class="sxs-lookup"><span data-stu-id="85c78-110">Version</span></span>|<span data-ttu-id="85c78-111">4.5</span><span class="sxs-lookup"><span data-stu-id="85c78-111">4.5</span></span>|
|<span data-ttu-id="85c78-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="85c78-112">Type</span></span>|<span data-ttu-id="85c78-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="85c78-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="85c78-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="85c78-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
