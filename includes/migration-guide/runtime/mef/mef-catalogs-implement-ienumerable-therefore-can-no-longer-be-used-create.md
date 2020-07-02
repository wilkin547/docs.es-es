---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620635"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="f6d1f-101">Los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador</span><span class="sxs-lookup"><span data-stu-id="f6d1f-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="f6d1f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f6d1f-102">Details</span></span>

<span data-ttu-id="f6d1f-103">A partir de .NET Framework 4.5, los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador (un objeto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="f6d1f-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="f6d1f-104">Al intentar serializar un catálogo de MEF se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f6d1f-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f6d1f-105">Suggestion</span></span>

<span data-ttu-id="f6d1f-106">Ya no se puede usar MEF para crear un serializador.</span><span class="sxs-lookup"><span data-stu-id="f6d1f-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="f6d1f-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f6d1f-107">Name</span></span>    | <span data-ttu-id="f6d1f-108">Valor</span><span class="sxs-lookup"><span data-stu-id="f6d1f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f6d1f-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f6d1f-109">Scope</span></span>   |<span data-ttu-id="f6d1f-110">Major</span><span class="sxs-lookup"><span data-stu-id="f6d1f-110">Major</span></span>|
|<span data-ttu-id="f6d1f-111">Versión</span><span class="sxs-lookup"><span data-stu-id="f6d1f-111">Version</span></span>|<span data-ttu-id="f6d1f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f6d1f-112">4.5</span></span>|
|<span data-ttu-id="f6d1f-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="f6d1f-113">Type</span></span>|<span data-ttu-id="f6d1f-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f6d1f-114">Runtime</span></span>|
