---
title: ICorDebugValueBreakpoint Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValueBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValueBreakpoint
helpviewer_keywords: ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92de5aa960c9ded27aef09d2c795437e9c599835
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="1160c-102">ICorDebugValueBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="1160c-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="1160c-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores concretos.</span><span class="sxs-lookup"><span data-stu-id="1160c-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1160c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1160c-104">Methods</span></span>  
  
|<span data-ttu-id="1160c-105">Método</span><span class="sxs-lookup"><span data-stu-id="1160c-105">Method</span></span>|<span data-ttu-id="1160c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1160c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1160c-107">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="1160c-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="1160c-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se ha establecido el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="1160c-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1160c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1160c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1160c-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1160c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1160c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1160c-111">Requirements</span></span>  
 <span data-ttu-id="1160c-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1160c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1160c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1160c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1160c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1160c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1160c-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1160c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1160c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1160c-116">See Also</span></span>  
 [<span data-ttu-id="1160c-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1160c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
