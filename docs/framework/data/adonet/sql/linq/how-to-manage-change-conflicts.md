---
title: Procedimiento para administrar conflictos de cambios
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 7858dc304d281dfb99755d83eec19b421f63d2ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903388"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="43ac5-102">Procedimiento para administrar conflictos de cambios</span><span class="sxs-lookup"><span data-stu-id="43ac5-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="43ac5-103">Proporciona una colección de API que le ayudarán a descubrir, evaluar y resolver los conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="43ac5-103">provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43ac5-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43ac5-104">In This Section</span></span>  
 [<span data-ttu-id="43ac5-105">Cómo: Detectar y resolver envíos con conflictos</span><span class="sxs-lookup"><span data-stu-id="43ac5-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="43ac5-106">Describe cómo detectar y resolver los conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="43ac5-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="43ac5-107">Cómo: Especificar que las excepciones de simultaneidad cuando se inician</span><span class="sxs-lookup"><span data-stu-id="43ac5-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="43ac5-108">Describe cómo especificar cuándo debe ser informado de los conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="43ac5-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="43ac5-109">Cómo: Especificar que los miembros se comprueban los conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="43ac5-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="43ac5-110">Describe cómo atribuir miembros para especificar si se debe comprobar la existencia de conflictos de simultaneidad entre ellos.</span><span class="sxs-lookup"><span data-stu-id="43ac5-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="43ac5-111">Cómo: Recuperar información de conflicto de entidades</span><span class="sxs-lookup"><span data-stu-id="43ac5-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="43ac5-112">Describe cómo recopilar información sobre los conflictos entre entidades.</span><span class="sxs-lookup"><span data-stu-id="43ac5-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="43ac5-113">Cómo: Recuperar información de conflictos de miembros</span><span class="sxs-lookup"><span data-stu-id="43ac5-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="43ac5-114">Describe cómo recopilar información sobre los conflictos entre miembros.</span><span class="sxs-lookup"><span data-stu-id="43ac5-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="43ac5-115">Cómo: Resolver conflictos de simultaneidad conservando valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="43ac5-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="43ac5-116">Describe cómo sobrescribir los valores actuales con valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43ac5-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="43ac5-117">Cómo: Resolver conflictos de simultaneidad sobrescribiendo valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="43ac5-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="43ac5-118">Describe cómo mantener los valores actuales sobrescribiendo los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43ac5-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="43ac5-119">Cómo: Resolver conflictos de combinación con los valores de la base de datos</span><span class="sxs-lookup"><span data-stu-id="43ac5-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="43ac5-120">Describe cómo resolver un conflicto combinando los valores actuales y los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43ac5-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43ac5-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="43ac5-121">Related Sections</span></span>  
 [<span data-ttu-id="43ac5-122">Simultaneidad optimista: información general</span><span class="sxs-lookup"><span data-stu-id="43ac5-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="43ac5-123">Explica las condiciones que se aplican a la simultaneidad optimista en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43ac5-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
