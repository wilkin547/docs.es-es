---
title: "ICorDebugThread4::HadUnhandledException (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a79d06f0a65facfbaa821d3dd6af547fd3d0305
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="888ee-102">ICorDebugThread4::HadUnhandledException (Método)</span><span class="sxs-lookup"><span data-stu-id="888ee-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="888ee-103">Indica si el subproceso nunca ha tenido una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="888ee-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="888ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="888ee-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="888ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="888ee-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="888ee-106">[out] Un puntero a la dirección de una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="888ee-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="888ee-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="888ee-107">Return Value</span></span>  
 <span data-ttu-id="888ee-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="888ee-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="888ee-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="888ee-109">HRESULT</span></span>|<span data-ttu-id="888ee-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="888ee-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="888ee-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="888ee-111">S_OK</span></span>|<span data-ttu-id="888ee-112">El subproceso ha tenido una excepción no controlada desde su creación.</span><span class="sxs-lookup"><span data-stu-id="888ee-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="888ee-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="888ee-113">S_FALSE</span></span>|<span data-ttu-id="888ee-114">El subproceso nunca ha tenido una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="888ee-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="888ee-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="888ee-115">Remarks</span></span>  
 <span data-ttu-id="888ee-116">Este método indica si el subproceso nunca ha tenido una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="888ee-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="888ee-117">Cuando se desencadena la devolución de llamada de excepción no controlada o se inicia la operación de adjuntar de JIT nativa, se garantiza que este método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="888ee-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="888ee-118">No hay ninguna garantía de que el [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) método devolverá la excepción no controlada; sin embargo, hará lo siguiente si el proceso no se ha continuado después de obtener la devolución de llamada de excepción no controlada o en adjuntar de JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="888ee-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="888ee-119">Además, es posible (aunque improbable) que haya más de un subproceso con una excepción no controlada en el momento en que se desencadene la operación de adjuntar de JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="888ee-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="888ee-120">En tal caso, no hay ninguna manera de determinar qué excepción desencadenó la de adjuntos JIT.</span><span class="sxs-lookup"><span data-stu-id="888ee-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="888ee-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="888ee-121">Requirements</span></span>  
 <span data-ttu-id="888ee-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="888ee-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="888ee-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="888ee-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="888ee-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="888ee-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="888ee-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="888ee-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888ee-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="888ee-126">See Also</span></span>  
 [<span data-ttu-id="888ee-127">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="888ee-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="888ee-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="888ee-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="888ee-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="888ee-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
