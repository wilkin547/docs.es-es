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
ms.openlocfilehash: c5182fd44f0cc2ad7b836bbcbddc469c89dbacb7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865706"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="91919-102">ICorProfilerCallback2::ThreadNameChanged (Método)</span><span class="sxs-lookup"><span data-stu-id="91919-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="91919-103">Notifica al generador de perfiles de código que el nombre de un subproceso ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="91919-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91919-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91919-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91919-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="91919-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="91919-106">de IDENTIFICADOR del subproceso.</span><span class="sxs-lookup"><span data-stu-id="91919-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="91919-107">de Longitud del nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="91919-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="91919-108">de Nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="91919-108">[in] The new name of the thread.</span></span> <span data-ttu-id="91919-109">El nombre no termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="91919-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91919-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="91919-110">Requirements</span></span>  
 <span data-ttu-id="91919-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91919-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91919-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="91919-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="91919-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91919-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91919-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91919-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91919-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="91919-115">See also</span></span>

- [<span data-ttu-id="91919-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91919-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="91919-117">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91919-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
