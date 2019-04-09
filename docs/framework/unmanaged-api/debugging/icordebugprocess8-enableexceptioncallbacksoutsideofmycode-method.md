---
title: Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08937e87b8bd2249b8608f8ec1ed1f7734961b3b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184839"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="80fed-102">Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="80fed-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="80fed-103">[compatible con la versión [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] y posteriores]</span><span class="sxs-lookup"><span data-stu-id="80fed-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="80fed-104">Habilita o deshabilita ciertos tipos de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) devoluciones de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="80fed-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80fed-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80fed-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80fed-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="80fed-107">[in]</span><span class="sxs-lookup"><span data-stu-id="80fed-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80fed-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80fed-108">Remarks</span></span>  
 <span data-ttu-id="80fed-109">Si el valor de `enableExceptionsOutsideOfJMC` es `false`:</span><span class="sxs-lookup"><span data-stu-id="80fed-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="80fed-110">No se producirá una excepción DEBUG_EXCEPTION_FIRST_CHANCE una devolución de llamada al depurador.</span><span class="sxs-lookup"><span data-stu-id="80fed-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="80fed-111">Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no dará como resultado una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso desde el origen a un controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="80fed-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="80fed-112">El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.</span><span class="sxs-lookup"><span data-stu-id="80fed-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fed-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80fed-113">Requirements</span></span>  
 <span data-ttu-id="80fed-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80fed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fed-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80fed-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80fed-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80fed-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="80fed-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="80fed-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80fed-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="80fed-118">See also</span></span>

- [<span data-ttu-id="80fed-119">Interfaz de ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="80fed-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="80fed-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="80fed-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
