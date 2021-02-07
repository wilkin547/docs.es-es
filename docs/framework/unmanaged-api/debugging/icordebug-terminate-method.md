---
description: 'Más información acerca de: ICorDebug:: Terminate (método)'
title: ICorDebug::Terminate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: c2de27a47bfd4c364a09180c75109679234f3cae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754295"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="22e47-103">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="22e47-103">ICorDebug::Terminate Method</span></span>

<span data-ttu-id="22e47-104">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="22e47-104">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22e47-105">`Terminate` no debe llamarse hasta que se haya recibido una devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) para todos los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="22e47-105">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e47-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22e47-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="22e47-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22e47-107">Remarks</span></span>  

 <span data-ttu-id="22e47-108">`Terminate` se debe llamar a cuando el `ICorDebug` objeto ya no se necesita.</span><span class="sxs-lookup"><span data-stu-id="22e47-108">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22e47-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22e47-109">Requirements</span></span>  

 <span data-ttu-id="22e47-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22e47-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22e47-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22e47-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22e47-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22e47-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22e47-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22e47-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e47-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e47-114">See also</span></span>

- [<span data-ttu-id="22e47-115">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22e47-115">ICorDebug Interface</span></span>](icordebug-interface.md)
