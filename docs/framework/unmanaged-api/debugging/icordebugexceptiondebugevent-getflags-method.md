---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 5793d939c8497ef842f614048707f69faa8ac568
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976049"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="2c67d-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="2c67d-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="2c67d-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="2c67d-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c67d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c67d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c67d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c67d-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="2c67d-106">enuncia Un puntero a un valor de [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="2c67d-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c67d-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c67d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c67d-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c67d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c67d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c67d-109">Requirements</span></span>  
 <span data-ttu-id="2c67d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c67d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c67d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c67d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c67d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c67d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c67d-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c67d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c67d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c67d-114">See also</span></span>

- [<span data-ttu-id="2c67d-115">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="2c67d-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="2c67d-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2c67d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
