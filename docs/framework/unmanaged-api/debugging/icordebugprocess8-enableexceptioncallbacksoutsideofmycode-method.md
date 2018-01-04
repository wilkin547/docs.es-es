---
title: "Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f13236c865f9a57d77ebf83ab48e010f06ef08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="8a0bc-102">Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="8a0bc-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="8a0bc-103">[compatible con la versión [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] y posteriores]</span><span class="sxs-lookup"><span data-stu-id="8a0bc-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="8a0bc-104">Habilita o deshabilita ciertos tipos de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) las devoluciones de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="8a0bc-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a0bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a0bc-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a0bc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a0bc-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="8a0bc-107">[in]</span><span class="sxs-lookup"><span data-stu-id="8a0bc-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a0bc-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a0bc-108">Remarks</span></span>  
 <span data-ttu-id="8a0bc-109">Si el valor de `enableExceptionsOutsideOfJMC` es `false`:</span><span class="sxs-lookup"><span data-stu-id="8a0bc-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="8a0bc-110">No se producirá una excepción DEBUG_EXCEPTION_FIRST_CHANCE una devolución de llamada al depurador.</span><span class="sxs-lookup"><span data-stu-id="8a0bc-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="8a0bc-111">Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no generará una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso de origen a un controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="8a0bc-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="8a0bc-112">El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.</span><span class="sxs-lookup"><span data-stu-id="8a0bc-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a0bc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a0bc-113">Requirements</span></span>  
 <span data-ttu-id="8a0bc-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a0bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a0bc-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a0bc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a0bc-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a0bc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a0bc-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a0bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0bc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a0bc-118">See Also</span></span>  
 [<span data-ttu-id="8a0bc-119">ICorDebugProcess8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a0bc-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [<span data-ttu-id="8a0bc-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8a0bc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
