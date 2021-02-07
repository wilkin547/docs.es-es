---
description: 'Más información acerca de: interfaz ICorDebugCode3'
title: ICorDebugCode3 (Interfaz)
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
ms.openlocfilehash: 378141395ab4d23e3e33a84c3b14ca4a75d847dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764845"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="0c925-103">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c925-103">ICorDebugCode3 Interface</span></span>

<span data-ttu-id="0c925-104">Proporciona un método que extiende "ICorDebugCode" y "ICorDebugCode2" para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="0c925-104">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c925-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c925-105">Methods</span></span>  
  
|<span data-ttu-id="0c925-106">Método</span><span class="sxs-lookup"><span data-stu-id="0c925-106">Method</span></span>|<span data-ttu-id="0c925-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c925-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c925-108">Método GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="0c925-108">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="0c925-109">Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="0c925-109">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c925-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c925-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c925-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0c925-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c925-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c925-112">Requirements</span></span>  

 <span data-ttu-id="0c925-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c925-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c925-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c925-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c925-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c925-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c925-116">**.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c925-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c925-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c925-117">See also</span></span>

- [<span data-ttu-id="0c925-118">ICorDebugILFrame3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c925-118">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
- [<span data-ttu-id="0c925-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0c925-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
