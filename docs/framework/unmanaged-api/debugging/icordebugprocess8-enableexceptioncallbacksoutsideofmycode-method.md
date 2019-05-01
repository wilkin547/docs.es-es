---
title: Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08937e87b8bd2249b8608f8ec1ed1f7734961b3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948569"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="b8e62-102">Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="b8e62-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="b8e62-103">[compatible con la versión [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] y posteriores]</span><span class="sxs-lookup"><span data-stu-id="b8e62-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="b8e62-104">Habilita o deshabilita ciertos tipos de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) devoluciones de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="b8e62-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e62-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8e62-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e62-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8e62-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="b8e62-107">[in]</span><span class="sxs-lookup"><span data-stu-id="b8e62-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8e62-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8e62-108">Remarks</span></span>  
 <span data-ttu-id="b8e62-109">Si el valor de `enableExceptionsOutsideOfJMC` es `false`:</span><span class="sxs-lookup"><span data-stu-id="b8e62-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="b8e62-110">No se producirá una excepción DEBUG_EXCEPTION_FIRST_CHANCE una devolución de llamada al depurador.</span><span class="sxs-lookup"><span data-stu-id="b8e62-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="b8e62-111">Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no dará como resultado una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso desde el origen a un controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="b8e62-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="b8e62-112">El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.</span><span class="sxs-lookup"><span data-stu-id="b8e62-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e62-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8e62-113">Requirements</span></span>  
 <span data-ttu-id="b8e62-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e62-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e62-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8e62-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8e62-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8e62-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8e62-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e62-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e62-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8e62-118">See also</span></span>

- [<span data-ttu-id="b8e62-119">ICorDebugProcess8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e62-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="b8e62-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b8e62-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
