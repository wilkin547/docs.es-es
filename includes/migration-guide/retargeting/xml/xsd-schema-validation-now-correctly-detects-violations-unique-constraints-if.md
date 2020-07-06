---
ms.openlocfilehash: 349854b0dec5a585990b9c5e7c0b575df5bf70f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615777"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a><span data-ttu-id="a9109-101">La validación del esquema XSD ahora detecta correctamente las infracciones de restricciones únicas si se usan claves compuestas y una de las claves está vacía</span><span class="sxs-lookup"><span data-stu-id="a9109-101">XSD Schema validation now correctly detects violations of unique constraints if compound keys are used and one key is empty</span></span>

#### <a name="details"></a><span data-ttu-id="a9109-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a9109-102">Details</span></span>

<span data-ttu-id="a9109-103">Las versiones de .NET Framework anteriores a la 4.6 presentaban un error que hacía que la validación de XSD no detectara restricciones únicas en claves compuestas si alguna de las claves estaba vacía.</span><span class="sxs-lookup"><span data-stu-id="a9109-103">Versions of the .NET Framework prior to 4.6 had a bug that caused XSD validation to not detect unique constraints on compound keys if one of the keys was empty.</span></span> <span data-ttu-id="a9109-104">Este problema se corrigió en .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="a9109-104">In the .NET Framework 4.6, this issue is corrected.</span></span> <span data-ttu-id="a9109-105">De este modo, se conseguirá una mayor corrección en la validación, pero también podría hacer que cierto XML no valide lo que antes sí validaría.</span><span class="sxs-lookup"><span data-stu-id="a9109-105">This will result in more correct validation, but it may also result in some XML not validating which previously would have.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a9109-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a9109-106">Suggestion</span></span>

<span data-ttu-id="a9109-107">Si se necesita una validación de .NET Framework 4.0 menos estricta, se puede establecer la versión 4.5 (o anterior) de .NET Framework como destino de la aplicación de validación.</span><span class="sxs-lookup"><span data-stu-id="a9109-107">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.5 (or earlier) of the .NET Framework.</span></span> <span data-ttu-id="a9109-108">Pero en la redestinación a .NET Framework 4.6, se debe realizar la revisión del código para asegurarse de que no se espere la validación de claves compuestas duplicadas (como se indica en la descripción de este problema).</span><span class="sxs-lookup"><span data-stu-id="a9109-108">When retargeting to .NET Framework 4.6, however, code review should be done to be sure that duplicate compound keys (as described in this issue's description) are not expected to validate.</span></span>

| <span data-ttu-id="a9109-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="a9109-109">Name</span></span>    | <span data-ttu-id="a9109-110">Valor</span><span class="sxs-lookup"><span data-stu-id="a9109-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a9109-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a9109-111">Scope</span></span>   | <span data-ttu-id="a9109-112">Borde</span><span class="sxs-lookup"><span data-stu-id="a9109-112">Edge</span></span>        |
| <span data-ttu-id="a9109-113">Versión</span><span class="sxs-lookup"><span data-stu-id="a9109-113">Version</span></span> | <span data-ttu-id="a9109-114">4.6</span><span class="sxs-lookup"><span data-stu-id="a9109-114">4.6</span></span>         |
| <span data-ttu-id="a9109-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="a9109-115">Type</span></span>    | <span data-ttu-id="a9109-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="a9109-116">Retargeting</span></span> |
