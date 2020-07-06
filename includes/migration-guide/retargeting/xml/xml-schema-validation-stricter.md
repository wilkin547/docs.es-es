---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617298"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="08ba5-101">Validación del esquema XML más estricta</span><span class="sxs-lookup"><span data-stu-id="08ba5-101">XML schema validation is stricter</span></span>

#### <a name="details"></a><span data-ttu-id="08ba5-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="08ba5-102">Details</span></span>

<span data-ttu-id="08ba5-103">En .NET Framework 4.5, la validación del esquema XML es más estricta.</span><span class="sxs-lookup"><span data-stu-id="08ba5-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="08ba5-104">Si usa xsd:anyURI para validar un identificador URI, como un protocolo mailto, la validación producirá un error si hay espacios en el URI.</span><span class="sxs-lookup"><span data-stu-id="08ba5-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="08ba5-105">En versiones anteriores de .NET Framework, la validación se realizaba correctamente.</span><span class="sxs-lookup"><span data-stu-id="08ba5-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="08ba5-106">El cambio solo afecta a las aplicaciones que tienen como destino .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="08ba5-106">The change affects only applications that target the .NET Framework 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="08ba5-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="08ba5-107">Suggestion</span></span>

<span data-ttu-id="08ba5-108">Si se necesita la validación de .NET Framework 4.0 (menos estricta), la aplicación que realiza la validación puede establecer la versión 4.0 de .NET Framework como destino.</span><span class="sxs-lookup"><span data-stu-id="08ba5-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="08ba5-109">Pero en la redestinación a .NET Framework 4.5, se debe realizar la revisión del código para asegurarse de que los URI no válidos (con espacios en blanco) no se esperan como valores de atributo con el tipo de datos anyURI.</span><span class="sxs-lookup"><span data-stu-id="08ba5-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>

| <span data-ttu-id="08ba5-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="08ba5-110">Name</span></span>    | <span data-ttu-id="08ba5-111">Valor</span><span class="sxs-lookup"><span data-stu-id="08ba5-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="08ba5-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="08ba5-112">Scope</span></span>   | <span data-ttu-id="08ba5-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="08ba5-113">Minor</span></span>       |
| <span data-ttu-id="08ba5-114">Versión</span><span class="sxs-lookup"><span data-stu-id="08ba5-114">Version</span></span> | <span data-ttu-id="08ba5-115">4.5</span><span class="sxs-lookup"><span data-stu-id="08ba5-115">4.5</span></span>         |
| <span data-ttu-id="08ba5-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="08ba5-116">Type</span></span>    | <span data-ttu-id="08ba5-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="08ba5-117">Retargeting</span></span> |
