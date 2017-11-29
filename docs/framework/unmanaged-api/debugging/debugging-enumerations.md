---
title: "Enumeraciones de depuración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c24882f2bd9819043bbc786bd2e5f35129a92744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-enumerations"></a><span data-ttu-id="dccd2-102">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="dccd2-102">Debugging Enumerations</span></span>
<span data-ttu-id="dccd2-103">En esta sección se describen las enumeraciones no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="dccd2-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dccd2-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dccd2-104">In This Section</span></span>  
 [<span data-ttu-id="dccd2-105">CLR_DEBUGGING_PROCESS_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="dccd2-106">Proporciona valores que se usan por el [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccd2-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="dccd2-107">CLRDataEnumMemoryFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="dccd2-108">Indica qué regiones de memoria en una llamada a la [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) debe incluir el método.</span><span class="sxs-lookup"><span data-stu-id="dccd2-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="dccd2-109">COR_PUB_ENUMPROCESS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="dccd2-110">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="dccd2-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="dccd2-111">CorDebugBlockingReason (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="dccd2-112">Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="dccd2-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="dccd2-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="dccd2-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="dccd2-114">Indica el motivo o los motivos para que se inicie una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="dccd2-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="dccd2-115">CorDebugCodeInvokeKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="dccd2-116">Describe cómo una función exportada invoca a código administrado.</span><span class="sxs-lookup"><span data-stu-id="dccd2-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="dccd2-117">Enumeración CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="dccd2-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="dccd2-118">Explica los motivos por los que una función exportada llama a código administrado.</span><span class="sxs-lookup"><span data-stu-id="dccd2-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="dccd2-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="dccd2-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="dccd2-120">Proporciona opciones de depuración adicionales que pueden usarse en una llamada a la [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccd2-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="dccd2-121">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="dccd2-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="dccd2-122">Indica el tipo de evento cuya información se descodifica por la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccd2-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="dccd2-123">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="dccd2-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="dccd2-124">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="dccd2-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="dccd2-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="dccd2-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="dccd2-126">Indica el tipo de devolución de llamada que se realiza desde un [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) eventos.</span><span class="sxs-lookup"><span data-stu-id="dccd2-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="dccd2-127">CorDebugExceptionFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="dccd2-128">Proporciona información adicional sobre una excepción.</span><span class="sxs-lookup"><span data-stu-id="dccd2-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="dccd2-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="dccd2-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="dccd2-130">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="dccd2-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="dccd2-131">CorDebugGCType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="dccd2-132">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="dccd2-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="dccd2-133">CorDebugGenerationTypes (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="dccd2-134">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="dccd2-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="dccd2-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="dccd2-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="dccd2-136">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="dccd2-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="dccd2-137">CorDebugIlToNativeMappingTypes (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="dccd2-138">Indica si un intervalo de instrucciones nativas determinado se corresponde con una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="dccd2-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="dccd2-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="dccd2-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="dccd2-140">Indica los tipos de código que se pueden ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="dccd2-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="dccd2-141">CorDebugInterfaceVersion (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="dccd2-142">Especifica una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.</span><span class="sxs-lookup"><span data-stu-id="dccd2-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="dccd2-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="dccd2-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="dccd2-144">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="dccd2-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="dccd2-145">CorDebugJITCompilerFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="dccd2-146">Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.</span><span class="sxs-lookup"><span data-stu-id="dccd2-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="dccd2-147">CorDebugJITCompilerFlagsDeprecated (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="dccd2-148">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="dccd2-148">Obsolete.</span></span> <span data-ttu-id="dccd2-149">Use la `CORDEBUG_JIT_DEFAULT` miembro de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeración en su lugar.</span><span class="sxs-lookup"><span data-stu-id="dccd2-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="dccd2-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="dccd2-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="dccd2-151">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="dccd2-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="dccd2-152">CorDebugMDAFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="dccd2-153">Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="dccd2-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="dccd2-154">CorDebugNGenPolicy (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="dccd2-155">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="dccd2-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="dccd2-156">CorDebugPlatform (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="dccd2-157">Proporciona valores de plataforma de destino que usan el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccd2-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="dccd2-158">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="dccd2-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="dccd2-159">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="dccd2-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="dccd2-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="dccd2-160">CorDebugRegister</span></span>  
 <span data-ttu-id="dccd2-161">Especifica los registros asociados con una arquitectura de procesador determinada.</span><span class="sxs-lookup"><span data-stu-id="dccd2-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="dccd2-162">CorDebugSetContextFlag (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="dccd2-163">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="dccd2-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="dccd2-164">Enumeración CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="dccd2-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="dccd2-165">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dccd2-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="dccd2-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="dccd2-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="dccd2-167">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="dccd2-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="dccd2-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="dccd2-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="dccd2-169">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="dccd2-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="dccd2-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="dccd2-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="dccd2-171">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="dccd2-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="dccd2-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="dccd2-172">CorDebugUserState</span></span>  
 <span data-ttu-id="dccd2-173">Indica el estado de uso de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="dccd2-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="dccd2-174">CorGCReferenceType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="dccd2-175">Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="dccd2-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="dccd2-176">ILCodeKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="dccd2-177">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="dccd2-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="dccd2-178">LoggingLevelEnum (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="dccd2-179">Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.</span><span class="sxs-lookup"><span data-stu-id="dccd2-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="dccd2-180">LogSwitchCallReason (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="dccd2-181">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dccd2-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="dccd2-182">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="dccd2-183">Indica el tipo de ubicación nativo de una variable.</span><span class="sxs-lookup"><span data-stu-id="dccd2-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="dccd2-184">WriteableMetadataUpdateMode (enumeración)</span><span class="sxs-lookup"><span data-stu-id="dccd2-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="dccd2-185">Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.</span><span class="sxs-lookup"><span data-stu-id="dccd2-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dccd2-186">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="dccd2-186">Related Sections</span></span>  
 [<span data-ttu-id="dccd2-187">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="dccd2-187">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="dccd2-188">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dccd2-188">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="dccd2-189">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="dccd2-189">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="dccd2-190">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="dccd2-190">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
