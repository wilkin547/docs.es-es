---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620725"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="e2bdd-101">XmlSchemaException ahora establece correctamente las posiciones de las líneas</span><span class="sxs-lookup"><span data-stu-id="e2bdd-101">XmlSchemaException now sets line positions properly</span></span>

#### <a name="details"></a><span data-ttu-id="e2bdd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e2bdd-102">Details</span></span>

<span data-ttu-id="e2bdd-103">Si el valor de <xref:System.Xml.Linq.LoadOptions.SetLineInfo> se pasa al método Load y se produce un error de validación, las propiedades <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contendrán ahora la información de línea.</span><span class="sxs-lookup"><span data-stu-id="e2bdd-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e2bdd-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e2bdd-104">Suggestion</span></span>

<span data-ttu-id="e2bdd-105">Se debe actualizar el código de control de excepciones que suponga que <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> no se van a establecer, ya que ahora estas propiedades se establecerán correctamente al usar SetLineInfo durante la carga de XML.</span><span class="sxs-lookup"><span data-stu-id="e2bdd-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>

| <span data-ttu-id="e2bdd-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e2bdd-106">Name</span></span>    | <span data-ttu-id="e2bdd-107">Valor</span><span class="sxs-lookup"><span data-stu-id="e2bdd-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e2bdd-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e2bdd-108">Scope</span></span>   |<span data-ttu-id="e2bdd-109">Borde</span><span class="sxs-lookup"><span data-stu-id="e2bdd-109">Edge</span></span>|
|<span data-ttu-id="e2bdd-110">Versión</span><span class="sxs-lookup"><span data-stu-id="e2bdd-110">Version</span></span>|<span data-ttu-id="e2bdd-111">4.5</span><span class="sxs-lookup"><span data-stu-id="e2bdd-111">4.5</span></span>|
|<span data-ttu-id="e2bdd-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="e2bdd-112">Type</span></span>|<span data-ttu-id="e2bdd-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e2bdd-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e2bdd-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e2bdd-114">Affected APIs</span></span>

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
