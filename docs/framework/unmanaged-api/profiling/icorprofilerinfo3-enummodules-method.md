---
description: 'Más información sobre: ICorProfilerInfo3:: EnumModules ((método)'
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
ms.openlocfilehash: 9cdb76b77f78fa68eafa111e60b31b738173d658
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646860"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="7837b-103">ICorProfilerInfo3::EnumModules (Método)</span><span class="sxs-lookup"><span data-stu-id="7837b-103">ICorProfilerInfo3::EnumModules Method</span></span>

<span data-ttu-id="7837b-104">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7837b-104">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7837b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7837b-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7837b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7837b-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="7837b-107">enuncia Puntero a una interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7837b-107">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7837b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7837b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7837b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7837b-109">Requirements</span></span>  

 <span data-ttu-id="7837b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7837b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7837b-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7837b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7837b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7837b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7837b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7837b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7837b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7837b-114">See also</span></span>

- [<span data-ttu-id="7837b-115">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7837b-115">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="7837b-116">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7837b-116">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="7837b-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7837b-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7837b-118">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7837b-118">Profiling</span></span>](index.md)
