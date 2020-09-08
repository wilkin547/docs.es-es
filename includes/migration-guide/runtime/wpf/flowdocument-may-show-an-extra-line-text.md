---
ms.openlocfilehash: a61005e317020c47a283dae292236624ec6057ce
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496803"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="b8108-101">FlowDocument puede mostrar una línea de texto adicional</span><span class="sxs-lookup"><span data-stu-id="b8108-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="b8108-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b8108-102">Details</span></span>

<span data-ttu-id="b8108-103">En algunos casos, un elemento <xref:System.Windows.Documents.FlowDocument> mostrará una línea de texto adicional cuando se ejecuta en .NET Framework 4.5 en comparación a cómo se mostraba cuando se ejecutaba en .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="b8108-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="b8108-104">No hay casos conocidos de que el cambio provoque que un texto se muestre de forma incorrecta o ilegible, pero podría dar la impresión de que el texto se omitió anteriormente de la vista de un <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="b8108-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b8108-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b8108-105">Suggestion</span></span>

<span data-ttu-id="b8108-106">En algunos casos, reducir la propiedad PageHeight del elemento de visualización en uno puede restaurar el número anterior de líneas mostradas.</span><span class="sxs-lookup"><span data-stu-id="b8108-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="b8108-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b8108-107">Name</span></span>    | <span data-ttu-id="b8108-108">Valor</span><span class="sxs-lookup"><span data-stu-id="b8108-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b8108-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b8108-109">Scope</span></span>   |<span data-ttu-id="b8108-110">Borde</span><span class="sxs-lookup"><span data-stu-id="b8108-110">Edge</span></span>|
|<span data-ttu-id="b8108-111">Versión</span><span class="sxs-lookup"><span data-stu-id="b8108-111">Version</span></span>|<span data-ttu-id="b8108-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b8108-112">4.5</span></span>|
|<span data-ttu-id="b8108-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="b8108-113">Type</span></span>|<span data-ttu-id="b8108-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b8108-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b8108-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b8108-115">Affected APIs</span></span>

- <xref:System.Windows.Documents.FlowDocument.%23ctor>
- <xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)>
- <xref:System.Windows.Controls.FlowDocumentReader.%23ctor>
- <xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor>
- <xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Documents.FlowDocument.#ctor`
- `M:System.Windows.Documents.FlowDocument.#ctor(System.Windows.Documents.Block)`
- `M:System.Windows.Controls.FlowDocumentReader.#ctor`
- `M:System.Windows.Controls.FlowDocumentPageViewer.#ctor`
- `M:System.Windows.Controls.Primitives.DocumentPageView.#ctor`

-->
