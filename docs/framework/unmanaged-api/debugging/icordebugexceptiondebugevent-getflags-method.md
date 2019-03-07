---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c38c3399c95d40acd6fafb05f51eb934647827e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471769"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="4ab64-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="4ab64-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="4ab64-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="4ab64-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ab64-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ab64-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ab64-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="4ab64-106">[out] Un puntero a un [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) valor que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="4ab64-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ab64-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ab64-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ab64-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4ab64-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ab64-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ab64-109">Requirements</span></span>  
 <span data-ttu-id="4ab64-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ab64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ab64-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ab64-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ab64-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ab64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ab64-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ab64-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab64-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ab64-114">See also</span></span>
- [<span data-ttu-id="4ab64-115">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ab64-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="4ab64-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4ab64-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
