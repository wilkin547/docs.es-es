---
description: 'Más información acerca de: depurar enumeraciones'
title: Enumeraciones de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: 4a1d2fc9061fec7f5384418e4893c357f5d340ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801428"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="eb5a7-103">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="eb5a7-103">Debugging Enumerations</span></span>

<span data-ttu-id="eb5a7-104">En esta sección se describen las enumeraciones no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-104">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb5a7-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eb5a7-105">In This Section</span></span>  

 [<span data-ttu-id="eb5a7-106">CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-106">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="eb5a7-107">Proporciona valores que usa el método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-107">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="eb5a7-108">CLRDataEnumMemoryFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-108">CLRDataEnumMemoryFlags Enumeration</span></span>](clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="eb5a7-109">Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-109">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="eb5a7-110">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-110">COR_PUB_ENUMPROCESS Enumeration</span></span>](cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="eb5a7-111">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-111">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="eb5a7-112">CorDebugBlockingReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-112">CorDebugBlockingReason Enumeration</span></span>](cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="eb5a7-113">Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-113">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="eb5a7-114">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="eb5a7-114">CorDebugChainReason</span></span>  
 <span data-ttu-id="eb5a7-115">Indica el motivo o los motivos para que se inicie una cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-115">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="eb5a7-116">Enumeración CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="eb5a7-116">CorDebugCodeInvokeKind Enumeration</span></span>](cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="eb5a7-117">Describe cómo una función exportada invoca a código administrado.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-117">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="eb5a7-118">Enumeración CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="eb5a7-118">CorDebugCodeInvokePurpose Enumeration</span></span>](cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="eb5a7-119">Explica los motivos por los que una función exportada llama a código administrado.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-119">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="eb5a7-120">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="eb5a7-120">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="eb5a7-121">Proporciona opciones de depuración adicionales que se pueden usar en una llamada al método [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-121">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="eb5a7-122">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="eb5a7-122">CorDebugDebugEventKind Enumeration</span></span>](cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="eb5a7-123">Indica el tipo de evento cuya información se descodifica mediante el método [DecodeEvent](icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-123">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="eb5a7-124">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="eb5a7-124">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="eb5a7-125">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-125">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="eb5a7-126">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="eb5a7-126">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="eb5a7-127">Indica el tipo de devolución de llamada que se realiza desde un evento [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-127">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="eb5a7-128">CorDebugExceptionFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-128">CorDebugExceptionFlags Enumeration</span></span>](cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="eb5a7-129">Proporciona información adicional sobre una excepción.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-129">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="eb5a7-130">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="eb5a7-130">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="eb5a7-131">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-131">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="eb5a7-132">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-132">CorDebugGCType Enumeration</span></span>](cordebuggctype-enumeration.md)  
 <span data-ttu-id="eb5a7-133">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-133">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="eb5a7-134">CorDebugGenerationTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-134">CorDebugGenerationTypes Enumeration</span></span>](cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="eb5a7-135">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-135">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="eb5a7-136">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="eb5a7-136">CorDebugHandleType</span></span>  
 <span data-ttu-id="eb5a7-137">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-137">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="eb5a7-138">CorDebugIlToNativeMappingTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-138">CorDebugIlToNativeMappingTypes Enumeration</span></span>](cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="eb5a7-139">Indica si un intervalo de instrucciones nativas determinado se corresponde con una región de código especial.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-139">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="eb5a7-140">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="eb5a7-140">CorDebugIntercept</span></span>  
 <span data-ttu-id="eb5a7-141">Indica los tipos de código que se pueden ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-141">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="eb5a7-142">CorDebugInterfaceVersion (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-142">CorDebugInterfaceVersion Enumeration</span></span>](cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="eb5a7-143">Especifica una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-143">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="eb5a7-144">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="eb5a7-144">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="eb5a7-145">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-145">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="eb5a7-146">CorDebugJITCompilerFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-146">CorDebugJITCompilerFlags Enumeration</span></span>](cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="eb5a7-147">Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-147">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="eb5a7-148">CorDebugJITCompilerFlagsDeprecated (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-148">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="eb5a7-149">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-149">Obsolete.</span></span> <span data-ttu-id="eb5a7-150">`CORDEBUG_JIT_DEFAULT`En su lugar, use el miembro de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-150">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="eb5a7-151">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="eb5a7-151">CorDebugMappingResult</span></span>  
 <span data-ttu-id="eb5a7-152">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="eb5a7-152">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="eb5a7-153">CorDebugMDAFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-153">CorDebugMDAFlags Enumeration</span></span>](cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="eb5a7-154">Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="eb5a7-154">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="eb5a7-155">CorDebugNGenPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-155">CorDebugNGenPolicy Enumeration</span></span>](cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="eb5a7-156">Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-156">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="eb5a7-157">CorDebugPlatform (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-157">CorDebugPlatform Enumeration</span></span>](cordebugplatform-enumeration.md)  
 <span data-ttu-id="eb5a7-158">Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb5a7-158">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="eb5a7-159">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="eb5a7-159">CorDebugRecordFormat Enumeration</span></span>](cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="eb5a7-160">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-160">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="eb5a7-161">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="eb5a7-161">CorDebugRegister</span></span>  
 <span data-ttu-id="eb5a7-162">Especifica los registros asociados con una arquitectura de procesador determinada.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-162">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="eb5a7-163">CorDebugSetContextFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-163">CorDebugSetContextFlag Enumeration</span></span>](cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="eb5a7-164">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-164">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="eb5a7-165">Enumeración CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="eb5a7-165">CorDebugStateChange Enumeration</span></span>](cordebugstatechange-enumeration.md)  
 <span data-ttu-id="eb5a7-166">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-166">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="eb5a7-167">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="eb5a7-167">CorDebugStepReason</span></span>  
 <span data-ttu-id="eb5a7-168">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-168">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="eb5a7-169">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="eb5a7-169">CorDebugThreadState</span></span>  
 <span data-ttu-id="eb5a7-170">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-170">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="eb5a7-171">\>Cordebugunmappedstop (</span><span class="sxs-lookup"><span data-stu-id="eb5a7-171">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="eb5a7-172">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-172">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="eb5a7-173">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="eb5a7-173">CorDebugUserState</span></span>  
 <span data-ttu-id="eb5a7-174">Indica el estado de uso de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-174">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="eb5a7-175">CorGCReferenceType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-175">CorGCReferenceType Enumeration</span></span>](corgcreferencetype-enumeration.md)  
 <span data-ttu-id="eb5a7-176">Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-176">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="eb5a7-177">ILCodeKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-177">ILCodeKind Enumeration</span></span>](ilcodekind-enumeration.md)  
 <span data-ttu-id="eb5a7-178">Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-178">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="eb5a7-179">LoggingLevelEnum (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-179">LoggingLevelEnum Enumeration</span></span>](logginglevelenum-enumeration.md)  
 <span data-ttu-id="eb5a7-180">Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-180">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="eb5a7-181">LogSwitchCallReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-181">LogSwitchCallReason Enumeration</span></span>](logswitchcallreason-enumeration.md)  
 <span data-ttu-id="eb5a7-182">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-182">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="eb5a7-183">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="eb5a7-183">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)  
 <span data-ttu-id="eb5a7-184">Indica el tipo de ubicación nativa de una variable.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-184">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="eb5a7-185">WriteableMetadataUpdateMode (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eb5a7-185">WriteableMetadataUpdateMode Enumeration</span></span>](writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="eb5a7-186">Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-186">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>

 <span data-ttu-id="eb5a7-187">[Enumeración ClrDataSourceType](clrdatasourcetype-enumeration.md) Proporciona valores utilizados por la estructura de CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="eb5a7-187">[ClrDataSourceType Enumeration](clrdatasourcetype-enumeration.md) Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="eb5a7-188">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="eb5a7-188">Related Sections</span></span>  

 [<span data-ttu-id="eb5a7-189">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="eb5a7-189">Debugging Coclasses</span></span>](debugging-coclasses.md)  
  
 [<span data-ttu-id="eb5a7-190">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="eb5a7-190">Debugging Interfaces</span></span>](debugging-interfaces.md)  
  
 [<span data-ttu-id="eb5a7-191">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="eb5a7-191">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)  
  
 [<span data-ttu-id="eb5a7-192">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="eb5a7-192">Debugging Structures</span></span>](debugging-structures.md)
