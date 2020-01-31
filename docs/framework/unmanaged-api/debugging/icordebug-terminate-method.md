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
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788958"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="d1cc4-102">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="d1cc4-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="d1cc4-103">Finaliza el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="d1cc4-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1cc4-104">no se debe llamar a `Terminate` hasta que se haya recibido una devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) para todos los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="d1cc4-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1cc4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1cc4-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d1cc4-106">Notas</span><span class="sxs-lookup"><span data-stu-id="d1cc4-106">Remarks</span></span>  
 <span data-ttu-id="d1cc4-107">se debe llamar a `Terminate` cuando ya no se necesita el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="d1cc4-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1cc4-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d1cc4-108">Requirements</span></span>  
 <span data-ttu-id="d1cc4-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1cc4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1cc4-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1cc4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1cc4-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1cc4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1cc4-112">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1cc4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1cc4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1cc4-113">See also</span></span>

- [<span data-ttu-id="d1cc4-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1cc4-114">ICorDebug Interface</span></span>](icordebug-interface.md)
