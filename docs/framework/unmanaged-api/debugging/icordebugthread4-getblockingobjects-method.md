---
title: "ICorDebugThread4::GetBlockingObjects (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetBlockingObjects Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6783d7f9af67acdff147cc46ea4f856f9b10bf3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="3aa21-102">ICorDebugThread4::GetBlockingObjects (Método)</span><span class="sxs-lookup"><span data-stu-id="3aa21-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="3aa21-103">Proporciona una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras que proporcionan información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3aa21-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3aa21-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3aa21-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3aa21-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="3aa21-106">[out] Un puntero a una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="3aa21-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3aa21-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3aa21-107">Remarks</span></span>  
 <span data-ttu-id="3aa21-108">El primer elemento de la enumeración devuelta corresponde a la primera estructura que está bloqueando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3aa21-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="3aa21-109">El segundo elemento corresponde a un elemento de bloqueo que se produce al ejecutar una llamada a procedimiento asincrónico (APC) cuando se bloquea en la primera y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3aa21-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="3aa21-110">La enumeración es válida solo durante el tiempo que dure el estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="3aa21-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="3aa21-111">Debe llamar a este método mientras el depurador está en un estado sincronizado.</span><span class="sxs-lookup"><span data-stu-id="3aa21-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="3aa21-112">Si `ppBlockingObjectEnum` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="3aa21-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="3aa21-113">Si un subproceso está bloqueado y no se puede determinar el error, el método devuelve un HRESULT que indica un error; en caso contrario, devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="3aa21-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa21-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3aa21-114">Requirements</span></span>  
 <span data-ttu-id="3aa21-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aa21-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa21-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3aa21-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3aa21-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3aa21-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3aa21-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa21-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa21-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aa21-119">See Also</span></span>  
 [<span data-ttu-id="3aa21-120">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3aa21-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="3aa21-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3aa21-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3aa21-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="3aa21-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
