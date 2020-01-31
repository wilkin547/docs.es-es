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
ms.openlocfilehash: e1bb5a6fd0550f7c25d46fa31ca11a10cec54986
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791077"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="f2238-102">Interfaz ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f2238-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="f2238-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="f2238-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2238-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f2238-104">Methods</span></span>  
  
|<span data-ttu-id="f2238-105">Método</span><span class="sxs-lookup"><span data-stu-id="f2238-105">Method</span></span>|<span data-ttu-id="f2238-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2238-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2238-107">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="f2238-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="f2238-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="f2238-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2238-109">Notas</span><span class="sxs-lookup"><span data-stu-id="f2238-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2238-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f2238-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2238-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f2238-111">Requirements</span></span>  
 <span data-ttu-id="f2238-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2238-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2238-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2238-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2238-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2238-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2238-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2238-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2238-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2238-116">See also</span></span>

- [<span data-ttu-id="f2238-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f2238-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
