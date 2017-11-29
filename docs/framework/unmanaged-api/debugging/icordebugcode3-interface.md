---
title: ICorDebugCode3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3
helpviewer_keywords: ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee60d052c65df64b1a753166b301ba0012cdc8e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="fab77-102">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fab77-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="fab77-103">Proporciona un método que extiende "ICorDebugCode" y "ICorDebugCode2" para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="fab77-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fab77-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fab77-104">Methods</span></span>  
  
|<span data-ttu-id="fab77-105">Método</span><span class="sxs-lookup"><span data-stu-id="fab77-105">Method</span></span>|<span data-ttu-id="fab77-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fab77-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fab77-107">GetReturnValueLiveOffset (método)</span><span class="sxs-lookup"><span data-stu-id="fab77-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="fab77-108">Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="fab77-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fab77-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fab77-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fab77-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fab77-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fab77-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fab77-111">Requirements</span></span>  
 <span data-ttu-id="fab77-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fab77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fab77-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fab77-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fab77-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fab77-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fab77-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fab77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab77-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab77-116">See Also</span></span>  
    
    
    
 [<span data-ttu-id="fab77-117">ICorDebugILFrame3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fab77-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 [<span data-ttu-id="fab77-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fab77-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
