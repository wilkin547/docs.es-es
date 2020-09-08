---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497227"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="5e98d-101">Los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador</span><span class="sxs-lookup"><span data-stu-id="5e98d-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="5e98d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5e98d-102">Details</span></span>

<span data-ttu-id="5e98d-103">A partir de .NET Framework 4.5, los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador (un objeto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="5e98d-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="5e98d-104">Al intentar serializar un catálogo de MEF se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="5e98d-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5e98d-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5e98d-105">Suggestion</span></span>

<span data-ttu-id="5e98d-106">Ya no se puede usar MEF para crear un serializador.</span><span class="sxs-lookup"><span data-stu-id="5e98d-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="5e98d-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5e98d-107">Name</span></span>    | <span data-ttu-id="5e98d-108">Valor</span><span class="sxs-lookup"><span data-stu-id="5e98d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5e98d-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5e98d-109">Scope</span></span>   |<span data-ttu-id="5e98d-110">Major</span><span class="sxs-lookup"><span data-stu-id="5e98d-110">Major</span></span>|
|<span data-ttu-id="5e98d-111">Versión</span><span class="sxs-lookup"><span data-stu-id="5e98d-111">Version</span></span>|<span data-ttu-id="5e98d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="5e98d-112">4.5</span></span>|
|<span data-ttu-id="5e98d-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="5e98d-113">Type</span></span>|<span data-ttu-id="5e98d-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5e98d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5e98d-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5e98d-115">Affected APIs</span></span>

<span data-ttu-id="5e98d-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="5e98d-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
