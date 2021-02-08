---
description: 'Más información sobre: estructuras de generación de perfiles'
title: Estructuras para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 7a76c49aaa301ba45c41fb2eb3f7770539dcc6c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798893"
---
# <a name="profiling-structures"></a><span data-ttu-id="ad705-103">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad705-103">Profiling Structures</span></span>

<span data-ttu-id="ad705-104">En esta sección se describen las estructuras no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="ad705-104">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad705-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ad705-105">In This Section</span></span>  

 [<span data-ttu-id="ad705-106">COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-106">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="ad705-107">Proporciona a Common Language Runtime información sobre una referencia de ensamblado que debe tener en cuenta a la hora de realizar un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ad705-107">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="ad705-108">COR_PRF_CODE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-108">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="ad705-109">Representa un bloque contiguo de código nativo almacenado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ad705-109">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="ad705-110">COR_PRF_EX_CLAUSE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-110">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="ad705-111">Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="ad705-111">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="ad705-112">COR_PRF_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-112">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="ad705-113">Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="ad705-113">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="ad705-114">COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-114">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="ad705-115">Representa los argumentos de una función, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ad705-115">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="ad705-116">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-116">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="ad705-117">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ad705-117">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="ad705-118">COR_PRF_GC_GENERATION_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad705-118">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="ad705-119">Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ad705-119">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad705-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ad705-120">Related Sections</span></span>  

 <span data-ttu-id="ad705-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="ad705-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="ad705-122">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="ad705-122">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="ad705-123">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad705-123">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="ad705-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad705-124">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="ad705-125">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad705-125">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="ad705-126">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad705-126">Profiling Enumerations</span></span>](profiling-enumerations.md)
