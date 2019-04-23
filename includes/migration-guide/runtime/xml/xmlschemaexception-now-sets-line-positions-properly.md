---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805039"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="d6511-101">XmlSchemaException ahora establece correctamente las posiciones de las líneas</span><span class="sxs-lookup"><span data-stu-id="d6511-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d6511-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d6511-102">Details</span></span>|<span data-ttu-id="d6511-103">Si el valor de <xref:System.Xml.Linq.LoadOptions.SetLineInfo> se pasa al método Load y se produce un error de validación, las propiedades <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contendrán ahora la información de línea.</span><span class="sxs-lookup"><span data-stu-id="d6511-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="d6511-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d6511-104">Suggestion</span></span>|<span data-ttu-id="d6511-105">Se debe actualizar el código de control de excepciones que suponga que <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> no se van a establecer, ya que ahora estas propiedades se establecerán correctamente al usar SetLineInfo durante la carga de XML.</span><span class="sxs-lookup"><span data-stu-id="d6511-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="d6511-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d6511-106">Scope</span></span>|<span data-ttu-id="d6511-107">Borde</span><span class="sxs-lookup"><span data-stu-id="d6511-107">Edge</span></span>|
|<span data-ttu-id="d6511-108">Versión</span><span class="sxs-lookup"><span data-stu-id="d6511-108">Version</span></span>|<span data-ttu-id="d6511-109">4.5</span><span class="sxs-lookup"><span data-stu-id="d6511-109">4.5</span></span>|
|<span data-ttu-id="d6511-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6511-110">Type</span></span>|<span data-ttu-id="d6511-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d6511-111">Runtime</span></span>|
|<span data-ttu-id="d6511-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d6511-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
