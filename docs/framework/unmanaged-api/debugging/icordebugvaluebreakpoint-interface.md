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
ms.openlocfilehash: f77268e069d322d0f491f78b154cf63b691e3e38
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966825"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="5d4f1-102">Interfaz ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5d4f1-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="5d4f1-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d4f1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5d4f1-104">Methods</span></span>  
  
|<span data-ttu-id="5d4f1-105">Método</span><span class="sxs-lookup"><span data-stu-id="5d4f1-105">Method</span></span>|<span data-ttu-id="5d4f1-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d4f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d4f1-107">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="5d4f1-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="5d4f1-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d4f1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d4f1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d4f1-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5d4f1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d4f1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d4f1-111">Requirements</span></span>  
 <span data-ttu-id="5d4f1-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d4f1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d4f1-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="5d4f1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d4f1-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d4f1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d4f1-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d4f1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4f1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d4f1-116">See also</span></span>

- [<span data-ttu-id="5d4f1-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5d4f1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
