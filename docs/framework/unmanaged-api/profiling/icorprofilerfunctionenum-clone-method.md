---
title: "ICorProfilerFunctionEnum::Clone (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Clone Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 449292d8bacd6bb965119da81671c739f12dc3a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="66aa0-102">ICorProfilerFunctionEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="66aa0-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="66aa0-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="66aa0-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66aa0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66aa0-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66aa0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66aa0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="66aa0-106">[out] Un puntero al puntero de interfaz, que, a su vez, señala a la copia de esta [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="66aa0-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="66aa0-107">La copia del enumerador mantiene su propio estado de enumeración independientemente de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="66aa0-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="66aa0-108">Sin embargo, la posición inicial del cursor de la copia es igual que la posición del cursor actual de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="66aa0-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66aa0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66aa0-109">Requirements</span></span>  
 <span data-ttu-id="66aa0-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66aa0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66aa0-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66aa0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66aa0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66aa0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66aa0-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66aa0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66aa0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="66aa0-114">See Also</span></span>  
 [<span data-ttu-id="66aa0-115">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66aa0-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="66aa0-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="66aa0-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
