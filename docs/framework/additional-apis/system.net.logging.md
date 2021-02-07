---
description: 'Más información sobre: clase de registro'
title: Clase de registro (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 1ae3079ab21502ee3f5bf71db57f0695da9a8571
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726213"
---
# <a name="logging-class"></a><span data-ttu-id="ab458-103">Clase Logging</span><span class="sxs-lookup"><span data-stu-id="ab458-103">Logging class</span></span>

<span data-ttu-id="ab458-104">Proporciona la funcionalidad de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ab458-104">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="ab458-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="ab458-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ab458-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="ab458-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="ab458-107">Associate (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-107">Associate method</span></span>

<span data-ttu-id="ab458-108">Registra información que dos objetos están asociados entre sí.</span><span class="sxs-lookup"><span data-stu-id="ab458-108">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="ab458-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-109">Parameters</span></span>

- <span data-ttu-id="ab458-110">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-110">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-111">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-111">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-112">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-112">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-113">Objeto con el que se va a asociar `objB` .</span><span class="sxs-lookup"><span data-stu-id="ab458-113">The object to associate with `objB`.</span></span>

- <span data-ttu-id="ab458-114">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-114">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-115">Objeto con el que se va a asociar `objA` .</span><span class="sxs-lookup"><span data-stu-id="ab458-115">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="ab458-116">Enter (TraceSource, Object, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-116">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="ab458-117">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="ab458-117">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="ab458-118">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-118">Parameters</span></span>

- <span data-ttu-id="ab458-119">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-119">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-120">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-120">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-121">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-121">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-122">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-122">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-123">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-123">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-124">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ab458-124">The method that is being entered.</span></span>

- <span data-ttu-id="ab458-125">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-125">`param` <xref:System.String></span></span>

  <span data-ttu-id="ab458-126">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-126">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="ab458-127">Enter (TraceSource, Object, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-127">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="ab458-128">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="ab458-128">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="ab458-129">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-129">Parameters</span></span>

- <span data-ttu-id="ab458-130">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-130">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-131">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-131">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-132">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-132">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-133">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-133">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-134">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-134">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-135">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ab458-135">The method that is being entered.</span></span>

- <span data-ttu-id="ab458-136">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-136">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-137">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-137">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="ab458-138">Enter (TraceSource, String, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-138">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="ab458-139">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="ab458-139">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="ab458-140">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-140">Parameters</span></span>

- <span data-ttu-id="ab458-141">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-141">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-142">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-142">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-143">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-143">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ab458-144">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-144">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-145">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-145">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-146">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ab458-146">The method that is being entered.</span></span>

- <span data-ttu-id="ab458-147">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-147">`param` <xref:System.String></span></span>

  <span data-ttu-id="ab458-148">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-148">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="ab458-149">Enter (TraceSource, String, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-149">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="ab458-150">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="ab458-150">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="ab458-151">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-151">Parameters</span></span>

- <span data-ttu-id="ab458-152">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-152">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-153">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-153">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-154">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-154">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ab458-155">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-155">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-156">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-156">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-157">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ab458-157">The method that is being entered.</span></span>

- <span data-ttu-id="ab458-158">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-158">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-159">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-159">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="ab458-160">Enter (TraceSource, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-160">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="ab458-161">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="ab458-161">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="ab458-162">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-162">Parameters</span></span>

- <span data-ttu-id="ab458-163">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-163">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-164">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-164">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-165">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-165">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-166">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ab458-166">The method that is being entered.</span></span>

- <span data-ttu-id="ab458-167">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-167">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="ab458-168">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-168">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="ab458-169">Enter (TraceSource, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-169">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="ab458-170">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="ab458-170">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="ab458-171">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-171">Parameters</span></span>

- <span data-ttu-id="ab458-172">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-172">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-173">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-173">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-174">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-174">`msg` <xref:System.String></span></span>

  <span data-ttu-id="ab458-175">Mensaje de entrada que se va a registrar en el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ab458-175">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="ab458-176">Exception (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-176">Exception method</span></span>

<span data-ttu-id="ab458-177">Registra una excepción y restaura la sangría.</span><span class="sxs-lookup"><span data-stu-id="ab458-177">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="ab458-178">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-178">Parameters</span></span>

- <span data-ttu-id="ab458-179">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-179">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-180">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-180">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-181">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-181">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-182">Objeto en el que se llamó al método que inició una excepción.</span><span class="sxs-lookup"><span data-stu-id="ab458-182">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="ab458-183">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-183">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-184">El método que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ab458-184">The method that threw the exception.</span></span>

- <span data-ttu-id="ab458-185">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="ab458-185">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="ab458-186">La excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="ab458-186">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="ab458-187">Exit (TraceSource, Object, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-187">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="ab458-188">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="ab458-188">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="ab458-189">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-189">Parameters</span></span>

- <span data-ttu-id="ab458-190">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-190">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-191">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-191">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-192">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-192">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-193">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-193">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-194">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-194">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-195">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="ab458-195">The method that is being exited.</span></span>

- <span data-ttu-id="ab458-196">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-196">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-197">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="ab458-197">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="ab458-198">Exit (TraceSource, String, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-198">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="ab458-199">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="ab458-199">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="ab458-200">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-200">Parameters</span></span>

- <span data-ttu-id="ab458-201">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-201">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-202">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-202">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-203">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-203">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ab458-204">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-204">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-205">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-205">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-206">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="ab458-206">The method that is being exited.</span></span>

- <span data-ttu-id="ab458-207">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-207">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-208">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="ab458-208">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="ab458-209">Exit (TraceSource, Object, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-209">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="ab458-210">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="ab458-210">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="ab458-211">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-211">Parameters</span></span>

- <span data-ttu-id="ab458-212">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-212">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-213">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-213">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-214">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="ab458-214">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="ab458-215">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-215">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-216">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-216">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-217">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="ab458-217">The method that is being exited.</span></span>

- <span data-ttu-id="ab458-218">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-218">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="ab458-219">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="ab458-219">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="ab458-220">Exit (TraceSource, cadena, cadena, cadena) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-220">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="ab458-221">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="ab458-221">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="ab458-222">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-222">Parameters</span></span>

- <span data-ttu-id="ab458-223">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-223">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-224">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-224">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-225">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-225">`obj` <xref:System.String></span></span>

  <span data-ttu-id="ab458-226">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="ab458-226">The object that the method was called on.</span></span>

- <span data-ttu-id="ab458-227">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-227">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-228">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="ab458-228">The method that is being exited.</span></span>

- <span data-ttu-id="ab458-229">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-229">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="ab458-230">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="ab458-230">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="ab458-231">Exit (TraceSource, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-231">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="ab458-232">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="ab458-232">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="ab458-233">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-233">Parameters</span></span>

- <span data-ttu-id="ab458-234">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-234">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-235">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-235">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-236">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-236">`method` <xref:System.String></span></span>

  <span data-ttu-id="ab458-237">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="ab458-237">The method that is being exited.</span></span>

- <span data-ttu-id="ab458-238">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-238">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="ab458-239">Los parámetros que se pasaron al método que se está cerrando.</span><span class="sxs-lookup"><span data-stu-id="ab458-239">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="ab458-240">Exit (TraceSource, String) (método)</span><span class="sxs-lookup"><span data-stu-id="ab458-240">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="ab458-241">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="ab458-241">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="ab458-242">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab458-242">Parameters</span></span>

- <span data-ttu-id="ab458-243">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ab458-243">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="ab458-244">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="ab458-244">The trace source to log the event to.</span></span>

- <span data-ttu-id="ab458-245">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="ab458-245">`msg` <xref:System.String></span></span>

  <span data-ttu-id="ab458-246">Mensaje de salida que se va a registrar en el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ab458-246">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="ab458-247">Propiedad http</span><span class="sxs-lookup"><span data-stu-id="ab458-247">Http property</span></span>

<span data-ttu-id="ab458-248">Obtiene el origen de seguimiento para "System .net. http".</span><span class="sxs-lookup"><span data-stu-id="ab458-248">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="ab458-249">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="ab458-249">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="ab458-250">El origen de seguimiento para "System .net. http" o `null` si el registro no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ab458-250">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="ab458-251">On (propiedad)</span><span class="sxs-lookup"><span data-stu-id="ab458-251">On property</span></span>

<span data-ttu-id="ab458-252">Obtiene un valor que indica si el registro está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ab458-252">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="ab458-253">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="ab458-253">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="ab458-254">`true` si el registro está habilitado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ab458-254">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab458-255">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab458-255">Requirements</span></span>

<span data-ttu-id="ab458-256">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ab458-256">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ab458-257">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="ab458-257">**Assembly:** System (in System.dll)</span></span>
