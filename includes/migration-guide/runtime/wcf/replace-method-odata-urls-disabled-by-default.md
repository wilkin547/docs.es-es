---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805045"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="5c723-101">El método Replace de las direcciones URL de OData está deshabilitado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="5c723-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5c723-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5c723-102">Details</span></span>|<span data-ttu-id="5c723-103">A partir de .NET Framework 4.5, el método Replace de direcciones URL de OData está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c723-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="5c723-104">Cuando el método Replace de OData esté deshabilitado (ahora, de forma predeterminada), cualquier solicitud de usuario, incluidas las funciones Replace (que son poco frecuentes), generará un error.</span><span class="sxs-lookup"><span data-stu-id="5c723-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="5c723-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5c723-105">Suggestion</span></span>|<span data-ttu-id="5c723-106">Si el método Replace es necesario (lo que es poco frecuente), se puede volver a habilitar mediante una opción de configuración (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="5c723-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="5c723-107">No obstante, si el método Replace está activado, puede crear vulnerabilidades de seguridad y solo debería usarse tras una revisión exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="5c723-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="5c723-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5c723-108">Scope</span></span>|<span data-ttu-id="5c723-109">Borde</span><span class="sxs-lookup"><span data-stu-id="5c723-109">Edge</span></span>|
|<span data-ttu-id="5c723-110">Versión</span><span class="sxs-lookup"><span data-stu-id="5c723-110">Version</span></span>|<span data-ttu-id="5c723-111">4.5</span><span class="sxs-lookup"><span data-stu-id="5c723-111">4.5</span></span>|
|<span data-ttu-id="5c723-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c723-112">Type</span></span>|<span data-ttu-id="5c723-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5c723-113">Runtime</span></span>|
|<span data-ttu-id="5c723-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5c723-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
