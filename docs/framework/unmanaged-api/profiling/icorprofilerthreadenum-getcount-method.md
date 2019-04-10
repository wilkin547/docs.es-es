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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b02f70f22a7d35bf0fe7816a52c490f88b31217
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218438"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="41810-102">ICorProfilerThreadEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="41810-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="41810-103">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41810-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41810-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41810-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41810-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41810-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="41810-106">[out] El número de subprocesos usados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41810-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41810-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41810-107">Requirements</span></span>  
 <span data-ttu-id="41810-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41810-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41810-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41810-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41810-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41810-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41810-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="41810-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41810-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="41810-112">See also</span></span>

- [<span data-ttu-id="41810-113">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41810-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="41810-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="41810-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
