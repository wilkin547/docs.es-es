---
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f85dccd5b59610c52adcf685828984c9344fd49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911282"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="36877-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="36877-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="36877-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="36877-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36877-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36877-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36877-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36877-105">Parameters</span></span>  
 <span data-ttu-id="36877-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="36877-106">ppThread</span></span>  
 <span data-ttu-id="36877-107">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="36877-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36877-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36877-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36877-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="36877-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36877-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36877-110">Requirements</span></span>  
 <span data-ttu-id="36877-111">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36877-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36877-112">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="36877-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36877-113">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36877-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36877-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36877-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36877-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="36877-115">See also</span></span>

- [<span data-ttu-id="36877-116">ICorDebugDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36877-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="36877-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="36877-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
