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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3037fc704ffc3aac4d050cef7857261f138f7d35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738070"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="0cfca-102">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="0cfca-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="0cfca-103">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="0cfca-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0cfca-104">`Terminate` no debe llamarse hasta un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) se ha recibido la devolución de llamada para todos los procesos que se está depurados.</span><span class="sxs-lookup"><span data-stu-id="0cfca-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cfca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cfca-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0cfca-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cfca-106">Remarks</span></span>  
 <span data-ttu-id="0cfca-107">`Terminate` debe llamarse cuando la `ICorDebug` objeto ya no es necesario.</span><span class="sxs-lookup"><span data-stu-id="0cfca-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cfca-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cfca-108">Requirements</span></span>  
 <span data-ttu-id="0cfca-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cfca-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cfca-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cfca-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cfca-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cfca-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cfca-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cfca-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cfca-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cfca-113">See also</span></span>

- [<span data-ttu-id="0cfca-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cfca-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
