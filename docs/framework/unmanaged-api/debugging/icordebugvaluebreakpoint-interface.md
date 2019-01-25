---
title: ICorDebugValueBreakpoint (Interfaz1)
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
ms.openlocfilehash: 58e6807b0546eadc4baacc276fa1ba7bda4e3aba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557765"
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="86005-102">ICorDebugValueBreakpoint (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="86005-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="86005-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="86005-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86005-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="86005-104">Methods</span></span>  
  
|<span data-ttu-id="86005-105">Método</span><span class="sxs-lookup"><span data-stu-id="86005-105">Method</span></span>|<span data-ttu-id="86005-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="86005-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86005-107">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="86005-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="86005-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="86005-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86005-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86005-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86005-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="86005-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86005-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86005-111">Requirements</span></span>  
 <span data-ttu-id="86005-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86005-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86005-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86005-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86005-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86005-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86005-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86005-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86005-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="86005-116">See also</span></span>
- [<span data-ttu-id="86005-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="86005-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
