---
title: ICorProfilerInfo3::EnumModules (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be5d05c34272b9fa5755b4d0e22fa9094707c5ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093883"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="bdf82-102">ICorProfilerInfo3::EnumModules (Método)</span><span class="sxs-lookup"><span data-stu-id="bdf82-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="bdf82-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bdf82-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdf82-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdf82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bdf82-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="bdf82-106">[out] Un puntero a un [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="bdf82-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdf82-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdf82-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf82-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdf82-108">Requirements</span></span>  
 <span data-ttu-id="bdf82-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf82-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf82-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdf82-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdf82-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdf82-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bdf82-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bdf82-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bdf82-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdf82-113">See also</span></span>

- [<span data-ttu-id="bdf82-114">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdf82-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="bdf82-115">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdf82-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="bdf82-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bdf82-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="bdf82-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bdf82-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
