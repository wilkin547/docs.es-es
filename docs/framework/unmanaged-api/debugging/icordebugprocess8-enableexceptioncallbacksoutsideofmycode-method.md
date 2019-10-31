---
title: Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123384"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="03ba2-102">Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="03ba2-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="03ba2-103">[Se admite en el .NET Framework 4,6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="03ba2-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="03ba2-104">Habilita o deshabilita determinados tipos de devoluciones de llamada de excepción de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="03ba2-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ba2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03ba2-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03ba2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03ba2-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="03ba2-107">[in]</span><span class="sxs-lookup"><span data-stu-id="03ba2-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03ba2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03ba2-108">Remarks</span></span>  
 <span data-ttu-id="03ba2-109">Si el valor de `enableExceptionsOutsideOfJMC` es `false`:</span><span class="sxs-lookup"><span data-stu-id="03ba2-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="03ba2-110">Una excepción DEBUG_EXCEPTION_FIRST_CHANCE no producirá una devolución de llamada al depurador.</span><span class="sxs-lookup"><span data-stu-id="03ba2-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="03ba2-111">Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no producirá una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso de un origen de excepción a un controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="03ba2-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="03ba2-112">El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.</span><span class="sxs-lookup"><span data-stu-id="03ba2-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03ba2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03ba2-113">Requirements</span></span>  
 <span data-ttu-id="03ba2-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03ba2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ba2-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03ba2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03ba2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03ba2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03ba2-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03ba2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ba2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="03ba2-118">See also</span></span>

- [<span data-ttu-id="03ba2-119">ICorDebugProcess8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03ba2-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [<span data-ttu-id="03ba2-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="03ba2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
