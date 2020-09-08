---
ms.openlocfilehash: fccf349517133245ec85ae3c25cedbfb27a7dd8b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496639"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="8355b-101">El método Replace de las direcciones URL de OData está deshabilitado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8355b-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="8355b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8355b-102">Details</span></span>

<span data-ttu-id="8355b-103">A partir de .NET Framework 4.5, el método Replace de direcciones URL de OData está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8355b-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="8355b-104">Cuando el método Replace de OData esté deshabilitado (ahora, de forma predeterminada), cualquier solicitud de usuario, incluidas las funciones Replace (que son poco frecuentes), generará un error.</span><span class="sxs-lookup"><span data-stu-id="8355b-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8355b-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8355b-105">Suggestion</span></span>

<span data-ttu-id="8355b-106">Si el método Replace es necesario (lo que es poco frecuente), se puede volver a habilitar mediante una opción de configuración (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="8355b-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="8355b-107">No obstante, si el método Replace está activado, puede crear vulnerabilidades de seguridad y solo debería usarse tras una revisión exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="8355b-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="8355b-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8355b-108">Name</span></span>    | <span data-ttu-id="8355b-109">Valor</span><span class="sxs-lookup"><span data-stu-id="8355b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8355b-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8355b-110">Scope</span></span>   |<span data-ttu-id="8355b-111">Borde</span><span class="sxs-lookup"><span data-stu-id="8355b-111">Edge</span></span>|
|<span data-ttu-id="8355b-112">Versión</span><span class="sxs-lookup"><span data-stu-id="8355b-112">Version</span></span>|<span data-ttu-id="8355b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8355b-113">4.5</span></span>|
|<span data-ttu-id="8355b-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="8355b-114">Type</span></span>|<span data-ttu-id="8355b-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8355b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8355b-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8355b-116">Affected APIs</span></span>

- <xref:System.Data.Services.DataService%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``T:System.Data.Services.DataService`1``

-->
