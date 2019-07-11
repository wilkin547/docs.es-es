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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6403540f9641ce885edf2760370e35f48faf1f10
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780320"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="4f677-102">ICorProfilerFunctionEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="4f677-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="4f677-103">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="4f677-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f677-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f677-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f677-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f677-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4f677-106">[out] El número de funciones que se cargaron.</span><span class="sxs-lookup"><span data-stu-id="4f677-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f677-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f677-107">Requirements</span></span>  
 <span data-ttu-id="4f677-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f677-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f677-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f677-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f677-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f677-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f677-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f677-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f677-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f677-112">See also</span></span>

- [<span data-ttu-id="4f677-113">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f677-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="4f677-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4f677-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
