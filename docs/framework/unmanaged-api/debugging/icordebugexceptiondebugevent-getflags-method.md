---
title: ICorDebugExceptionDebugEvent::GetFlags (método)
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af4c7feb7076eeac6089a3255c7832c17a43469b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208844"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="392c5-102">ICorDebugExceptionDebugEvent::GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="392c5-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="392c5-103">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="392c5-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="392c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="392c5-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="392c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="392c5-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="392c5-106">[out] Un puntero a un [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) valor que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="392c5-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="392c5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="392c5-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="392c5-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="392c5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="392c5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="392c5-109">Requirements</span></span>  
 <span data-ttu-id="392c5-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="392c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="392c5-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="392c5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="392c5-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="392c5-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="392c5-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="392c5-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="392c5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="392c5-114">See also</span></span>

- [<span data-ttu-id="392c5-115">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="392c5-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="392c5-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="392c5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
