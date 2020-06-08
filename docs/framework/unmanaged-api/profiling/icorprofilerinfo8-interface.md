---
title: Interface ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2cca915eda44d73aea7469e5f752c57309c2300d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495169"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="f1d8c-102">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="f1d8c-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="f1d8c-103">Una subclase de [ICorProfilerInfo7](icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f1d8c-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="f1d8c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f1d8c-104">Methods</span></span>  

| <span data-ttu-id="f1d8c-105">Método</span><span class="sxs-lookup"><span data-stu-id="f1d8c-105">Method</span></span>|<span data-ttu-id="f1d8c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1d8c-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="f1d8c-107">Método IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="f1d8c-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="f1d8c-108">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="f1d8c-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="f1d8c-109">Método GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="f1d8c-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="f1d8c-110">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="f1d8c-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="f1d8c-111">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f1d8c-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="f1d8c-112">Método GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="f1d8c-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="f1d8c-113">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f1d8c-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f1d8c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1d8c-114">Requirements</span></span>  
<span data-ttu-id="f1d8c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d8c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f1d8c-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1d8c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="f1d8c-117">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f1d8c-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f1d8c-118">See also</span></span>

- [<span data-ttu-id="f1d8c-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1d8c-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
