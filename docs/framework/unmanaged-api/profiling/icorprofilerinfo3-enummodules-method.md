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
ms.openlocfilehash: 85adf2dbdbb8c02192a9017bc4f664274a08ee24
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496586"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="edbfc-102">ICorProfilerInfo3::EnumModules (Método)</span><span class="sxs-lookup"><span data-stu-id="edbfc-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="edbfc-103">Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="edbfc-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edbfc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edbfc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edbfc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edbfc-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="edbfc-106">enuncia Puntero a una interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="edbfc-106">[out] A pointer to an [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edbfc-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="edbfc-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edbfc-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edbfc-108">Requirements</span></span>  
 <span data-ttu-id="edbfc-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edbfc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edbfc-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edbfc-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edbfc-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edbfc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edbfc-112">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edbfc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edbfc-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="edbfc-113">See also</span></span>

- [<span data-ttu-id="edbfc-114">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edbfc-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="edbfc-115">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edbfc-115">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="edbfc-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="edbfc-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="edbfc-117">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="edbfc-117">Profiling</span></span>](index.md)
