---
title: ICorProfilerCallback2::HandleCreated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
ms.openlocfilehash: 0c25a5cad01ef0eb268e90c38bd24d638b6f8cc4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865771"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="5b5af-102">ICorProfilerCallback2::HandleCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="5b5af-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="5b5af-103">Notifica al generador de perfiles de código que se ha creado un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5b5af-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b5af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b5af-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b5af-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5b5af-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="5b5af-106">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5b5af-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="5b5af-107">de IDENTIFICADOR del objeto para el que se creó el identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5b5af-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b5af-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5b5af-108">Requirements</span></span>  
 <span data-ttu-id="5b5af-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b5af-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b5af-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b5af-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b5af-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b5af-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b5af-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b5af-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5af-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b5af-113">See also</span></span>

- [<span data-ttu-id="5b5af-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b5af-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5b5af-115">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b5af-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
