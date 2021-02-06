---
description: 'Más información acerca de: ICorProfilerInfo:: Gethandlefromthread ((método)'
title: ICorProfilerInfo::GetHandleFromThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
ms.openlocfilehash: 541a2872bc3cbbe8233e09283b9773957b0a7daf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647562"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="0feb3-103">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="0feb3-103">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="0feb3-104">Asigna el identificador de un subproceso a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="0feb3-104">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0feb3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0feb3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0feb3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0feb3-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="0feb3-107">de IDENTIFICADOR del subproceso que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="0feb3-107">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="0feb3-108">enuncia Puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="0feb3-108">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0feb3-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0feb3-109">Remarks</span></span>  

 <span data-ttu-id="0feb3-110">El generador de perfiles debe llamar a la `DuplicateHandle` función de Win32 en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="0feb3-110">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  

 <span data-ttu-id="0feb3-111">El identificador devuelto por este método es propiedad del tiempo de ejecución y el generador de perfiles nunca debe cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="0feb3-111">The handle returned from this method is owned by the runtime and the profiler should never close it.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0feb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0feb3-112">Requirements</span></span>  

 <span data-ttu-id="0feb3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0feb3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0feb3-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0feb3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0feb3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0feb3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0feb3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0feb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0feb3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0feb3-117">See also</span></span>

- [<span data-ttu-id="0feb3-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0feb3-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
