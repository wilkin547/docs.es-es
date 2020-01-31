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
ms.openlocfilehash: 626ecddae8ba91d1830d98210208f9fbee36f073
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868593"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="8400b-102">ICorProfilerInfo3::EnumModules (Método)</span><span class="sxs-lookup"><span data-stu-id="8400b-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="8400b-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8400b-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8400b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8400b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8400b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8400b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8400b-106">enuncia Puntero a una interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8400b-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8400b-107">Notas</span><span class="sxs-lookup"><span data-stu-id="8400b-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8400b-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8400b-108">Requirements</span></span>  
 <span data-ttu-id="8400b-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8400b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8400b-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8400b-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8400b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8400b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8400b-112">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8400b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8400b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8400b-113">See also</span></span>

- [<span data-ttu-id="8400b-114">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8400b-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="8400b-115">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8400b-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="8400b-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8400b-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="8400b-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8400b-117">Profiling</span></span>](index.md)
