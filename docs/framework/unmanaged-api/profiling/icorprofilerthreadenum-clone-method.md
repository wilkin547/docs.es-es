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
ms.openlocfilehash: 84a71ac3a1ba30e20bb6ec7e6a0e31db9d3b5738
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455711"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="e73ec-102">ICorProfilerThreadEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="e73ec-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="e73ec-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="e73ec-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e73ec-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e73ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e73ec-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e73ec-106">[out] Un puntero al puntero de interfaz, que, a su vez, señala a la copia de esta [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="e73ec-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="e73ec-107">La copia del enumerador mantiene su propio estado de enumeración independientemente de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="e73ec-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="e73ec-108">Sin embargo, la posición inicial del cursor de la copia es igual a esta posición actual del cursor del enumerador.</span><span class="sxs-lookup"><span data-stu-id="e73ec-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e73ec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e73ec-109">Requirements</span></span>  
 <span data-ttu-id="e73ec-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e73ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e73ec-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e73ec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e73ec-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e73ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e73ec-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e73ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73ec-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e73ec-114">See Also</span></span>  
 [<span data-ttu-id="e73ec-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="e73ec-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="e73ec-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e73ec-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
