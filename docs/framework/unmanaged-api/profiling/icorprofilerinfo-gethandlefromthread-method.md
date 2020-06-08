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
ms.openlocfilehash: 419195d9450bf07e5ad8c7cedcac76e175137c96
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498250"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="bfe97-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="bfe97-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="bfe97-103">Asigna el identificador de un subproceso a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="bfe97-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfe97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfe97-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfe97-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="bfe97-106">de IDENTIFICADOR del subproceso que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="bfe97-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="bfe97-107">enuncia Puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="bfe97-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe97-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfe97-108">Remarks</span></span>  
 <span data-ttu-id="bfe97-109">El generador de perfiles debe llamar a la `DuplicateHandle` función de Win32 en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="bfe97-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe97-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfe97-110">Requirements</span></span>  
 <span data-ttu-id="bfe97-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfe97-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe97-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfe97-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfe97-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfe97-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfe97-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfe97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe97-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="bfe97-115">See also</span></span>

- [<span data-ttu-id="bfe97-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfe97-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
