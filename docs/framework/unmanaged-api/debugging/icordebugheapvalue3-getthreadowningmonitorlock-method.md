---
description: 'Más información sobre: ICorDebugHeapValue3:: Getthreadowningmonitorlock ((método)'
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
ms.openlocfilehash: 9bd9e251c1e04bffd749c0569e4716d4c6fa89e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660705"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="8f7a9-103">ICorDebugHeapValue3::GetThreadOwningMonitorLock (Método)</span><span class="sxs-lookup"><span data-stu-id="8f7a9-103">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>

<span data-ttu-id="8f7a9-104">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-104">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f7a9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7a9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f7a9-106">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="8f7a9-107">enuncia Subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-107">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="8f7a9-108">enuncia Número de veces que este subproceso tendría que liberar el bloqueo antes de que vuelva a ser propiedad.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-108">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f7a9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f7a9-109">Return Value</span></span>  

 <span data-ttu-id="8f7a9-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8f7a9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f7a9-111">HRESULT</span></span>|<span data-ttu-id="8f7a9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f7a9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f7a9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f7a9-113">S_OK</span></span>|<span data-ttu-id="8f7a9-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="8f7a9-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8f7a9-115">S_FALSE</span></span>|<span data-ttu-id="8f7a9-116">Ningún subproceso administrado posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-116">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="8f7a9-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="8f7a9-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f7a9-118">Notas</span><span class="sxs-lookup"><span data-stu-id="8f7a9-118">Remarks</span></span>  

 <span data-ttu-id="8f7a9-119">Si un subproceso administrado posee el bloqueo de monitor en este objeto:</span><span class="sxs-lookup"><span data-stu-id="8f7a9-119">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="8f7a9-120">El método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-120">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="8f7a9-121">El objeto Thread es válido hasta que se cierra el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-121">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="8f7a9-122">Si ningún subproceso administrado posee el bloqueo de monitor en este objeto `ppThread` y no `pAcquisitionCount` se modifica y el método devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-122">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="8f7a9-123">Si `ppThread` o `pAcquisitionCount` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-123">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="8f7a9-124">Si se produce un error de modo que no se pueda determinar cuál es el propietario del subproceso, si existe, el bloqueo de monitor en este objeto, el método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="8f7a9-124">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7a9-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f7a9-125">Requirements</span></span>  

 <span data-ttu-id="8f7a9-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f7a9-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7a9-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f7a9-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f7a9-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f7a9-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f7a9-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7a9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7a9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f7a9-130">See also</span></span>

- [<span data-ttu-id="8f7a9-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8f7a9-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8f7a9-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="8f7a9-132">Debugging</span></span>](index.md)
