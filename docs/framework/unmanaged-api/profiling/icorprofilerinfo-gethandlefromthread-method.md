---
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
ms.openlocfilehash: 94c2c6e01e4188f1fa13c3b6a9f638d4b79a502f
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678190"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="35d64-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="35d64-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="35d64-103">Asigna el identificador de un subproceso a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="35d64-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35d64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35d64-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35d64-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="35d64-106">de IDENTIFICADOR del subproceso que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="35d64-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="35d64-107">enuncia Puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="35d64-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35d64-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35d64-108">Remarks</span></span>  

 <span data-ttu-id="35d64-109">El generador de perfiles debe llamar a la `DuplicateHandle` función de Win32 en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="35d64-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  

 <span data-ttu-id="35d64-110">El identificador devuelto por este método es propiedad del tiempo de ejecución y el generador de perfiles nunca debe cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="35d64-110">The handle returned from this method is owned by the runtime and the profiler should never close it.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="35d64-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35d64-111">Requirements</span></span>  

 <span data-ttu-id="35d64-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d64-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d64-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35d64-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35d64-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35d64-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35d64-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d64-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d64-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35d64-116">See also</span></span>

- [<span data-ttu-id="35d64-117">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35d64-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
