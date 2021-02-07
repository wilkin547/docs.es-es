---
description: 'Más información sobre: ICorProfilerInfo4:: Enumthreads ((método)'
title: ICorProfilerInfo4::EnumThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: d597e68b8765e135d5bdb403dbdb161b7acbaa9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686939"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="9be26-103">ICorProfilerInfo4::EnumThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="9be26-103">ICorProfilerInfo4::EnumThreads Method</span></span>

<span data-ttu-id="9be26-104">Devuelve un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="9be26-104">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9be26-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9be26-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9be26-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="9be26-107">enuncia Puntero a una interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9be26-107">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9be26-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9be26-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9be26-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9be26-109">Requirements</span></span>  

 <span data-ttu-id="9be26-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9be26-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9be26-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9be26-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9be26-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9be26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9be26-113">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be26-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be26-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9be26-114">See also</span></span>

- [<span data-ttu-id="9be26-115">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9be26-115">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="9be26-116">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9be26-116">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="9be26-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9be26-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9be26-118">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9be26-118">Profiling</span></span>](index.md)
