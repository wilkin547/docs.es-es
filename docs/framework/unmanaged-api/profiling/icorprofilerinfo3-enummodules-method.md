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
ms.openlocfilehash: 91550d3328acfb5f3bf2ab461fb2d826ee34c580
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545165"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="585a7-102">ICorProfilerInfo3::EnumModules (Método)</span><span class="sxs-lookup"><span data-stu-id="585a7-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="585a7-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="585a7-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="585a7-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="585a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="585a7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="585a7-106">[out] Un puntero a un [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="585a7-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="585a7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="585a7-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585a7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="585a7-108">Requirements</span></span>  
 <span data-ttu-id="585a7-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="585a7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585a7-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="585a7-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="585a7-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="585a7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="585a7-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585a7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585a7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="585a7-113">See also</span></span>
- [<span data-ttu-id="585a7-114">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="585a7-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="585a7-115">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="585a7-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="585a7-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="585a7-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="585a7-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="585a7-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
