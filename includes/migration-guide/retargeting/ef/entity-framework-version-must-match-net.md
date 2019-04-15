---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234814"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="58115-101">La versión de Entity Framework debe coincidir con la versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="58115-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="58115-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="58115-102">Details</span></span>|<span data-ttu-id="58115-103">La versión de Entity Framework se debe hacer coincidir con la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58115-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="58115-104">Para .NET Framework 4.5 se recomienda Entity Framework 5.</span><span class="sxs-lookup"><span data-stu-id="58115-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="58115-105">Hay algunos problemas conocidos con EF 4.x en un proyecto de .NET Framework 4.5 relacionados con <xref:System.ComponentModel.DataAnnotations>.</span><span class="sxs-lookup"><span data-stu-id="58115-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="58115-106">En .NET 4.5, estos se movieron a otro ensamblado, por lo que hay problemas a la hora de determinar qué anotaciones se van a usar.</span><span class="sxs-lookup"><span data-stu-id="58115-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="58115-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="58115-107">Suggestion</span></span>|<span data-ttu-id="58115-108">Actualizar a Entity Framework 5 para .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="58115-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="58115-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="58115-109">Scope</span></span>|<span data-ttu-id="58115-110">Major</span><span class="sxs-lookup"><span data-stu-id="58115-110">Major</span></span>|
|<span data-ttu-id="58115-111">Versión</span><span class="sxs-lookup"><span data-stu-id="58115-111">Version</span></span>|<span data-ttu-id="58115-112">4.5</span><span class="sxs-lookup"><span data-stu-id="58115-112">4.5</span></span>|
|<span data-ttu-id="58115-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="58115-113">Type</span></span>|<span data-ttu-id="58115-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="58115-114">Retargeting</span></span>|
