---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620689"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="864f1-101">FlowDocument puede mostrar una línea de texto adicional</span><span class="sxs-lookup"><span data-stu-id="864f1-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="864f1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="864f1-102">Details</span></span>

<span data-ttu-id="864f1-103">En algunos casos, un elemento <xref:System.Windows.Documents.FlowDocument> mostrará una línea de texto adicional cuando se ejecuta en .NET Framework 4.5 en comparación a cómo se mostraba cuando se ejecutaba en .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="864f1-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="864f1-104">No hay casos conocidos de que el cambio provoque que un texto se muestre de forma incorrecta o ilegible, pero podría dar la impresión de que el texto se omitió anteriormente de la vista de un <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="864f1-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="864f1-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="864f1-105">Suggestion</span></span>

<span data-ttu-id="864f1-106">En algunos casos, reducir la propiedad PageHeight del elemento de visualización en uno puede restaurar el número anterior de líneas mostradas.</span><span class="sxs-lookup"><span data-stu-id="864f1-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="864f1-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="864f1-107">Name</span></span>    | <span data-ttu-id="864f1-108">Valor</span><span class="sxs-lookup"><span data-stu-id="864f1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="864f1-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="864f1-109">Scope</span></span>   |<span data-ttu-id="864f1-110">Borde</span><span class="sxs-lookup"><span data-stu-id="864f1-110">Edge</span></span>|
|<span data-ttu-id="864f1-111">Versión</span><span class="sxs-lookup"><span data-stu-id="864f1-111">Version</span></span>|<span data-ttu-id="864f1-112">4.5</span><span class="sxs-lookup"><span data-stu-id="864f1-112">4.5</span></span>|
|<span data-ttu-id="864f1-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="864f1-113">Type</span></span>|<span data-ttu-id="864f1-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="864f1-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="864f1-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="864f1-115">Affected APIs</span></span>

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|
