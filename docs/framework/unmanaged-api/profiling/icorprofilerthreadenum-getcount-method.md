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
ms.openlocfilehash: a35f2e69515ea520396641effc05371b54ad8afc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702334"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="f980f-102">ICorProfilerThreadEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="f980f-102">ICorProfilerThreadEnum::GetCount Method</span></span>

<span data-ttu-id="f980f-103">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f980f-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f980f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f980f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f980f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f980f-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f980f-106">enuncia Número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f980f-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f980f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f980f-107">Requirements</span></span>  

 <span data-ttu-id="f980f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f980f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f980f-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f980f-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f980f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f980f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f980f-111">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f980f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f980f-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f980f-112">See also</span></span>

- [<span data-ttu-id="f980f-113">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f980f-113">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="f980f-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f980f-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
