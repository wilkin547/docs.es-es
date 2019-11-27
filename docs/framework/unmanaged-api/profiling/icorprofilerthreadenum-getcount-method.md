---
title: ICorProfilerThreadEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: 695b720119854de4645b2f14dd55811f2465504a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447644"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="84712-102">ICorProfilerThreadEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="84712-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="84712-103">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="84712-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84712-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84712-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84712-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84712-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="84712-106">enuncia Número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="84712-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84712-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84712-107">Requirements</span></span>  
 <span data-ttu-id="84712-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84712-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84712-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84712-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84712-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84712-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84712-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84712-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84712-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="84712-112">See also</span></span>

- [<span data-ttu-id="84712-113">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84712-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="84712-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="84712-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
