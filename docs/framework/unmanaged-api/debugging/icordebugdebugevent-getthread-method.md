---
title: Método ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 66b4abc4bebfbbde2e6a6b25d2bc0e88839a363f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136645"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="d70ba-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="d70ba-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="d70ba-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="d70ba-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d70ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d70ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d70ba-105">Parameters</span></span>  
 <span data-ttu-id="d70ba-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="d70ba-106">ppThread</span></span>  
 <span data-ttu-id="d70ba-107">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="d70ba-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d70ba-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d70ba-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d70ba-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d70ba-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d70ba-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d70ba-110">Requirements</span></span>  
 <span data-ttu-id="d70ba-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d70ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d70ba-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d70ba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d70ba-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d70ba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d70ba-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d70ba-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70ba-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d70ba-115">See also</span></span>

- [<span data-ttu-id="d70ba-116">ICorDebugDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d70ba-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="d70ba-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d70ba-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
