---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: aaf137b1d851d0de86bde697c9e3a512f34d2aa9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782919"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="0b8e7-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="0b8e7-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="0b8e7-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="0b8e7-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b8e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b8e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b8e7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0b8e7-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="0b8e7-106">enuncia Un puntero a un valor de [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="0b8e7-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b8e7-107">Notas</span><span class="sxs-lookup"><span data-stu-id="0b8e7-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b8e7-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0b8e7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b8e7-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0b8e7-109">Requirements</span></span>  
 <span data-ttu-id="0b8e7-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b8e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b8e7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b8e7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b8e7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b8e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b8e7-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b8e7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b8e7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b8e7-114">See also</span></span>

- [<span data-ttu-id="0b8e7-115">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b8e7-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="0b8e7-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0b8e7-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
