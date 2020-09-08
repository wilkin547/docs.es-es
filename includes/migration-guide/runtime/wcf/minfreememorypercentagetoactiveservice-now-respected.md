---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496285"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="3b1cf-101">Ahora se respeta MinFreeMemoryPercentageToActiveService</span><span class="sxs-lookup"><span data-stu-id="3b1cf-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="3b1cf-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b1cf-102">Details</span></span>

<span data-ttu-id="3b1cf-103">Este ajuste establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="3b1cf-104">Está diseñado para evitar las excepciones <xref:System.OutOfMemoryException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="3b1cf-105">En .NET Framework 4.5, este ajuste no tenía ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="3b1cf-106">En .NET Framework 4.5.1, este ajuste se respeta.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3b1cf-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3b1cf-107">Suggestion</span></span>

<span data-ttu-id="3b1cf-108">Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="3b1cf-109">Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="3b1cf-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3b1cf-110">Name</span></span>    | <span data-ttu-id="3b1cf-111">Valor</span><span class="sxs-lookup"><span data-stu-id="3b1cf-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3b1cf-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3b1cf-112">Scope</span></span>   |<span data-ttu-id="3b1cf-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="3b1cf-113">Minor</span></span>|
|<span data-ttu-id="3b1cf-114">Versión</span><span class="sxs-lookup"><span data-stu-id="3b1cf-114">Version</span></span>|<span data-ttu-id="3b1cf-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3b1cf-115">4.5.1</span></span>|
|<span data-ttu-id="3b1cf-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b1cf-116">Type</span></span>|<span data-ttu-id="3b1cf-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3b1cf-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3b1cf-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3b1cf-118">Affected APIs</span></span>

<span data-ttu-id="3b1cf-119">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="3b1cf-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
