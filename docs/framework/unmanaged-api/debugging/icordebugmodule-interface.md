---
title: ICorDebugModule Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule
helpviewer_keywords: ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59c24d8305e71aac01843155b86fb54fb1e1263d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule-interface1"></a><span data-ttu-id="9a753-102">ICorDebugModule Interfaz1</span><span class="sxs-lookup"><span data-stu-id="9a753-102">ICorDebugModule Interface1</span></span>
<span data-ttu-id="9a753-103">Representa un módulo de common language runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="9a753-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a753-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9a753-104">Methods</span></span>  
  
|<span data-ttu-id="9a753-105">Método</span><span class="sxs-lookup"><span data-stu-id="9a753-105">Method</span></span>|<span data-ttu-id="9a753-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a753-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a753-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="9a753-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="9a753-108">Not implemented.</span></span>|  
|[<span data-ttu-id="9a753-109">EnableClassLoadCallbacks (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="9a753-110">Determina si el [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) las devoluciones de llamada se llama para este módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="9a753-111">EnableJITDebugging (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="9a753-112">Determina si el compilador de just-in-time (JIT) conserva la información de depuración para los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="9a753-113">GetAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="9a753-114">Obtiene el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="9a753-115">GetBaseAddress (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="9a753-116">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="9a753-117">GetClassFromToken (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="9a753-118">Obtiene el ICorDebugClass desde los metadatos.</span><span class="sxs-lookup"><span data-stu-id="9a753-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="9a753-119">GetEditAndContinueSnapshot (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="9a753-120">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9a753-120">Deprecated.</span></span>|  
|[<span data-ttu-id="9a753-121">GetFunctionFromRVA (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="9a753-122">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="9a753-122">Not implemented.</span></span>|  
|[<span data-ttu-id="9a753-123">GetFunctionFromToken (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="9a753-124">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9a753-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="9a753-125">GetGlobalVariableValue (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="9a753-126">Obtiene un objeto de valor para la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="9a753-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="9a753-127">GetMetaDataInterface (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="9a753-128">Obtiene un puntero de interfaz de metadatos que puede usarse para examinar los metadatos para el módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="9a753-129">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="9a753-130">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="9a753-131">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="9a753-132">Obtiene el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="9a753-133">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="9a753-134">Obtiene el tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="9a753-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="9a753-135">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="9a753-136">Obtiene el token para la entrada de la tabla de este módulo.</span><span class="sxs-lookup"><span data-stu-id="9a753-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="9a753-137">IsDynamic (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="9a753-138">Indica si el módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="9a753-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="9a753-139">IsInMemory (método)</span><span class="sxs-lookup"><span data-stu-id="9a753-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="9a753-140">Indica si este módulo sólo existe en memoria.</span><span class="sxs-lookup"><span data-stu-id="9a753-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a753-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a753-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a753-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9a753-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a753-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a753-143">Requirements</span></span>  
 <span data-ttu-id="9a753-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a753-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a753-145">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a753-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a753-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a753-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a753-147">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a753-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a753-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a753-148">See Also</span></span>  
 [<span data-ttu-id="9a753-149">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a753-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="9a753-150">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9a753-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
