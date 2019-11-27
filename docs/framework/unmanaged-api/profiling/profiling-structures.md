---
title: Estructuras para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 2f3e8cedcc498230311c0b52f7ecc1c2c4fc8ff1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447694"
---
# <a name="profiling-structures"></a><span data-ttu-id="2a49c-102">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2a49c-102">Profiling Structures</span></span>
<span data-ttu-id="2a49c-103">En esta sección se describen las estructuras no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="2a49c-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a49c-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="2a49c-104">In This Section</span></span>  
 [<span data-ttu-id="2a49c-105">COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="2a49c-106">Proporciona a Common Language Runtime información sobre una referencia de ensamblado que debe tener en cuenta a la hora de realizar un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2a49c-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="2a49c-107">COR_PRF_CODE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="2a49c-108">Representa un bloque contiguo de código nativo almacenado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="2a49c-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="2a49c-109">COR_PRF_EX_CLAUSE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="2a49c-110">Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="2a49c-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="2a49c-111">COR_PRF_FUNCTION (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="2a49c-112">Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="2a49c-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="2a49c-113">COR_PRF_FUNCTION_ARGUMENT_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="2a49c-114">Representa los argumentos de una función, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="2a49c-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="2a49c-115">COR_PRF_FUNCTION_ARGUMENT_RANGE (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="2a49c-116">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="2a49c-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="2a49c-117">COR_PRF_GC_GENERATION_RANGE (estructura)</span><span class="sxs-lookup"><span data-stu-id="2a49c-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="2a49c-118">Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2a49c-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2a49c-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2a49c-119">Related Sections</span></span>  
 <span data-ttu-id="2a49c-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="2a49c-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="2a49c-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="2a49c-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="2a49c-122">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2a49c-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="2a49c-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2a49c-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="2a49c-124">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2a49c-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="2a49c-125">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2a49c-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
