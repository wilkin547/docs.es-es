---
title: Interface ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928935"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="914b7-102">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="914b7-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="914b7-103">Una subclase de [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="914b7-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="914b7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="914b7-104">Methods</span></span>  

| <span data-ttu-id="914b7-105">Método</span><span class="sxs-lookup"><span data-stu-id="914b7-105">Method</span></span>|<span data-ttu-id="914b7-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="914b7-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="914b7-107">Método IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="914b7-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="914b7-108">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="914b7-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="914b7-109">Método GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="914b7-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="914b7-110">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="914b7-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="914b7-111">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="914b7-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="914b7-112">Método GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="914b7-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="914b7-113">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="914b7-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="914b7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="914b7-114">Requirements</span></span>  
<span data-ttu-id="914b7-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="914b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="914b7-116">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="914b7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="914b7-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="914b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="914b7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="914b7-118">See also</span></span>

- [<span data-ttu-id="914b7-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="914b7-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
