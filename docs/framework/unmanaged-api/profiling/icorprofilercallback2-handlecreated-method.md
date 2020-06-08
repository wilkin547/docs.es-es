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
ms.openlocfilehash: 772f0c00bb850e35a6f5bf7fa4df2b3052999df5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499797"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="8d1ff-102">ICorProfilerCallback2::HandleCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="8d1ff-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="8d1ff-103">Notifica al generador de perfiles de código que se ha creado un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8d1ff-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d1ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d1ff-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d1ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d1ff-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="8d1ff-106">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8d1ff-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="8d1ff-107">de IDENTIFICADOR del objeto para el que se creó el identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8d1ff-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d1ff-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d1ff-108">Requirements</span></span>  
 <span data-ttu-id="8d1ff-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d1ff-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d1ff-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d1ff-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d1ff-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d1ff-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d1ff-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d1ff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1ff-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="8d1ff-113">See also</span></span>

- [<span data-ttu-id="8d1ff-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d1ff-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8d1ff-115">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d1ff-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
