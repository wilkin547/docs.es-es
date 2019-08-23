---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbe6f6a2953c3f815606e881b86a693b7a0e6ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951895"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="e2016-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="e2016-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="e2016-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="e2016-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2016-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2016-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2016-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2016-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="e2016-106">enuncia Un puntero a un valor de [cordebugexceptionflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="e2016-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2016-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2016-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2016-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2016-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2016-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2016-109">Requirements</span></span>  
 <span data-ttu-id="e2016-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2016-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2016-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="e2016-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2016-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2016-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2016-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2016-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2016-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2016-114">See also</span></span>

- [<span data-ttu-id="e2016-115">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2016-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="e2016-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e2016-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
