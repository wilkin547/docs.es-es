---
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793535"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="42a93-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="42a93-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="42a93-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="42a93-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42a93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42a93-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="42a93-105">Parameters</span></span>  
 <span data-ttu-id="42a93-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="42a93-106">ppThread</span></span>  
 <span data-ttu-id="42a93-107">[out] Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="42a93-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42a93-108">Notas</span><span class="sxs-lookup"><span data-stu-id="42a93-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42a93-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="42a93-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42a93-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="42a93-110">Requirements</span></span>  
 <span data-ttu-id="42a93-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a93-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42a93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42a93-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42a93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42a93-114">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42a93-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a93-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="42a93-115">See also</span></span>

- [<span data-ttu-id="42a93-116">ICorDebugDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42a93-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="42a93-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="42a93-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
