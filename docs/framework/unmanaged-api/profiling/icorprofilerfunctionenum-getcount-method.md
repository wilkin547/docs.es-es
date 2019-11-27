---
title: ICorProfilerFunctionEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
ms.openlocfilehash: 5ccd90e92e83d7f9f6f19a082fb84dc1f1c35f4c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447809"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="e6aa5-102">ICorProfilerFunctionEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="e6aa5-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="e6aa5-103">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="e6aa5-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6aa5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6aa5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6aa5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6aa5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e6aa5-106">enuncia El número de funciones que se cargaron.</span><span class="sxs-lookup"><span data-stu-id="e6aa5-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6aa5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6aa5-107">Requirements</span></span>  
 <span data-ttu-id="e6aa5-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6aa5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6aa5-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6aa5-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6aa5-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6aa5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6aa5-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6aa5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6aa5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6aa5-112">See also</span></span>

- [<span data-ttu-id="e6aa5-113">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6aa5-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="e6aa5-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e6aa5-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
