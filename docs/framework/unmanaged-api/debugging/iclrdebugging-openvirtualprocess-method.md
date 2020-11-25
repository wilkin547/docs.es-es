---
title: ICLRDebugging::OpenVirtualProcess (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
ms.openlocfilehash: 2edd7f628e17c8dc6cbcbb577d06269ba8c64cb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723550"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="4443e-102">ICLRDebugging::OpenVirtualProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="4443e-102">ICLRDebugging::OpenVirtualProcess Method</span></span>

<span data-ttu-id="4443e-103">Obtiene la interfaz ICorDebugProcess que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4443e-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4443e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4443e-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4443e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4443e-105">Parameters</span></span>  

 `moduleBaseAddress`  
 <span data-ttu-id="4443e-106">de La dirección base de un módulo en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="4443e-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="4443e-107">Se devolverá COR_E_NOT_CLR si el módulo especificado no es un módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="4443e-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="4443e-108">de Una abstracción de destino de datos que permite al depurador administrado inspeccionar el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="4443e-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="4443e-109">El depurador debe implementar la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4443e-109">The debugger must implement the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="4443e-110">Debe implementar la interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) para admitir escenarios en los que el CLR que se está depurando no se instala localmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4443e-110">You should implement the [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="4443e-111">de Una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión.</span><span class="sxs-lookup"><span data-stu-id="4443e-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="4443e-112">Este parámetro es necesario solo si `ppProcess` o `pFlags` no lo es `null` .</span><span class="sxs-lookup"><span data-stu-id="4443e-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="4443e-113">de Versión más alta de CLR que este depurador puede depurar.</span><span class="sxs-lookup"><span data-stu-id="4443e-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="4443e-114">Debe especificar las versiones principal, secundaria y de compilación de la versión de CLR más reciente que admite este depurador y establecer el número de revisión en 65535 para acomodar futuras versiones de servicio de CLR en contexto.</span><span class="sxs-lookup"><span data-stu-id="4443e-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="4443e-115">de IDENTIFICADOR de la interfaz ICorDebugProcess que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="4443e-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="4443e-116">Actualmente, los únicos valores aceptados son IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 y IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="4443e-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="4443e-117">enuncia Puntero a la interfaz COM identificada por `riidProcess` .</span><span class="sxs-lookup"><span data-stu-id="4443e-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4443e-118">[in, out] Versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="4443e-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="4443e-119">En la entrada, este valor puede ser `null` .</span><span class="sxs-lookup"><span data-stu-id="4443e-119">On input, this value can be `null`.</span></span> <span data-ttu-id="4443e-120">También puede apuntar a una estructura de [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) , en cuyo caso el campo de la estructura `wStructVersion` se debe inicializar en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4443e-120">It can also point to a [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="4443e-121">En la salida, la estructura devuelta se `CLR_DEBUGGING_VERSION` rellenará con la información de versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="4443e-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="4443e-122">enuncia Marcas informativas sobre el tiempo de ejecución especificado.</span><span class="sxs-lookup"><span data-stu-id="4443e-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="4443e-123">Vea el tema [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) para obtener una descripción de las marcas.</span><span class="sxs-lookup"><span data-stu-id="4443e-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4443e-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4443e-124">Return Value</span></span>  

 <span data-ttu-id="4443e-125">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4443e-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4443e-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4443e-126">HRESULT</span></span>|<span data-ttu-id="4443e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="4443e-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4443e-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="4443e-128">S_OK</span></span>|<span data-ttu-id="4443e-129">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4443e-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="4443e-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4443e-130">E_POINTER</span></span>|<span data-ttu-id="4443e-131">`pDataTarget` es `null`.</span><span class="sxs-lookup"><span data-stu-id="4443e-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="4443e-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="4443e-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="4443e-133">La devolución de llamada [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) devuelve un error o no proporciona un identificador válido.</span><span class="sxs-lookup"><span data-stu-id="4443e-133">The [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="4443e-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="4443e-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="4443e-135">`pDataTarget` no implementa las interfaces de destino de datos necesarias para esta versión del Runtime.</span><span class="sxs-lookup"><span data-stu-id="4443e-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="4443e-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="4443e-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="4443e-137">El módulo indicado no es un módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="4443e-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="4443e-138">Este valor HRESULT también se devuelve cuando no se puede detectar un módulo CLR porque la memoria está dañada, el módulo no está disponible o la versión de CLR es posterior a la versión de la corrección de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="4443e-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="4443e-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="4443e-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="4443e-140">Esta versión en tiempo de ejecución no admite este modelo de depuración.</span><span class="sxs-lookup"><span data-stu-id="4443e-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="4443e-141">Actualmente, las versiones de CLR no admiten el modelo de depuración antes de la .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4443e-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="4443e-142">El `pwszVersion` parámetro de salida sigue establecido en el valor correcto después de este error.</span><span class="sxs-lookup"><span data-stu-id="4443e-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="4443e-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="4443e-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="4443e-144">La versión de CLR es mayor que la versión que este depurador notifica para admitir.</span><span class="sxs-lookup"><span data-stu-id="4443e-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="4443e-145">El `pwszVersion` parámetro de salida sigue establecido en el valor correcto después de este error.</span><span class="sxs-lookup"><span data-stu-id="4443e-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="4443e-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="4443e-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="4443e-147">La `riidProcess` interfaz no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4443e-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="4443e-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="4443e-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="4443e-149">La `CLR_DEBUGGING_VERSION` estructura no tiene un valor reconocido para `wStructVersion` .</span><span class="sxs-lookup"><span data-stu-id="4443e-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="4443e-150">El único valor aceptado en este momento es 0.</span><span class="sxs-lookup"><span data-stu-id="4443e-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4443e-151">Excepciones</span><span class="sxs-lookup"><span data-stu-id="4443e-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4443e-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4443e-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4443e-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4443e-153">Requirements</span></span>  

 <span data-ttu-id="4443e-154">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4443e-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4443e-155">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4443e-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4443e-156">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4443e-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4443e-157">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4443e-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4443e-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4443e-158">See also</span></span>

- [<span data-ttu-id="4443e-159">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4443e-159">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4443e-160">Depuración</span><span class="sxs-lookup"><span data-stu-id="4443e-160">Debugging</span></span>](index.md)
