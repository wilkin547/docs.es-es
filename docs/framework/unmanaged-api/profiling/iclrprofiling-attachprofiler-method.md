---
description: 'Más información sobre: ICLRProfiling:: AttachProfiler (método)'
title: ICLRProfiling::AttachProfiler (Método)
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
ms.openlocfilehash: 11b53b39d3332d1f72304352fad525e5881e05a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648459"
---
# <a name="iclrprofilingattachprofiler-method"></a><span data-ttu-id="537ce-103">ICLRProfiling::AttachProfiler (Método)</span><span class="sxs-lookup"><span data-stu-id="537ce-103">ICLRProfiling::AttachProfiler Method</span></span>

<span data-ttu-id="537ce-104">Asocia el generador de perfiles especificado al proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="537ce-104">Attaches the specified profiler to the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="537ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="537ce-105">Syntax</span></span>  
  
```cpp  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
## <a name="parameters"></a><span data-ttu-id="537ce-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="537ce-106">Parameters</span></span>

- `dwProfileeProcessID`

  <span data-ttu-id="537ce-107">\[en] identificador de proceso del proceso al que se debe adjuntar el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="537ce-107">\[in] The process ID of the process to which the profiler should be attached.</span></span> <span data-ttu-id="537ce-108">En un equipo de 64 bits, el valor de bits del proceso cuyo perfil se ha generado debe coincidir con el valor de bits del proceso desencadenador que llama a `AttachProfiler`.</span><span class="sxs-lookup"><span data-stu-id="537ce-108">On a 64-bit machine, the profiled process's bitness must match the bitness of the trigger process that is calling `AttachProfiler`.</span></span> <span data-ttu-id="537ce-109">Si la cuenta de usuario con la que llama a `AttachProfiler` tiene privilegios administrativos, el proceso de destino puede ser cualquier proceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="537ce-109">If the user account under which `AttachProfiler` is called has administrative privileges, the target process may be any process on the system.</span></span> <span data-ttu-id="537ce-110">De lo contrario, el proceso de destino debe pertenecer a la misma cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="537ce-110">Otherwise, the target process must be owned by the same user account.</span></span>

- `dwMillisecondsMax`

  <span data-ttu-id="537ce-111">\[en] la duración de tiempo, en milisegundos, para `AttachProfiler` que se complete.</span><span class="sxs-lookup"><span data-stu-id="537ce-111">\[in] The time duration, in milliseconds, for `AttachProfiler` to complete.</span></span> <span data-ttu-id="537ce-112">El proceso de desencadenador debe pasar un tiempo de espera que se sabe que es suficiente para que el generador de perfiles determinado complete su inicialización.</span><span class="sxs-lookup"><span data-stu-id="537ce-112">The trigger process should pass a timeout that is known to be sufficient for the particular profiler to complete its initialization.</span></span>
  
- `pClsidProfiler`

  <span data-ttu-id="537ce-113">\[in] un puntero al CLSID del generador de perfiles que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="537ce-113">\[in] A pointer to the CLSID of the profiler to be loaded.</span></span> <span data-ttu-id="537ce-114">El proceso desencadenador puede reutilizar esta memoria después de que `AttachProfiler` vuelva.</span><span class="sxs-lookup"><span data-stu-id="537ce-114">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span>

- `wszProfilerPath`

  <span data-ttu-id="537ce-115">\[en] ruta de acceso completa al archivo DLL del generador de perfiles que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="537ce-115">\[in] The full path to the profiler’s DLL file to be loaded.</span></span> <span data-ttu-id="537ce-116">Esta cadena debe contener un máximo de 260 caracteres, incluido el terminador NULL.</span><span class="sxs-lookup"><span data-stu-id="537ce-116">This string should contain no more than 260 characters, including the null terminator.</span></span> <span data-ttu-id="537ce-117">Si `wszProfilerPath` es NULL o una cadena vacía, Common Language Runtime (CLR) intentará encontrar la ubicación del archivo DLL del generador de perfiles; para ello, buscará en el Registro el CLSID al que `pClsidProfiler` apunta.</span><span class="sxs-lookup"><span data-stu-id="537ce-117">If `wszProfilerPath` is null or an empty string, the common language runtime (CLR) will try to find the location of the profiler’s DLL file by looking in the registry for the CLSID that `pClsidProfiler` points to.</span></span>

- `pvClientData`

  <span data-ttu-id="537ce-118">\[in] un puntero a los datos que se van a pasar al generador de perfiles mediante el método [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) .</span><span class="sxs-lookup"><span data-stu-id="537ce-118">\[in] A pointer to data to be passed to the profiler by the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method.</span></span> <span data-ttu-id="537ce-119">El proceso desencadenador puede reutilizar esta memoria después de que `AttachProfiler` vuelva.</span><span class="sxs-lookup"><span data-stu-id="537ce-119">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span> <span data-ttu-id="537ce-120">Si `pvClientData` es NULL, `cbClientData` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="537ce-120">If `pvClientData` is null, `cbClientData` must be 0 (zero).</span></span>

- `cbClientData`

  <span data-ttu-id="537ce-121">\[in] tamaño, en bytes, de los datos a los que `pvClientData` señala.</span><span class="sxs-lookup"><span data-stu-id="537ce-121">\[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>

## <a name="return-value"></a><span data-ttu-id="537ce-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="537ce-122">Return Value</span></span>  

 <span data-ttu-id="537ce-123">Este método devuelve los HRESULT siguientes.</span><span class="sxs-lookup"><span data-stu-id="537ce-123">This method returns the following HRESULTs.</span></span>  
  
|<span data-ttu-id="537ce-124">HRESULT</span><span class="sxs-lookup"><span data-stu-id="537ce-124">HRESULT</span></span>|<span data-ttu-id="537ce-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="537ce-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="537ce-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="537ce-126">S_OK</span></span>|<span data-ttu-id="537ce-127">El generador de perfiles especificado se ha asociado correctamente al proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="537ce-127">The specified profiler has successfully attached to the target process.</span></span>|  
|<span data-ttu-id="537ce-128">CORPROF_E_PROFILER_ALREADY_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="537ce-128">CORPROF_E_PROFILER_ALREADY_ACTIVE</span></span>|<span data-ttu-id="537ce-129">Ya hay un generador de perfiles activo o asociado al proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="537ce-129">There is already a profiler active or attaching to the target process.</span></span>|  
|<span data-ttu-id="537ce-130">CORPROF_E_PROFILER_NOT_ATTACHABLE</span><span class="sxs-lookup"><span data-stu-id="537ce-130">CORPROF_E_PROFILER_NOT_ATTACHABLE</span></span>|<span data-ttu-id="537ce-131">El generador de perfiles especificado no admite la asociación.</span><span class="sxs-lookup"><span data-stu-id="537ce-131">The specified profiler does not support attachment.</span></span> <span data-ttu-id="537ce-132">El proceso desencadenador puede intentar asociar un generador de perfiles diferente.</span><span class="sxs-lookup"><span data-stu-id="537ce-132">The trigger process may attempt to attach a different profiler.</span></span>|  
|<span data-ttu-id="537ce-133">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span><span class="sxs-lookup"><span data-stu-id="537ce-133">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span></span>|<span data-ttu-id="537ce-134">No puede solicitar la asociación de un generador de perfiles porque la versión del proceso de destino es incompatible con el proceso actual que está llamando a `AttachProfiler`.</span><span class="sxs-lookup"><span data-stu-id="537ce-134">Unable to request a profiler attachment, because the version of the target process is incompatible with the current process that is calling `AttachProfiler`.</span></span>|  
|<span data-ttu-id="537ce-135">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span><span class="sxs-lookup"><span data-stu-id="537ce-135">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span></span>|<span data-ttu-id="537ce-136">El usuario del proceso desencadenador no tiene acceso al proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="537ce-136">The user of the trigger process does not have access to the target process.</span></span>|  
|<span data-ttu-id="537ce-137">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span><span class="sxs-lookup"><span data-stu-id="537ce-137">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span></span>|<span data-ttu-id="537ce-138">El usuario del proceso desencadenador no tiene los privilegios necesarios para asociar un generador de perfiles al proceso de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="537ce-138">The user of the trigger process does not have the privileges necessary to attach a profiler to the given target process.</span></span> <span data-ttu-id="537ce-139">El registro de eventos de aplicación puede contener más información.</span><span class="sxs-lookup"><span data-stu-id="537ce-139">The application event log may contain more information.</span></span>|  
|<span data-ttu-id="537ce-140">CORPROF_E_IPC_FAILED</span><span class="sxs-lookup"><span data-stu-id="537ce-140">CORPROF_E_IPC_FAILED</span></span>|<span data-ttu-id="537ce-141">Se produjo un error de comunicación con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="537ce-141">A failure occurred when communicating with the target process.</span></span> <span data-ttu-id="537ce-142">Esto suele ocurrir si el proceso de destino se estaba cerrando.</span><span class="sxs-lookup"><span data-stu-id="537ce-142">This commonly happens if the target process was shutting down.</span></span>|  
|<span data-ttu-id="537ce-143">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="537ce-143">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span></span>|<span data-ttu-id="537ce-144">El proceso de destino no existe o no está ejecutando ningún CLR que admita la asociación.</span><span class="sxs-lookup"><span data-stu-id="537ce-144">The target process does not exist or is not running a CLR that supports attachment.</span></span> <span data-ttu-id="537ce-145">Esto puede indicar que el CLR se descargó desde la llamada al método de enumeración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="537ce-145">This may indicate that the CLR was unloaded since the call to the runtime enumeration method.</span></span>|  
|<span data-ttu-id="537ce-146">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="537ce-146">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span></span>|<span data-ttu-id="537ce-147">El tiempo de espera se agotó sin que el generador de perfiles comenzara a cargarse.</span><span class="sxs-lookup"><span data-stu-id="537ce-147">The timeout expired without beginning to load the profiler.</span></span> <span data-ttu-id="537ce-148">Puede volver a intentar la operación de asociación.</span><span class="sxs-lookup"><span data-stu-id="537ce-148">You can retry the attach operation.</span></span> <span data-ttu-id="537ce-149">El tiempo de espera se agota cuando un finalizador del proceso de destino se ejecuta durante más tiempo que el valor del tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="537ce-149">Timeouts occur when a finalizer in the target process runs for a longer time than the timeout value.</span></span>|  
|<span data-ttu-id="537ce-150">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="537ce-150">E_INVALIDARG</span></span>|<span data-ttu-id="537ce-151">Uno o más parámetros tienen valores no válidos.</span><span class="sxs-lookup"><span data-stu-id="537ce-151">One or more parameters have invalid values.</span></span>|  
|<span data-ttu-id="537ce-152">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="537ce-152">E_FAIL</span></span>|<span data-ttu-id="537ce-153">Se ha producido algún otro error no especificado.</span><span class="sxs-lookup"><span data-stu-id="537ce-153">Some other, unspecified failure occurred.</span></span>|  
|<span data-ttu-id="537ce-154">Otros códigos de error</span><span class="sxs-lookup"><span data-stu-id="537ce-154">Other error codes</span></span>|<span data-ttu-id="537ce-155">Si el método [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) del generador de perfiles devuelve un valor HRESULT que indica un error, `AttachProfiler` devuelve el mismo HRESULT.</span><span class="sxs-lookup"><span data-stu-id="537ce-155">If the profiler’s [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method returns an HRESULT that indicates failure, `AttachProfiler` returns that same HRESULT.</span></span> <span data-ttu-id="537ce-156">En este caso, E_NOTIMPL se convierte en CORPROF_E_PROFILER_NOT_ATTACHABLE.</span><span class="sxs-lookup"><span data-stu-id="537ce-156">In this case, E_NOTIMPL is converted to CORPROF_E_PROFILER_NOT_ATTACHABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="537ce-157">Observaciones</span><span class="sxs-lookup"><span data-stu-id="537ce-157">Remarks</span></span>  
  
## <a name="memory-management"></a><span data-ttu-id="537ce-158">Administración de memoria</span><span class="sxs-lookup"><span data-stu-id="537ce-158">Memory Management</span></span>  

 <span data-ttu-id="537ce-159">En consonancia con las convenciones de COM, el llamador de `AttachProfiler` (por ejemplo, el código desencadenador creado por el desarrollador del generador de perfiles) es responsable de la asignación y desasignación de la memoria para los datos a los que el parámetro `pvClientData` apunta.</span><span class="sxs-lookup"><span data-stu-id="537ce-159">In keeping with COM conventions, the caller of `AttachProfiler` (for example, the trigger code authored by the profiler developer) is responsible for allocating and de-allocating the memory for the data that the `pvClientData` parameter points to.</span></span> <span data-ttu-id="537ce-160">Cuando el CLR ejecuta la llamada a `AttachProfiler`, realiza una copia de la memoria a la que `pvClientData` apunta y la transmite al proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="537ce-160">When the CLR executes the `AttachProfiler` call, it makes a copy of the memory that `pvClientData` points to and transmits it to the target process.</span></span> <span data-ttu-id="537ce-161">Cuando el CLR dentro del proceso de destino recibe su propia copia del bloque `pvClientData`, pasa el bloque al generador de perfiles con el método `InitializeForAttach` y, después, desasigna su copia del bloque `pvClientData` del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="537ce-161">When the CLR inside the target process receives its own copy of the `pvClientData` block, it passes the block to the profiler through the `InitializeForAttach` method, and then deallocates its copy of the `pvClientData` block from the target process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="537ce-162">Requisitos</span><span class="sxs-lookup"><span data-stu-id="537ce-162">Requirements</span></span>  

 <span data-ttu-id="537ce-163">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="537ce-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537ce-164">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="537ce-164">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="537ce-165">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="537ce-165">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="537ce-166">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="537ce-166">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537ce-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="537ce-167">See also</span></span>

- [<span data-ttu-id="537ce-168">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="537ce-168">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="537ce-169">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="537ce-169">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="537ce-170">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="537ce-170">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="537ce-171">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="537ce-171">Profiling</span></span>](index.md)
