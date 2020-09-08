---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496104"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="31b4f-101">Se puede producir un error en la deserialización de objetos entre dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="31b4f-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="31b4f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="31b4f-102">Details</span></span>

<span data-ttu-id="31b4f-103">En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="31b4f-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="31b4f-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="31b4f-104">Suggestion</span></span>

<span data-ttu-id="31b4f-105">Consulte [Mitigación: deserialización de objetos en distintos dominios de aplicación](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="31b4f-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="31b4f-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="31b4f-106">Name</span></span>    | <span data-ttu-id="31b4f-107">Valor</span><span class="sxs-lookup"><span data-stu-id="31b4f-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="31b4f-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="31b4f-108">Scope</span></span>   |<span data-ttu-id="31b4f-109">Borde</span><span class="sxs-lookup"><span data-stu-id="31b4f-109">Edge</span></span>|
|<span data-ttu-id="31b4f-110">Versión</span><span class="sxs-lookup"><span data-stu-id="31b4f-110">Version</span></span>|<span data-ttu-id="31b4f-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="31b4f-111">4.5.1</span></span>|
|<span data-ttu-id="31b4f-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="31b4f-112">Type</span></span>|<span data-ttu-id="31b4f-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="31b4f-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="31b4f-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="31b4f-114">Affected APIs</span></span>

<span data-ttu-id="31b4f-115">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="31b4f-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
