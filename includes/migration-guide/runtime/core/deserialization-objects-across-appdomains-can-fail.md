---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805053"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="d8f62-101">Se puede producir un error en la deserialización de objetos entre dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="d8f62-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d8f62-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8f62-102">Details</span></span>|<span data-ttu-id="d8f62-103">En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d8f62-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="d8f62-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d8f62-104">Suggestion</span></span>|<span data-ttu-id="d8f62-105">Consulte [Mitigación: deserialización de objetos en distintos dominios de aplicación](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="d8f62-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="d8f62-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d8f62-106">Scope</span></span>|<span data-ttu-id="d8f62-107">Borde</span><span class="sxs-lookup"><span data-stu-id="d8f62-107">Edge</span></span>|
|<span data-ttu-id="d8f62-108">Versión</span><span class="sxs-lookup"><span data-stu-id="d8f62-108">Version</span></span>|<span data-ttu-id="d8f62-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d8f62-109">4.5.1</span></span>|
|<span data-ttu-id="d8f62-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="d8f62-110">Type</span></span>|<span data-ttu-id="d8f62-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d8f62-111">Runtime</span></span>|
