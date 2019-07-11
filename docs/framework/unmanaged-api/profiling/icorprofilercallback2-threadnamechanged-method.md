---
title: ICorProfilerCallback2::ThreadNameChanged (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ffe25cae7122e65bed6aece7b0f6b2abe82c1eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779293"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="8db82-102">ICorProfilerCallback2::ThreadNameChanged (Método)</span><span class="sxs-lookup"><span data-stu-id="8db82-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="8db82-103">Notifica al generador de perfiles de código que ha cambiado el nombre de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8db82-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8db82-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8db82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8db82-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="8db82-106">[in] El identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8db82-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8db82-107">[in] La longitud del nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8db82-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="8db82-108">[in] El nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8db82-108">[in] The new name of the thread.</span></span> <span data-ttu-id="8db82-109">El nombre no está terminada en null.</span><span class="sxs-lookup"><span data-stu-id="8db82-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db82-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8db82-110">Requirements</span></span>  
 <span data-ttu-id="8db82-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8db82-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db82-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8db82-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8db82-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8db82-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8db82-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8db82-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db82-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8db82-115">See also</span></span>

- [<span data-ttu-id="8db82-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8db82-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8db82-117">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8db82-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
