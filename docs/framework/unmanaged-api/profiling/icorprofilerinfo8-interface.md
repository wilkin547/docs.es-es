---
title: Interface ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: eedd16006781de517587e5138543b9b9eca3ff90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733612"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="795c6-102">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="795c6-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="795c6-103">Una subclase de [ICorProfilerInfo7](icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="795c6-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="795c6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="795c6-104">Methods</span></span>  

| <span data-ttu-id="795c6-105">Método</span><span class="sxs-lookup"><span data-stu-id="795c6-105">Method</span></span>|<span data-ttu-id="795c6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="795c6-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="795c6-107">Método IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="795c6-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="795c6-108">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="795c6-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="795c6-109">Método GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="795c6-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="795c6-110">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="795c6-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="795c6-111">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="795c6-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="795c6-112">Método GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="795c6-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="795c6-113">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="795c6-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="795c6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="795c6-114">Requirements</span></span>  

<span data-ttu-id="795c6-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="795c6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="795c6-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="795c6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="795c6-117">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="795c6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="795c6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="795c6-118">See also</span></span>

- [<span data-ttu-id="795c6-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="795c6-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
