---
title: "ICorProfilerModuleEnum::Clone (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.Clone Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d6e5da0912c1926fea4afe513e7140055052416
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="d2dd7-102">ICorProfilerModuleEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="d2dd7-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="d2dd7-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2dd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2dd7-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2dd7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2dd7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d2dd7-106">[out] Un puntero al puntero de interfaz que a su vez señala a la copia de este [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="d2dd7-107">La copia del enumerador mantiene su propio estado de enumeración independientemente de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d2dd7-108">Sin embargo, la posición inicial del cursor de la copia es igual que la posición del cursor actual de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2dd7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2dd7-109">Requirements</span></span>  
 <span data-ttu-id="d2dd7-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2dd7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2dd7-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2dd7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2dd7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2dd7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2dd7-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2dd7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2dd7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2dd7-114">See Also</span></span>  
 [<span data-ttu-id="d2dd7-115">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2dd7-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="d2dd7-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d2dd7-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
