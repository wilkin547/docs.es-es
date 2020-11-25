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
ms.openlocfilehash: 632a9070eab227bc48ce76c51ea08f98060d680d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722550"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="ba24d-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="ba24d-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="ba24d-103">Asigna el identificador de un subproceso a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="ba24d-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba24d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba24d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba24d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba24d-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="ba24d-106">de IDENTIFICADOR del subproceso que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="ba24d-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="ba24d-107">enuncia Puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="ba24d-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba24d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba24d-108">Remarks</span></span>  

 <span data-ttu-id="ba24d-109">El generador de perfiles debe llamar a la `DuplicateHandle` función de Win32 en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="ba24d-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba24d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba24d-110">Requirements</span></span>  

 <span data-ttu-id="ba24d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba24d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba24d-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba24d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba24d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba24d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba24d-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba24d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba24d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba24d-115">See also</span></span>

- [<span data-ttu-id="ba24d-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba24d-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
