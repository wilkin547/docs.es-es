---
description: 'Más información sobre: ICorDebugProcess8:: EnableExceptionCallbacksOutsideOfMyCode (método)'
title: Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: a85c9d62e5fb62fe620f0901509afa5a03504d4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691281"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="802ce-103">Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="802ce-103">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>

<span data-ttu-id="802ce-104">[Se admite en el .NET Framework 4,6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="802ce-104">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="802ce-105">Habilita o deshabilita determinados tipos de devoluciones de llamada de excepción de [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="802ce-105">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="802ce-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="802ce-106">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="802ce-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="802ce-107">Parameters</span></span>  

 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="802ce-108">[in]</span><span class="sxs-lookup"><span data-stu-id="802ce-108">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="802ce-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="802ce-109">Remarks</span></span>  

 <span data-ttu-id="802ce-110">Si el valor de `enableExceptionsOutsideOfJMC` es `false`:</span><span class="sxs-lookup"><span data-stu-id="802ce-110">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="802ce-111">Una excepción DEBUG_EXCEPTION_FIRST_CHANCE no generará una devolución de llamada al depurador.</span><span class="sxs-lookup"><span data-stu-id="802ce-111">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="802ce-112">Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no generará una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso desde el origen de una excepción al controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).</span><span class="sxs-lookup"><span data-stu-id="802ce-112">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="802ce-113">El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.</span><span class="sxs-lookup"><span data-stu-id="802ce-113">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="802ce-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="802ce-114">Requirements</span></span>  

 <span data-ttu-id="802ce-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="802ce-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="802ce-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="802ce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="802ce-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="802ce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="802ce-118">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="802ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="802ce-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="802ce-119">See also</span></span>

- [<span data-ttu-id="802ce-120">Interfaz de ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="802ce-120">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="802ce-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="802ce-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
