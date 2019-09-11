---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb92deee21c63c935454ff7c7c4e70be6f770436
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895004"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="ec62d-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="ec62d-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="ec62d-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec62d-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec62d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec62d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec62d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec62d-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="ec62d-106">enuncia Un puntero a un valor de [cordebugexceptionflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec62d-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec62d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec62d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec62d-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ec62d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec62d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec62d-109">Requirements</span></span>  
 <span data-ttu-id="ec62d-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec62d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec62d-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="ec62d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec62d-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec62d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec62d-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec62d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec62d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec62d-114">See also</span></span>

- [<span data-ttu-id="ec62d-115">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec62d-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="ec62d-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ec62d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
