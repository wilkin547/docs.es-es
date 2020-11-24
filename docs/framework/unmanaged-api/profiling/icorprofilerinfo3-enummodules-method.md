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
ms.openlocfilehash: 698f6abc872a7e072ae47520386aa9c7ddfb44fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681475"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="487a4-102">ICorProfilerInfo3::EnumModules (Método)</span><span class="sxs-lookup"><span data-stu-id="487a4-102">ICorProfilerInfo3::EnumModules Method</span></span>

<span data-ttu-id="487a4-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="487a4-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="487a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="487a4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="487a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="487a4-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="487a4-106">enuncia Puntero a una interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="487a4-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="487a4-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="487a4-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="487a4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="487a4-108">Requirements</span></span>  

 <span data-ttu-id="487a4-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="487a4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="487a4-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="487a4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="487a4-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="487a4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="487a4-112">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="487a4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="487a4-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="487a4-113">See also</span></span>

- [<span data-ttu-id="487a4-114">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="487a4-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="487a4-115">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="487a4-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="487a4-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="487a4-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="487a4-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="487a4-117">Profiling</span></span>](index.md)
