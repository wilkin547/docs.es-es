---
title: Interfaz ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: c573e6b768aee1e8b681dcf2e828dc24d409025b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793011"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="c8ae7-102">Interfaz ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="c8ae7-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="c8ae7-103">Representa un módulo de Common Language Runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="c8ae7-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8ae7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c8ae7-104">Methods</span></span>  
  
|<span data-ttu-id="c8ae7-105">Método</span><span class="sxs-lookup"><span data-stu-id="c8ae7-105">Method</span></span>|<span data-ttu-id="c8ae7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8ae7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8ae7-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-107">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="c8ae7-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-108">Not implemented.</span></span>|  
|[<span data-ttu-id="c8ae7-109">EnableClassLoadCallbacks (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-109">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="c8ae7-110">Determina si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-110">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="c8ae7-111">EnableJITDebugging (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-111">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="c8ae7-112">Determina si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="c8ae7-113">GetAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-113">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="c8ae7-114">Obtiene el ensamblado contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="c8ae7-115">GetBaseAddress (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-115">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="c8ae7-116">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="c8ae7-117">GetClassFromToken (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-117">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="c8ae7-118">Obtiene el ICorDebugClass de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="c8ae7-119">GetEditAndContinueSnapshot (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-119">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="c8ae7-120">Opción obsoleta.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-120">Deprecated.</span></span>|  
|[<span data-ttu-id="c8ae7-121">GetFunctionFromRVA (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-121">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="c8ae7-122">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-122">Not implemented.</span></span>|  
|[<span data-ttu-id="c8ae7-123">GetFunctionFromToken (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-123">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="c8ae7-124">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="c8ae7-125">GetGlobalVariableValue (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-125">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="c8ae7-126">Obtiene un objeto de valor para la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="c8ae7-127">GetMetaDataInterface (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-127">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="c8ae7-128">Obtiene un puntero de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="c8ae7-129">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-129">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="c8ae7-130">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="c8ae7-131">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-131">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="c8ae7-132">Obtiene el proceso contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="c8ae7-133">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-133">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="c8ae7-134">Obtiene el tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="c8ae7-135">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-135">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="c8ae7-136">Obtiene el token para la entrada de la tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="c8ae7-137">IsDynamic (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-137">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="c8ae7-138">Indica si el módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="c8ae7-139">IsInMemory (método)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-139">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="c8ae7-140">Indica si este módulo solo existe en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8ae7-141">Notas</span><span class="sxs-lookup"><span data-stu-id="c8ae7-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8ae7-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c8ae7-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8ae7-143">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c8ae7-143">Requirements</span></span>  
 <span data-ttu-id="c8ae7-144">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8ae7-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8ae7-145">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8ae7-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8ae7-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8ae7-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8ae7-147">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8ae7-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ae7-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8ae7-148">See also</span></span>

- [<span data-ttu-id="c8ae7-149">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ae7-149">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="c8ae7-150">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c8ae7-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
