---
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
ms.openlocfilehash: 44bb98f54debb129f951cc388fea81ca0f17b20c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895321"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="84066-102">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="84066-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="84066-103">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="84066-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84066-104">`Terminate`no debe llamarse hasta que se haya recibido una devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) para todos los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="84066-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84066-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84066-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="84066-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="84066-106">Remarks</span></span>  
 <span data-ttu-id="84066-107">`Terminate`se debe llamar a cuando `ICorDebug` el objeto ya no se necesita.</span><span class="sxs-lookup"><span data-stu-id="84066-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84066-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84066-108">Requirements</span></span>  
 <span data-ttu-id="84066-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84066-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84066-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84066-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84066-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84066-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84066-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84066-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84066-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="84066-113">See also</span></span>

- [<span data-ttu-id="84066-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84066-114">ICorDebug Interface</span></span>](icordebug-interface.md)
