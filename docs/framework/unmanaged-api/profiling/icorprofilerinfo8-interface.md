---
title: Interfaz ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 210029ed1b1c7d780f3895f975f7a72227bbea80
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973825"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="4b005-102">Interfaz ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="4b005-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="4b005-103">Una subclase de [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="4b005-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="4b005-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4b005-104">Methods</span></span>  

| <span data-ttu-id="4b005-105">Método</span><span class="sxs-lookup"><span data-stu-id="4b005-105">Method</span></span>|<span data-ttu-id="4b005-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4b005-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="4b005-107">Método IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="4b005-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="4b005-108">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="4b005-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="4b005-109">Método GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="4b005-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="4b005-110">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="4b005-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="4b005-111">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="4b005-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="4b005-112">Método GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="4b005-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="4b005-113">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="4b005-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4b005-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b005-114">Requirements</span></span>  
<span data-ttu-id="4b005-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b005-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4b005-116">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="4b005-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="4b005-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b005-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="4b005-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b005-118">See also</span></span>
- [<span data-ttu-id="4b005-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4b005-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
