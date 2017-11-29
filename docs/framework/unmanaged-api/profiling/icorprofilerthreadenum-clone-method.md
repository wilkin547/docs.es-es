---
title: "ICorProfilerThreadEnum::Clone (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Clone
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8954381fda72122269e5ebf49863e20f17ac32c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="32d41-102">ICorProfilerThreadEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="32d41-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="32d41-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="32d41-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32d41-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32d41-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32d41-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="32d41-106">[out] Un puntero al puntero de interfaz, que, a su vez, señala a la copia de esta [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="32d41-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="32d41-107">La copia del enumerador mantiene su propio estado de enumeración independientemente de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="32d41-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="32d41-108">Sin embargo, la posición inicial del cursor de la copia es igual a esta posición actual del cursor del enumerador.</span><span class="sxs-lookup"><span data-stu-id="32d41-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d41-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32d41-109">Requirements</span></span>  
 <span data-ttu-id="32d41-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32d41-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d41-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="32d41-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="32d41-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32d41-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32d41-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d41-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="32d41-114">See Also</span></span>  
 [<span data-ttu-id="32d41-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="32d41-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="32d41-116">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="32d41-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
