---
title: Eventos en tiempo de ejecución de excepción
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica de las excepciones y el control de excepciones.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594723"
---
# <a name="net-runtime-exception-events"></a><span data-ttu-id="faacf-103">Eventos de excepción en tiempo de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="faacf-103">.NET runtime exception events</span></span>

<span data-ttu-id="faacf-104">Estos eventos en tiempo de ejecución capturan información sobre las excepciones que se producen.</span><span class="sxs-lookup"><span data-stu-id="faacf-104">These runtime events capture information about exceptions that are thrown.</span></span> <span data-ttu-id="faacf-105">Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="faacf-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="exceptionthrown_v1-event"></a><span data-ttu-id="faacf-106">Evento ExceptionThrown_V1</span><span class="sxs-lookup"><span data-stu-id="faacf-106">ExceptionThrown_V1 event</span></span>

|<span data-ttu-id="faacf-107">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-107">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-109">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-109">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-110">Error (1)</span><span class="sxs-lookup"><span data-stu-id="faacf-110">Error (1)</span></span>|

 <span data-ttu-id="faacf-111">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-111">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-112">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-112">Event</span></span>|<span data-ttu-id="faacf-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-113">Event ID</span></span>|<span data-ttu-id="faacf-114">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|<span data-ttu-id="faacf-115">80</span><span class="sxs-lookup"><span data-stu-id="faacf-115">80</span></span>|<span data-ttu-id="faacf-116">Se genera una excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="faacf-116">A managed exception is thrown.</span></span>|

|<span data-ttu-id="faacf-117">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="faacf-117">Field name</span></span>|<span data-ttu-id="faacf-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="faacf-118">Data type</span></span>|<span data-ttu-id="faacf-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="faacf-119">Description</span></span>|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|<span data-ttu-id="faacf-120">Tipo de la excepción; por ejemplo, `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="faacf-120">Type of the exception; for example, `System.NullReferenceException`.</span></span>|
|`ExceptionMessage`|`win:UnicodeString`|<span data-ttu-id="faacf-121">Mensaje actual de la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-121">Actual exception message.</span></span>|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="faacf-122">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-122">Instruction pointer where exception occurred.</span></span>|
|`ExceptionHR`|`win:UInt32`|<span data-ttu-id="faacf-123">Excepción [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="faacf-123">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|
|`ExceptionFlags`|`win:UInt16`|<span data-ttu-id="faacf-124">`0x01`: HasInnerException.</span><span class="sxs-lookup"><span data-stu-id="faacf-124">`0x01`: HasInnerException.</span></span><br /><br /> <span data-ttu-id="faacf-125">`0x02`: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="faacf-125">`0x02`: IsNestedException.</span></span><br /><br /> <span data-ttu-id="faacf-126">`0x04`: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="faacf-126">`0x04`: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="faacf-127">`0x08`: IsCorruptedStateException (indica que el estado del proceso está dañado; consulte [control de excepciones de estado dañadas](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="faacf-127">`0x08`: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="faacf-128">`0x10`: IsCLSCompliant (una excepción que se deriva de <xref:System.Exception> es conforme a CLS; en caso contrario, no es conforme a CLS).</span><span class="sxs-lookup"><span data-stu-id="faacf-128">`0x10`: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="faacf-129">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="faacf-129">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstart-event"></a><span data-ttu-id="faacf-130">Evento ExceptionCatchStart</span><span class="sxs-lookup"><span data-stu-id="faacf-130">ExceptionCatchStart event</span></span>

<span data-ttu-id="faacf-131">Este evento se genera cuando comienza un controlador Catch administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-131">This event is emitted when a managed exception catch handler begins.</span></span>

|<span data-ttu-id="faacf-132">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-132">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-133">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-133">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-134">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-134">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-135">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-135">Informational (4)</span></span>|

 <span data-ttu-id="faacf-136">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-136">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-137">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-137">Event</span></span>|<span data-ttu-id="faacf-138">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-138">Event ID</span></span>|<span data-ttu-id="faacf-139">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-139">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|<span data-ttu-id="faacf-140">250</span><span class="sxs-lookup"><span data-stu-id="faacf-140">250</span></span>|<span data-ttu-id="faacf-141">El tiempo de ejecución controla una excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="faacf-141">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="faacf-142">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="faacf-142">Field name</span></span>|<span data-ttu-id="faacf-143">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="faacf-143">Data type</span></span>|<span data-ttu-id="faacf-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="faacf-144">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="faacf-145">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-145">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="faacf-146">Puntero al descriptor de método en el método en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-146">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="faacf-147">Nombre del método en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-147">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="faacf-148">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="faacf-148">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptioncatchstop-event"></a><span data-ttu-id="faacf-149">Evento ExceptionCatchStop</span><span class="sxs-lookup"><span data-stu-id="faacf-149">ExceptionCatchStop event</span></span>

<span data-ttu-id="faacf-150">Este evento se genera cuando finaliza un controlador Catch administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-150">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="faacf-151">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-151">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-152">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-152">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-153">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-153">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-154">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-154">Informational (4)</span></span>|

 <span data-ttu-id="faacf-155">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-155">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-156">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-156">Event</span></span>|<span data-ttu-id="faacf-157">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-157">Event ID</span></span>|<span data-ttu-id="faacf-158">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-158">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|<span data-ttu-id="faacf-159">251</span><span class="sxs-lookup"><span data-stu-id="faacf-159">251</span></span>|<span data-ttu-id="faacf-160">Se realiza un controlador catch de excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="faacf-160">A managed exception catch handler is done.</span></span>|

## <a name="exceptionfinallystart-event"></a><span data-ttu-id="faacf-161">Evento ExceptionFinallyStart</span><span class="sxs-lookup"><span data-stu-id="faacf-161">ExceptionFinallyStart event</span></span>

<span data-ttu-id="faacf-162">Este evento se genera cuando comienza un controlador final de excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="faacf-162">This event is emitted when a managed exception finally handler begins.</span></span>

|<span data-ttu-id="faacf-163">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-163">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-164">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-164">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-165">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-165">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-166">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-166">Informational (4)</span></span>|

 <span data-ttu-id="faacf-167">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-167">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-168">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-168">Event</span></span>|<span data-ttu-id="faacf-169">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-169">Event ID</span></span>|<span data-ttu-id="faacf-170">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-170">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|<span data-ttu-id="faacf-171">252</span><span class="sxs-lookup"><span data-stu-id="faacf-171">252</span></span>|<span data-ttu-id="faacf-172">El tiempo de ejecución controla una excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="faacf-172">A managed exception is handled by the runtime.</span></span>|

|<span data-ttu-id="faacf-173">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="faacf-173">Field name</span></span>|<span data-ttu-id="faacf-174">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="faacf-174">Data type</span></span>|<span data-ttu-id="faacf-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="faacf-175">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="faacf-176">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-176">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="faacf-177">Puntero al descriptor de método en el método en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-177">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="faacf-178">Nombre del método en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-178">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="faacf-179">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="faacf-179">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="exceptionfinallystop-event"></a><span data-ttu-id="faacf-180">Evento ExceptionFinallyStop</span><span class="sxs-lookup"><span data-stu-id="faacf-180">ExceptionFinallyStop event</span></span>

<span data-ttu-id="faacf-181">Este evento se genera cuando finaliza un controlador Catch administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-181">This event is emitted when a managed exception catch handler ends.</span></span>

|<span data-ttu-id="faacf-182">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-182">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-183">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-183">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-184">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-184">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-185">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-185">Informational (4)</span></span>|

 <span data-ttu-id="faacf-186">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-186">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-187">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-187">Event</span></span>|<span data-ttu-id="faacf-188">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-188">Event ID</span></span>|<span data-ttu-id="faacf-189">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-189">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|<span data-ttu-id="faacf-190">253</span><span class="sxs-lookup"><span data-stu-id="faacf-190">253</span></span>|<span data-ttu-id="faacf-191">Se realiza un controlador Finally de excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="faacf-191">A managed exception finally handler is done.</span></span>|

## <a name="exceptionfilterstart-event"></a><span data-ttu-id="faacf-192">Evento ExceptionFilterStart</span><span class="sxs-lookup"><span data-stu-id="faacf-192">ExceptionFilterStart event</span></span>

<span data-ttu-id="faacf-193">Este evento se genera cuando comienza un filtrado de excepciones administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-193">This event is emitted when a managed exception filtering begins.</span></span>

|<span data-ttu-id="faacf-194">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-194">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-195">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-195">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-196">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-196">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-197">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-197">Informational (4)</span></span>|

 <span data-ttu-id="faacf-198">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-198">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-199">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-199">Event</span></span>|<span data-ttu-id="faacf-200">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-200">Event ID</span></span>|<span data-ttu-id="faacf-201">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-201">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|<span data-ttu-id="faacf-202">254</span><span class="sxs-lookup"><span data-stu-id="faacf-202">254</span></span>|<span data-ttu-id="faacf-203">Comienza un filtrado de excepciones administradas.</span><span class="sxs-lookup"><span data-stu-id="faacf-203">A managed exception filtering begins.</span></span>|

|<span data-ttu-id="faacf-204">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="faacf-204">Field name</span></span>|<span data-ttu-id="faacf-205">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="faacf-205">Data type</span></span>|<span data-ttu-id="faacf-206">Descripción</span><span class="sxs-lookup"><span data-stu-id="faacf-206">Description</span></span>|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|<span data-ttu-id="faacf-207">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-207">Instruction pointer where exception occurred.</span></span>|
|`MethodID`|`win:Pointer`|<span data-ttu-id="faacf-208">Puntero al descriptor de método en el método en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-208">Pointer to the method descriptor on the method where exception occurred.</span></span>|
|`MethodName`|`win:UnicodeString`|<span data-ttu-id="faacf-209">Nombre del método en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="faacf-209">Name of the method where exception occurred.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="faacf-210">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="faacf-210">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="exceptionfilterstop-event"></a><span data-ttu-id="faacf-211">Evento ExceptionFilterStop</span><span class="sxs-lookup"><span data-stu-id="faacf-211">ExceptionFilterStop event</span></span>

<span data-ttu-id="faacf-212">Este evento se genera cuando finaliza un filtrado de excepciones administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-212">This event is emitted when a managed exception filtering ends.</span></span>

|<span data-ttu-id="faacf-213">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-213">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-214">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-214">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-215">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-215">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-216">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-216">Informational (4)</span></span>|

 <span data-ttu-id="faacf-217">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-217">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-218">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-218">Event</span></span>|<span data-ttu-id="faacf-219">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-219">Event ID</span></span>|<span data-ttu-id="faacf-220">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-220">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|<span data-ttu-id="faacf-221">255</span><span class="sxs-lookup"><span data-stu-id="faacf-221">255</span></span>|<span data-ttu-id="faacf-222">Finaliza un filtrado de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-222">A managed exception filtering ends.</span></span>|

## <a name="exceptionthrownstop-event"></a><span data-ttu-id="faacf-223">Evento ExceptionThrownStop</span><span class="sxs-lookup"><span data-stu-id="faacf-223">ExceptionThrownStop event</span></span>

<span data-ttu-id="faacf-224">Este evento se genera cuando el motor en tiempo de ejecución realiza el control de una excepción administrada que se produjo.</span><span class="sxs-lookup"><span data-stu-id="faacf-224">This event is emitted when the runtime is done handling a managed exception that was thrown.</span></span>

|<span data-ttu-id="faacf-225">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="faacf-225">Keyword for raising the event</span></span>|<span data-ttu-id="faacf-226">Nivel</span><span class="sxs-lookup"><span data-stu-id="faacf-226">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="faacf-227">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="faacf-227">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="faacf-228">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="faacf-228">Informational (4)</span></span>|
  
 <span data-ttu-id="faacf-229">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="faacf-229">The following table shows event information.</span></span>

|<span data-ttu-id="faacf-230">Evento</span><span class="sxs-lookup"><span data-stu-id="faacf-230">Event</span></span>|<span data-ttu-id="faacf-231">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="faacf-231">Event ID</span></span>|<span data-ttu-id="faacf-232">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="faacf-232">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|<span data-ttu-id="faacf-233">256</span><span class="sxs-lookup"><span data-stu-id="faacf-233">256</span></span>|<span data-ttu-id="faacf-234">Finaliza un filtrado de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="faacf-234">A managed exception filtering ends.</span></span>|
