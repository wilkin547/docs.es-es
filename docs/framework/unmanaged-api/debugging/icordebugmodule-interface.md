---
description: 'Más información acerca de: ICorDebugModule (interfaz)'
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
ms.openlocfilehash: f78023fe9975b609309c1c511380a3a394426283
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660120"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="941ca-103">Interfaz ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="941ca-103">ICorDebugModule Interface</span></span>

<span data-ttu-id="941ca-104">Representa un módulo de Common Language Runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="941ca-104">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="941ca-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="941ca-105">Methods</span></span>  
  
|<span data-ttu-id="941ca-106">Método</span><span class="sxs-lookup"><span data-stu-id="941ca-106">Method</span></span>|<span data-ttu-id="941ca-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="941ca-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="941ca-108">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="941ca-108">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="941ca-109">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="941ca-109">Not implemented.</span></span>|  
|[<span data-ttu-id="941ca-110">Método EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="941ca-110">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="941ca-111">Determina si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-111">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="941ca-112">Método EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="941ca-112">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="941ca-113">Determina si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-113">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="941ca-114">Método GetAssembly</span><span class="sxs-lookup"><span data-stu-id="941ca-114">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="941ca-115">Obtiene el ensamblado contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-115">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="941ca-116">GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="941ca-116">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="941ca-117">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-117">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="941ca-118">Método GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="941ca-118">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="941ca-119">Obtiene el ICorDebugClass de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="941ca-119">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="941ca-120">Método GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="941ca-120">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="941ca-121">En desuso.</span><span class="sxs-lookup"><span data-stu-id="941ca-121">Deprecated.</span></span>|  
|[<span data-ttu-id="941ca-122">Método GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="941ca-122">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="941ca-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="941ca-123">Not implemented.</span></span>|  
|[<span data-ttu-id="941ca-124">Método GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="941ca-124">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="941ca-125">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="941ca-125">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="941ca-126">Método GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="941ca-126">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="941ca-127">Obtiene un objeto de valor para la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="941ca-127">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="941ca-128">Método GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="941ca-128">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="941ca-129">Obtiene un puntero de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-129">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="941ca-130">Método GetName</span><span class="sxs-lookup"><span data-stu-id="941ca-130">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="941ca-131">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-131">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="941ca-132">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="941ca-132">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="941ca-133">Obtiene el proceso contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-133">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="941ca-134">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="941ca-134">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="941ca-135">Obtiene el tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="941ca-135">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="941ca-136">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="941ca-136">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="941ca-137">Obtiene el token para la entrada de la tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="941ca-137">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="941ca-138">Método IsDynamic</span><span class="sxs-lookup"><span data-stu-id="941ca-138">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="941ca-139">Indica si el módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="941ca-139">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="941ca-140">Método IsInMemory</span><span class="sxs-lookup"><span data-stu-id="941ca-140">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="941ca-141">Indica si este módulo solo existe en la memoria.</span><span class="sxs-lookup"><span data-stu-id="941ca-141">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="941ca-142">Observaciones</span><span class="sxs-lookup"><span data-stu-id="941ca-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="941ca-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="941ca-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="941ca-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="941ca-144">Requirements</span></span>  

 <span data-ttu-id="941ca-145">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="941ca-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="941ca-146">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="941ca-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="941ca-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="941ca-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="941ca-148">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="941ca-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941ca-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="941ca-149">See also</span></span>

- [<span data-ttu-id="941ca-150">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="941ca-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="941ca-151">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="941ca-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
