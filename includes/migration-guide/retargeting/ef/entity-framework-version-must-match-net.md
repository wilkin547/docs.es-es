---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617272"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="72f93-101">La versión de Entity Framework debe coincidir con la versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="72f93-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="72f93-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="72f93-102">Details</span></span>

<span data-ttu-id="72f93-103">La versión de Entity Framework (EF) se debe hacer coincidir con la de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72f93-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="72f93-104">Para .NET Framework 4.5 se recomienda Entity Framework 5.</span><span class="sxs-lookup"><span data-stu-id="72f93-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="72f93-105">Hay algunos problemas conocidos con EF 4.x en un proyecto de .NET Framework 4.5 relacionados con <xref:System.ComponentModel.DataAnnotations>.</span><span class="sxs-lookup"><span data-stu-id="72f93-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="72f93-106">En .NET Framework 4.5, estos se movieron a otro ensamblado, por lo que hay problemas a la hora de determinar qué anotaciones se van a usar.</span><span class="sxs-lookup"><span data-stu-id="72f93-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="72f93-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="72f93-107">Suggestion</span></span>

<span data-ttu-id="72f93-108">Actualizar a Entity Framework 5 para .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="72f93-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="72f93-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="72f93-109">Name</span></span>    | <span data-ttu-id="72f93-110">Valor</span><span class="sxs-lookup"><span data-stu-id="72f93-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="72f93-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="72f93-111">Scope</span></span>   | <span data-ttu-id="72f93-112">Major</span><span class="sxs-lookup"><span data-stu-id="72f93-112">Major</span></span>       |
| <span data-ttu-id="72f93-113">Versión</span><span class="sxs-lookup"><span data-stu-id="72f93-113">Version</span></span> | <span data-ttu-id="72f93-114">4.5</span><span class="sxs-lookup"><span data-stu-id="72f93-114">4.5</span></span>         |
| <span data-ttu-id="72f93-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="72f93-115">Type</span></span>    | <span data-ttu-id="72f93-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="72f93-116">Retargeting</span></span> |
