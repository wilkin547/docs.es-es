---
description: 'Más información acerca de: ICorProfilerCallback2:: HandleCreated (método)'
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
ms.openlocfilehash: 17f4ed83646907a229dcc6a30dcce1b52fa608d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657091"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="78052-103">ICorProfilerCallback2::HandleCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="78052-103">ICorProfilerCallback2::HandleCreated Method</span></span>

<span data-ttu-id="78052-104">Notifica al generador de perfiles de código que se ha creado un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="78052-104">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78052-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78052-105">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78052-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78052-106">Parameters</span></span>  

 `handleId`  
 <span data-ttu-id="78052-107">de IDENTIFICADOR del identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="78052-107">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="78052-108">de IDENTIFICADOR del objeto para el que se creó el identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="78052-108">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78052-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78052-109">Requirements</span></span>  

 <span data-ttu-id="78052-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78052-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78052-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78052-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78052-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78052-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78052-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78052-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78052-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="78052-114">See also</span></span>

- [<span data-ttu-id="78052-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78052-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="78052-116">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78052-116">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
