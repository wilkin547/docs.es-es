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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167751"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="65779-102">Interfaz ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="65779-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="65779-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="65779-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65779-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="65779-104">Methods</span></span>  
  
|<span data-ttu-id="65779-105">Método</span><span class="sxs-lookup"><span data-stu-id="65779-105">Method</span></span>|<span data-ttu-id="65779-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="65779-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65779-107">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="65779-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="65779-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="65779-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65779-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65779-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65779-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="65779-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65779-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65779-111">Requirements</span></span>  
 <span data-ttu-id="65779-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65779-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65779-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65779-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65779-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65779-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="65779-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="65779-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65779-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="65779-116">See also</span></span>

- [<span data-ttu-id="65779-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="65779-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
