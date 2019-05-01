---
title: ICorDebugILFrame3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b46c74ec0bfc1fc44bcaca07439c472b0fd8393f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946450"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="b2b20-102">ICorDebugILFrame3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2b20-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="b2b20-103">Proporciona un método que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="b2b20-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="b2b20-104">`ICorDebugILFrame3` es una extensión lógica de las interfaces ICorDebugILFrame y ICorDebugILFrame2.</span><span class="sxs-lookup"><span data-stu-id="b2b20-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2b20-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b2b20-105">Methods</span></span>  
  
|<span data-ttu-id="b2b20-106">Método</span><span class="sxs-lookup"><span data-stu-id="b2b20-106">Method</span></span>|<span data-ttu-id="b2b20-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2b20-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2b20-108">GetReturnValueForILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="b2b20-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="b2b20-109">Obtiene un objeto ICorDebugValue que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="b2b20-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2b20-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2b20-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2b20-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b2b20-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b20-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2b20-112">Requirements</span></span>  
 <span data-ttu-id="b2b20-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2b20-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2b20-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2b20-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2b20-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2b20-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2b20-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2b20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b20-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2b20-117">See also</span></span>

- [<span data-ttu-id="b2b20-118">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2b20-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="b2b20-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b2b20-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
