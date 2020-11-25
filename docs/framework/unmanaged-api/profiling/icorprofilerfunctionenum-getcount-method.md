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
ms.openlocfilehash: 3ccf75523eb9362b8ef5c38d224a419502cb8b92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724152"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="05d3c-102">ICorProfilerFunctionEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="05d3c-102">ICorProfilerFunctionEnum::GetCount Method</span></span>

<span data-ttu-id="05d3c-103">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="05d3c-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05d3c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05d3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05d3c-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="05d3c-106">enuncia El número de funciones que se cargaron.</span><span class="sxs-lookup"><span data-stu-id="05d3c-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d3c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05d3c-107">Requirements</span></span>  

 <span data-ttu-id="05d3c-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d3c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d3c-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05d3c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05d3c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05d3c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05d3c-111">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d3c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d3c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05d3c-112">See also</span></span>

- [<span data-ttu-id="05d3c-113">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="05d3c-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="05d3c-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="05d3c-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
