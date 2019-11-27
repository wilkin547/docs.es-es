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
ms.openlocfilehash: a212a0499b1091f1c77b52951ecef2cb2cace4df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447834"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="a10ef-102">ICorProfilerFunctionEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="a10ef-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="a10ef-103">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a10ef-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a10ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a10ef-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a10ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a10ef-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a10ef-106">enuncia Un puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a10ef-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="a10ef-107">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="a10ef-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="a10ef-108">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="a10ef-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a10ef-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a10ef-109">Requirements</span></span>  
 <span data-ttu-id="a10ef-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a10ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a10ef-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a10ef-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a10ef-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a10ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a10ef-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a10ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10ef-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a10ef-114">See also</span></span>

- [<span data-ttu-id="a10ef-115">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a10ef-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="a10ef-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a10ef-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
