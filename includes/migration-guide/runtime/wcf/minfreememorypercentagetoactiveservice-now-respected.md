---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235884"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="2d8f7-101">Ahora se respeta MinFreeMemoryPercentageToActiveService</span><span class="sxs-lookup"><span data-stu-id="2d8f7-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2d8f7-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="2d8f7-102">Details</span></span>|<span data-ttu-id="2d8f7-103">Este ajuste establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="2d8f7-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="2d8f7-104">Está diseñado para evitar las excepciones <xref:System.OutOfMemoryException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="2d8f7-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=name> exceptions.</span></span> <span data-ttu-id="2d8f7-105">En .NET Framework 4.5, este ajuste no tenía ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="2d8f7-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="2d8f7-106">En .NET Framework 4.5.1, este ajuste se respeta.</span><span class="sxs-lookup"><span data-stu-id="2d8f7-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>|
|<span data-ttu-id="2d8f7-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="2d8f7-107">Suggestion</span></span>|<span data-ttu-id="2d8f7-108">Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración.</span><span class="sxs-lookup"><span data-stu-id="2d8f7-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="2d8f7-109">Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.</span><span class="sxs-lookup"><span data-stu-id="2d8f7-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>|
|<span data-ttu-id="2d8f7-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="2d8f7-110">Scope</span></span>|<span data-ttu-id="2d8f7-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="2d8f7-111">Minor</span></span>|
|<span data-ttu-id="2d8f7-112">Versión</span><span class="sxs-lookup"><span data-stu-id="2d8f7-112">Version</span></span>|<span data-ttu-id="2d8f7-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="2d8f7-113">4.5.1</span></span>|
|<span data-ttu-id="2d8f7-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="2d8f7-114">Type</span></span>|<span data-ttu-id="2d8f7-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2d8f7-115">Runtime</span></span>|
