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
ms.openlocfilehash: 86e17b48bc491c45f8b46be23ab626dc1f2a6962
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709848"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="2c26a-102">Interfaz ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="2c26a-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="2c26a-103">Representa un módulo de Common Language Runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="2c26a-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c26a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2c26a-104">Methods</span></span>  
  
|<span data-ttu-id="2c26a-105">Método</span><span class="sxs-lookup"><span data-stu-id="2c26a-105">Method</span></span>|<span data-ttu-id="2c26a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c26a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c26a-107">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2c26a-107">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="2c26a-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="2c26a-108">Not implemented.</span></span>|  
|[<span data-ttu-id="2c26a-109">Método EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="2c26a-109">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="2c26a-110">Determina si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-110">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="2c26a-111">Método EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="2c26a-111">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="2c26a-112">Determina si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="2c26a-113">Método GetAssembly</span><span class="sxs-lookup"><span data-stu-id="2c26a-113">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="2c26a-114">Obtiene el ensamblado contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="2c26a-115">GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="2c26a-115">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="2c26a-116">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="2c26a-117">GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2c26a-117">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="2c26a-118">Obtiene el ICorDebugClass de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2c26a-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="2c26a-119">Método GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="2c26a-119">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="2c26a-120">Desusado.</span><span class="sxs-lookup"><span data-stu-id="2c26a-120">Deprecated.</span></span>|  
|[<span data-ttu-id="2c26a-121">Método GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="2c26a-121">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="2c26a-122">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="2c26a-122">Not implemented.</span></span>|  
|[<span data-ttu-id="2c26a-123">GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2c26a-123">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="2c26a-124">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2c26a-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="2c26a-125">Método GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="2c26a-125">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="2c26a-126">Obtiene un objeto de valor para la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="2c26a-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="2c26a-127">Método GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="2c26a-127">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="2c26a-128">Obtiene un puntero de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="2c26a-129">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="2c26a-129">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="2c26a-130">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="2c26a-131">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="2c26a-131">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="2c26a-132">Obtiene el proceso contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="2c26a-133">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="2c26a-133">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="2c26a-134">Obtiene el tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="2c26a-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="2c26a-135">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2c26a-135">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="2c26a-136">Obtiene el token para la entrada de la tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="2c26a-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="2c26a-137">Método IsDynamic</span><span class="sxs-lookup"><span data-stu-id="2c26a-137">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="2c26a-138">Indica si el módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="2c26a-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="2c26a-139">Método IsInMemory</span><span class="sxs-lookup"><span data-stu-id="2c26a-139">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="2c26a-140">Indica si este módulo solo existe en la memoria.</span><span class="sxs-lookup"><span data-stu-id="2c26a-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c26a-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c26a-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c26a-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2c26a-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c26a-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c26a-143">Requirements</span></span>  

 <span data-ttu-id="2c26a-144">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c26a-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c26a-145">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c26a-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c26a-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c26a-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c26a-147">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c26a-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c26a-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c26a-148">See also</span></span>

- [<span data-ttu-id="2c26a-149">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c26a-149">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="2c26a-150">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2c26a-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
