---
title: Enumeraciones de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: a83b1aa0b2cc068ed2f73dca04083b1085d45201
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789169"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="b5fd3-102">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b5fd3-102">Debugging Enumerations</span></span>
<span data-ttu-id="b5fd3-103">En esta sección se describen las enumeraciones no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5fd3-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="b5fd3-104">In This Section</span></span>  
 [<span data-ttu-id="b5fd3-105">CLR_DEBUGGING_PROCESS_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="b5fd3-106">Proporciona valores que usa el método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="b5fd3-107">CLRDataEnumMemoryFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-107">CLRDataEnumMemoryFlags Enumeration</span></span>](clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="b5fd3-108">Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="b5fd3-109">COR_PUB_ENUMPROCESS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="b5fd3-110">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="b5fd3-111">CorDebugBlockingReason (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-111">CorDebugBlockingReason Enumeration</span></span>](cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="b5fd3-112">Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="b5fd3-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="b5fd3-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="b5fd3-114">Indica el motivo o los motivos para que se inicie una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="b5fd3-115">CorDebugCodeInvokeKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-115">CorDebugCodeInvokeKind Enumeration</span></span>](cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="b5fd3-116">Describe cómo una función exportada invoca a código administrado.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="b5fd3-117">CorDebugCodeInvokePurpose (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-117">CorDebugCodeInvokePurpose Enumeration</span></span>](cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="b5fd3-118">Explica los motivos por los que una función exportada llama a código administrado.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="b5fd3-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="b5fd3-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="b5fd3-120">Proporciona opciones de depuración adicionales que se pueden usar en una llamada al método [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="b5fd3-121">CorDebugDebugEventKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-121">CorDebugDebugEventKind Enumeration</span></span>](cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="b5fd3-122">Indica el tipo de evento cuya información se descodifica mediante el método [DecodeEvent](icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-122">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="b5fd3-123">CorDebugDecodeEventFlagsWindows (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="b5fd3-124">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="b5fd3-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="b5fd3-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="b5fd3-126">Indica el tipo de devolución de llamada que se realiza desde un evento [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="b5fd3-127">CorDebugExceptionFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-127">CorDebugExceptionFlags Enumeration</span></span>](cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="b5fd3-128">Proporciona información adicional sobre una excepción.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="b5fd3-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="b5fd3-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="b5fd3-130">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="b5fd3-131">CorDebugGCType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-131">CorDebugGCType Enumeration</span></span>](cordebuggctype-enumeration.md)  
 <span data-ttu-id="b5fd3-132">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="b5fd3-133">CorDebugGenerationTypes (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-133">CorDebugGenerationTypes Enumeration</span></span>](cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="b5fd3-134">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="b5fd3-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="b5fd3-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="b5fd3-136">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="b5fd3-137">CorDebugIlToNativeMappingTypes (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="b5fd3-138">Indica si un intervalo de instrucciones nativas determinado se corresponde con una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="b5fd3-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="b5fd3-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="b5fd3-140">Indica los tipos de código que se pueden ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="b5fd3-141">CorDebugInterfaceVersion (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-141">CorDebugInterfaceVersion Enumeration</span></span>](cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="b5fd3-142">Especifica una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="b5fd3-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="b5fd3-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="b5fd3-144">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="b5fd3-145">CorDebugJITCompilerFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-145">CorDebugJITCompilerFlags Enumeration</span></span>](cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="b5fd3-146">Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="b5fd3-147">CorDebugJITCompilerFlagsDeprecated (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="b5fd3-148">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-148">Obsolete.</span></span> <span data-ttu-id="b5fd3-149">En su lugar, use el miembro `CORDEBUG_JIT_DEFAULT` de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="b5fd3-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="b5fd3-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="b5fd3-151">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="b5fd3-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="b5fd3-152">CorDebugMDAFlags (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-152">CorDebugMDAFlags Enumeration</span></span>](cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="b5fd3-153">Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="b5fd3-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="b5fd3-154">CorDebugNGenPolicy (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-154">CorDebugNGenPolicy Enumeration</span></span>](cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="b5fd3-155">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="b5fd3-156">CorDebugPlatform (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-156">CorDebugPlatform Enumeration</span></span>](cordebugplatform-enumeration.md)  
 <span data-ttu-id="b5fd3-157">Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fd3-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="b5fd3-158">CorDebugRecordFormat (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-158">CorDebugRecordFormat Enumeration</span></span>](cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="b5fd3-159">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="b5fd3-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="b5fd3-160">CorDebugRegister</span></span>  
 <span data-ttu-id="b5fd3-161">Especifica los registros asociados con una arquitectura de procesador determinada.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="b5fd3-162">CorDebugSetContextFlag (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-162">CorDebugSetContextFlag Enumeration</span></span>](cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="b5fd3-163">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="b5fd3-164">CorDebugStateChange (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-164">CorDebugStateChange Enumeration</span></span>](cordebugstatechange-enumeration.md)  
 <span data-ttu-id="b5fd3-165">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="b5fd3-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="b5fd3-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="b5fd3-167">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="b5fd3-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="b5fd3-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="b5fd3-169">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="b5fd3-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="b5fd3-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="b5fd3-171">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="b5fd3-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="b5fd3-172">CorDebugUserState</span></span>  
 <span data-ttu-id="b5fd3-173">Indica el estado de uso de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="b5fd3-174">CorGCReferenceType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-174">CorGCReferenceType Enumeration</span></span>](corgcreferencetype-enumeration.md)  
 <span data-ttu-id="b5fd3-175">Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="b5fd3-176">ILCodeKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-176">ILCodeKind Enumeration</span></span>](ilcodekind-enumeration.md)  
 <span data-ttu-id="b5fd3-177">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="b5fd3-178">LoggingLevelEnum (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-178">LoggingLevelEnum Enumeration</span></span>](logginglevelenum-enumeration.md)  
 <span data-ttu-id="b5fd3-179">Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="b5fd3-180">LogSwitchCallReason (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-180">LogSwitchCallReason Enumeration</span></span>](logswitchcallreason-enumeration.md)  
 <span data-ttu-id="b5fd3-181">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="b5fd3-182">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-182">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)  
 <span data-ttu-id="b5fd3-183">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="b5fd3-184">WriteableMetadataUpdateMode (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b5fd3-184">WriteableMetadataUpdateMode Enumeration</span></span>](writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="b5fd3-185">Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span> 

 <span data-ttu-id="b5fd3-186">[Enumeración ClrDataSourceType](clrdatasourcetype-enumeration.md) Proporciona valores utilizados por la estructura de CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="b5fd3-186">[ClrDataSourceType Enumeration](clrdatasourcetype-enumeration.md) Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b5fd3-187">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b5fd3-187">Related Sections</span></span>  
 [<span data-ttu-id="b5fd3-188">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="b5fd3-188">Debugging Coclasses</span></span>](debugging-coclasses.md)  
  
 [<span data-ttu-id="b5fd3-189">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b5fd3-189">Debugging Interfaces</span></span>](debugging-interfaces.md)  
  
 [<span data-ttu-id="b5fd3-190">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="b5fd3-190">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)  
  
 [<span data-ttu-id="b5fd3-191">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b5fd3-191">Debugging Structures</span></span>](debugging-structures.md)
