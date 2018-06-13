---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ba09991e9452a86c6b7a1cbb08a38a71ba2aeaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416769"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="df2d9-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock (Método)</span><span class="sxs-lookup"><span data-stu-id="df2d9-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="df2d9-103">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="df2d9-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df2d9-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df2d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df2d9-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="df2d9-106">[out] El subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="df2d9-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="df2d9-107">[out] El número de veces que este subproceso tendría que liberar el bloqueo antes de volver a ser desenredado.</span><span class="sxs-lookup"><span data-stu-id="df2d9-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df2d9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df2d9-108">Return Value</span></span>  
 <span data-ttu-id="df2d9-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="df2d9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="df2d9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df2d9-110">HRESULT</span></span>|<span data-ttu-id="df2d9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="df2d9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df2d9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="df2d9-112">S_OK</span></span>|<span data-ttu-id="df2d9-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="df2d9-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="df2d9-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="df2d9-114">S_FALSE</span></span>|<span data-ttu-id="df2d9-115">Ningún subproceso administrado posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="df2d9-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="df2d9-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="df2d9-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df2d9-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df2d9-117">Remarks</span></span>  
 <span data-ttu-id="df2d9-118">Si un subproceso administrado posee el bloqueo de monitor en este objeto:</span><span class="sxs-lookup"><span data-stu-id="df2d9-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
-   <span data-ttu-id="df2d9-119">El método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="df2d9-119">The method returns S_OK.</span></span>  
  
-   <span data-ttu-id="df2d9-120">El objeto de subproceso es válido hasta que sale del subproceso.</span><span class="sxs-lookup"><span data-stu-id="df2d9-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="df2d9-121">Si ningún subproceso administrado posee el bloqueo de monitor en este objeto, `ppThread` y `pAcquisitionCount` son iguales, y el método devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="df2d9-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="df2d9-122">Si `ppThread` o `pAcquisitionCount` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="df2d9-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="df2d9-123">Si se produce un error, por ejemplo, que no se puede determinar que, si lo hay, subproceso posee el bloqueo de monitor en este objeto, el método devuelve un HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="df2d9-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df2d9-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df2d9-124">Requirements</span></span>  
 <span data-ttu-id="df2d9-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df2d9-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2d9-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df2d9-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df2d9-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df2d9-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df2d9-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2d9-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2d9-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="df2d9-129">See Also</span></span>  
 [<span data-ttu-id="df2d9-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="df2d9-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="df2d9-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="df2d9-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
