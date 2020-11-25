---
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: ca6aba7897d9e97743d29db49bd058e140f84e6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713592"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="9251d-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="9251d-102">ICorDebugDebugEvent::GetThread Method</span></span>

<span data-ttu-id="9251d-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="9251d-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9251d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9251d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9251d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9251d-105">Parameters</span></span>  

 <span data-ttu-id="9251d-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="9251d-106">ppThread</span></span>  
 <span data-ttu-id="9251d-107">[out] Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="9251d-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9251d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9251d-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9251d-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9251d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9251d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9251d-110">Requirements</span></span>  

 <span data-ttu-id="9251d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9251d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9251d-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9251d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9251d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9251d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9251d-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9251d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9251d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9251d-115">See also</span></span>

- [<span data-ttu-id="9251d-116">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9251d-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="9251d-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9251d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
