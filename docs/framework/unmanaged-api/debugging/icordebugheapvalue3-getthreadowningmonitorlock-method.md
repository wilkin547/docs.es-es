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
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788620"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="2e30d-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock (Método)</span><span class="sxs-lookup"><span data-stu-id="2e30d-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="2e30d-103">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="2e30d-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e30d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e30d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e30d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2e30d-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="2e30d-106">enuncia Subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="2e30d-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="2e30d-107">enuncia Número de veces que este subproceso tendría que liberar el bloqueo antes de que vuelva a ser propiedad.</span><span class="sxs-lookup"><span data-stu-id="2e30d-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e30d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e30d-108">Return Value</span></span>  
 <span data-ttu-id="2e30d-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2e30d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2e30d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e30d-110">HRESULT</span></span>|<span data-ttu-id="2e30d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e30d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e30d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e30d-112">S_OK</span></span>|<span data-ttu-id="2e30d-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e30d-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="2e30d-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2e30d-114">S_FALSE</span></span>|<span data-ttu-id="2e30d-115">Ningún subproceso administrado posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="2e30d-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2e30d-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2e30d-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e30d-117">Notas</span><span class="sxs-lookup"><span data-stu-id="2e30d-117">Remarks</span></span>  
 <span data-ttu-id="2e30d-118">Si un subproceso administrado posee el bloqueo de monitor en este objeto:</span><span class="sxs-lookup"><span data-stu-id="2e30d-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="2e30d-119">El método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="2e30d-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="2e30d-120">El objeto Thread es válido hasta que se cierra el subproceso.</span><span class="sxs-lookup"><span data-stu-id="2e30d-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="2e30d-121">Si ningún subproceso administrado posee el bloqueo de monitor en este objeto, `ppThread` y `pAcquisitionCount` no se modifican y el método devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="2e30d-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="2e30d-122">Si `ppThread` o `pAcquisitionCount` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="2e30d-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="2e30d-123">Si se produce un error de modo que no se pueda determinar cuál es el propietario del subproceso, si existe, el bloqueo de monitor en este objeto, el método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="2e30d-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e30d-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2e30d-124">Requirements</span></span>  
 <span data-ttu-id="2e30d-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e30d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e30d-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e30d-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e30d-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e30d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e30d-128">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e30d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e30d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e30d-129">See also</span></span>

- [<span data-ttu-id="2e30d-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2e30d-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2e30d-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="2e30d-131">Debugging</span></span>](index.md)
