---
title: Interfaz ICorDebugCode3
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: f2f75c3c54c0fa2d55dc0179c05e4edea6e36738
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777827"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="2ccf7-102">Interfaz ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="2ccf7-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="2ccf7-103">Proporciona un método que extiende "ICorDebugCode" y "ICorDebugCode2" para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ccf7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2ccf7-104">Methods</span></span>  
  
|<span data-ttu-id="2ccf7-105">Método</span><span class="sxs-lookup"><span data-stu-id="2ccf7-105">Method</span></span>|<span data-ttu-id="2ccf7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ccf7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ccf7-107">GetReturnValueLiveOffset (método)</span><span class="sxs-lookup"><span data-stu-id="2ccf7-107">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="2ccf7-108">Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ccf7-109">Notas</span><span class="sxs-lookup"><span data-stu-id="2ccf7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ccf7-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ccf7-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2ccf7-111">Requirements</span></span>  
 <span data-ttu-id="2ccf7-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ccf7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ccf7-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ccf7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ccf7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ccf7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ccf7-115">**.NET Framework versiones:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ccf7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ccf7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ccf7-116">See also</span></span>

- [<span data-ttu-id="2ccf7-117">ICorDebugILFrame3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ccf7-117">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
- [<span data-ttu-id="2ccf7-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2ccf7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
