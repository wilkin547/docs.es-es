---
title: ICorProfilerThreadEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0301334621a2e393a59e7cc34f2964450a81213f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074175"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="8b1d8-102">ICorProfilerThreadEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="8b1d8-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="8b1d8-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="8b1d8-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b1d8-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b1d8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b1d8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8b1d8-106">[out] Un puntero al puntero de interfaz, que, a su vez, señala a la copia de este [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="8b1d8-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="8b1d8-107">La copia del enumerador mantiene su propio estado de enumeración por separado desde este enumerador.</span><span class="sxs-lookup"><span data-stu-id="8b1d8-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="8b1d8-108">Sin embargo, la posición inicial del cursor de la copia es igual a esta posición actual del cursor del enumerador.</span><span class="sxs-lookup"><span data-stu-id="8b1d8-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b1d8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b1d8-109">Requirements</span></span>  
 <span data-ttu-id="8b1d8-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b1d8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b1d8-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b1d8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b1d8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b1d8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b1d8-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b1d8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1d8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b1d8-114">See also</span></span>

- [<span data-ttu-id="8b1d8-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="8b1d8-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="8b1d8-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8b1d8-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
