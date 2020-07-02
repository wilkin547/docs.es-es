---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620650"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="54a0e-101">Ahora se respeta MinFreeMemoryPercentageToActiveService</span><span class="sxs-lookup"><span data-stu-id="54a0e-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="54a0e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="54a0e-102">Details</span></span>

<span data-ttu-id="54a0e-103">Este ajuste establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="54a0e-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="54a0e-104">Está diseñado para evitar las excepciones <xref:System.OutOfMemoryException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="54a0e-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="54a0e-105">En .NET Framework 4.5, este ajuste no tenía ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="54a0e-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="54a0e-106">En .NET Framework 4.5.1, este ajuste se respeta.</span><span class="sxs-lookup"><span data-stu-id="54a0e-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="54a0e-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="54a0e-107">Suggestion</span></span>

<span data-ttu-id="54a0e-108">Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración.</span><span class="sxs-lookup"><span data-stu-id="54a0e-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="54a0e-109">Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.</span><span class="sxs-lookup"><span data-stu-id="54a0e-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="54a0e-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="54a0e-110">Name</span></span>    | <span data-ttu-id="54a0e-111">Valor</span><span class="sxs-lookup"><span data-stu-id="54a0e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="54a0e-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="54a0e-112">Scope</span></span>   |<span data-ttu-id="54a0e-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="54a0e-113">Minor</span></span>|
|<span data-ttu-id="54a0e-114">Versión</span><span class="sxs-lookup"><span data-stu-id="54a0e-114">Version</span></span>|<span data-ttu-id="54a0e-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="54a0e-115">4.5.1</span></span>|
|<span data-ttu-id="54a0e-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="54a0e-116">Type</span></span>|<span data-ttu-id="54a0e-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="54a0e-117">Runtime</span></span>|
