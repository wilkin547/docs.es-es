---
ms.openlocfilehash: e3b9711ac66901d69838de4c9f309d086b06fd4d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620731"
---
### <a name="xslt-forward-compat-now-works"></a><span data-ttu-id="173e0-101">Ya funciona la compatibilidad con versiones posteriores de XSLT</span><span class="sxs-lookup"><span data-stu-id="173e0-101">XSLT forward compat now works</span></span>

#### <a name="details"></a><span data-ttu-id="173e0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="173e0-102">Details</span></span>

<span data-ttu-id="173e0-103">En .NET Framework 4, la compatibilidad con versiones posteriores de XSLT 1.0 presentaba los problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="173e0-103">In the .NET Framework 4, XSLT 1.0 forward compatibility had the following issues:</span></span><ul><li><span data-ttu-id="173e0-104">La carga de una hoja de estilos no se realizaba correctamente si su versión estaba establecida en 2.0 y el analizador encontraba una construcción de XSLT 1.0 desconocida.</span><span class="sxs-lookup"><span data-stu-id="173e0-104">Loading a style sheet failed if its version was set to 2.0 and the parser encountered an unrecognized XSLT 1.0 construct.</span></span></li><li><span data-ttu-id="173e0-105">La construcción <code>xsl:sort</code> no podía ordenar los datos si la versión de la hoja de estilos estaba establecida en 1.1.</span><span class="sxs-lookup"><span data-stu-id="173e0-105">The <code>xsl:sort</code> construct failed to sort data if the style sheet version was set to 1.1.</span></span></li></ul><span data-ttu-id="173e0-106">En .NET Framework 4.5, se han corregido estos problemas y el modo de compatibilidad con versiones posteriores de XSLT 1.0 funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="173e0-106">In the .NET Framework 4.5, these issues have been fixed, and XSLT 1.0 forward compatibility mode works properly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="173e0-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="173e0-107">Suggestion</span></span>

<span data-ttu-id="173e0-108">La mayoría de las aplicaciones no deberían verse afectadas, pero en algunos casos los datos se ordenarán de otra forma ahora que se respeta xsl:sort.</span><span class="sxs-lookup"><span data-stu-id="173e0-108">Most apps should be unaffected, however data will be sorted differently in some cases now that xsl:sort is respected.</span></span> <span data-ttu-id="173e0-109">Si se usa <code>xsl:sort</code> en hojas de estilo de la versión 1.1, confirme que las aplicaciones no dependían del orden de los datos sin ordenar.</span><span class="sxs-lookup"><span data-stu-id="173e0-109">If <code>xsl:sort</code> is used in 1.1 style sheets, confirm that apps were not depending on the unsorted order of data.</span></span> <span data-ttu-id="173e0-110">Si las aplicaciones se basan en el comportamiento de ordenación de la versión 4.0, quite <code>xsl:sort</code> de la hoja de estilos.</span><span class="sxs-lookup"><span data-stu-id="173e0-110">If apps rely on the 4.0 sorting behavior, remove <code>xsl:sort</code> from the style sheet.</span></span>

| <span data-ttu-id="173e0-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="173e0-111">Name</span></span>    | <span data-ttu-id="173e0-112">Valor</span><span class="sxs-lookup"><span data-stu-id="173e0-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="173e0-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="173e0-113">Scope</span></span>   |<span data-ttu-id="173e0-114">Borde</span><span class="sxs-lookup"><span data-stu-id="173e0-114">Edge</span></span>|
|<span data-ttu-id="173e0-115">Versión</span><span class="sxs-lookup"><span data-stu-id="173e0-115">Version</span></span>|<span data-ttu-id="173e0-116">4.5</span><span class="sxs-lookup"><span data-stu-id="173e0-116">4.5</span></span>|
|<span data-ttu-id="173e0-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="173e0-117">Type</span></span>|<span data-ttu-id="173e0-118">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="173e0-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="173e0-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="173e0-119">Affected APIs</span></span>

-<xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
