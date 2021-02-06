---
description: 'Más información acerca de: ICorProfilerThreadEnum:: GetCount (método)'
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
ms.openlocfilehash: 5219dfc71b79be82f769ac7c8230beaf62c6f33e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646431"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="434b1-103">ICorProfilerThreadEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="434b1-103">ICorProfilerThreadEnum::GetCount Method</span></span>

<span data-ttu-id="434b1-104">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="434b1-104">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="434b1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="434b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="434b1-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="434b1-107">enuncia Número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="434b1-107">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="434b1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434b1-108">Requirements</span></span>  

 <span data-ttu-id="434b1-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="434b1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="434b1-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="434b1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="434b1-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="434b1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="434b1-112">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="434b1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434b1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="434b1-113">See also</span></span>

- [<span data-ttu-id="434b1-114">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="434b1-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="434b1-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="434b1-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
