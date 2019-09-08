---
title: Procedimiento para administrar conflictos de cambios
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 49ccb08a375b612e62a8911e98f8ec08058802db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781839"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="01621-102">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="01621-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="01621-103">proporciona una colección de API que le ayudarán a detectar, evaluar y resolver conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="01621-103">provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01621-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="01621-104">In This Section</span></span>  
 [<span data-ttu-id="01621-105">Procedimientos: Detectar y resolver envíos en conflicto</span><span class="sxs-lookup"><span data-stu-id="01621-105">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="01621-106">Describe cómo detectar y resolver los conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="01621-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="01621-107">Cómo: Especificar Cuándo se inician las excepciones de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="01621-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="01621-108">Describe cómo especificar cuándo debe ser informado de los conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="01621-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="01621-109">Procedimientos: Especificar los miembros para los que se van a probar los conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="01621-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="01621-110">Describe cómo atribuir miembros para especificar si se debe comprobar la existencia de conflictos de simultaneidad entre ellos.</span><span class="sxs-lookup"><span data-stu-id="01621-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="01621-111">Cómo: Recuperar información de conflictos de entidades</span><span class="sxs-lookup"><span data-stu-id="01621-111">How to: Retrieve Entity Conflict Information</span></span>](how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="01621-112">Describe cómo recopilar información sobre los conflictos entre entidades.</span><span class="sxs-lookup"><span data-stu-id="01621-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="01621-113">Procedimientos: Recuperar información de conflictos de miembros</span><span class="sxs-lookup"><span data-stu-id="01621-113">How to: Retrieve Member Conflict Information</span></span>](how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="01621-114">Describe cómo recopilar información sobre los conflictos entre miembros.</span><span class="sxs-lookup"><span data-stu-id="01621-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="01621-115">Cómo: Resolver conflictos conservando los valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="01621-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="01621-116">Describe cómo sobrescribir los valores actuales con valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="01621-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="01621-117">Procedimientos: Resolver conflictos sobrescribiendo los valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="01621-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="01621-118">Describe cómo mantener los valores actuales sobrescribiendo los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="01621-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="01621-119">Cómo: Resolver conflictos mediante la combinación con valores de base de datos</span><span class="sxs-lookup"><span data-stu-id="01621-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="01621-120">Describe cómo resolver un conflicto combinando los valores actuales y los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="01621-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="01621-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="01621-121">Related Sections</span></span>  
 [<span data-ttu-id="01621-122">Simultaneidad optimista: Introducción</span><span class="sxs-lookup"><span data-stu-id="01621-122">Optimistic Concurrency: Overview</span></span>](optimistic-concurrency-overview.md)  
 <span data-ttu-id="01621-123">Explica las condiciones que se aplican a la simultaneidad optimista en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01621-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
