---
title: ICorProfilerFunctionEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e30cc8ff320c1a4a9a69fb2a07427ef4c8a4149
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485374"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="a320b-102">ICorProfilerFunctionEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="a320b-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="a320b-103">Obtiene un puntero de interfaz a una copia de este [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="a320b-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a320b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a320b-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a320b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a320b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a320b-106">[out] Un puntero al puntero de interfaz, que, a su vez, señala a la copia de este [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="a320b-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="a320b-107">La copia del enumerador mantiene su propio estado de enumeración por separado desde este enumerador.</span><span class="sxs-lookup"><span data-stu-id="a320b-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="a320b-108">Sin embargo, la posición inicial del cursor de la copia es igual que la posición del cursor actual de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="a320b-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a320b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a320b-109">Requirements</span></span>  
 <span data-ttu-id="a320b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a320b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a320b-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a320b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a320b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a320b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a320b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a320b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a320b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a320b-114">See also</span></span>
- [<span data-ttu-id="a320b-115">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a320b-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="a320b-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a320b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
