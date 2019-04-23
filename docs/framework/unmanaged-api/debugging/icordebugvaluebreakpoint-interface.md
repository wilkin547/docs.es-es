---
title: Interfaz ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778359a7d26b6e2f19984a1f7ff06a527f2449f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167751"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="395ec-102">Interfaz ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="395ec-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="395ec-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="395ec-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="395ec-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="395ec-104">Methods</span></span>  
  
|<span data-ttu-id="395ec-105">Método</span><span class="sxs-lookup"><span data-stu-id="395ec-105">Method</span></span>|<span data-ttu-id="395ec-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="395ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="395ec-107">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="395ec-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="395ec-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="395ec-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="395ec-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="395ec-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="395ec-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="395ec-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="395ec-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="395ec-111">Requirements</span></span>  
 <span data-ttu-id="395ec-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="395ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="395ec-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="395ec-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="395ec-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="395ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="395ec-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="395ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="395ec-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="395ec-116">See also</span></span>

- [<span data-ttu-id="395ec-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="395ec-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
