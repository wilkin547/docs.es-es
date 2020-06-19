---
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
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990512"
---
# <a name="logging-class"></a><span data-ttu-id="0a15e-102">Clase de registro</span><span class="sxs-lookup"><span data-stu-id="0a15e-102">Logging class</span></span>

<span data-ttu-id="0a15e-103">Proporciona la funcionalidad de registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-103">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="0a15e-104">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0a15e-104">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0a15e-105">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0a15e-105">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="0a15e-106">Associate (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-106">Associate method</span></span>

<span data-ttu-id="0a15e-107">Registra información que dos objetos están asociados entre sí.</span><span class="sxs-lookup"><span data-stu-id="0a15e-107">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-108">Parameters</span></span>

- <span data-ttu-id="0a15e-109">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-109">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-110">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-110">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-111">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-111">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-112">Objeto con el que se va a asociar `objB` .</span><span class="sxs-lookup"><span data-stu-id="0a15e-112">The object to associate with `objB`.</span></span>

- <span data-ttu-id="0a15e-113">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-113">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-114">Objeto con el que se va a asociar `objA` .</span><span class="sxs-lookup"><span data-stu-id="0a15e-114">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="0a15e-115">Enter (TraceSource, Object, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-115">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="0a15e-116">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-116">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-117">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-117">Parameters</span></span>

- <span data-ttu-id="0a15e-118">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-118">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-119">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-119">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-120">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-120">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-121">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-121">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-122">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-122">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-123">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0a15e-123">The method that is being entered.</span></span>

- <span data-ttu-id="0a15e-124">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-124">`param` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-125">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-125">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="0a15e-126">Enter (TraceSource, Object, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-126">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="0a15e-127">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-127">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-128">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-128">Parameters</span></span>

- <span data-ttu-id="0a15e-129">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-129">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-130">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-130">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-131">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-131">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-132">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-132">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-133">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-133">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-134">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0a15e-134">The method that is being entered.</span></span>

- <span data-ttu-id="0a15e-135">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-135">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-136">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-136">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="0a15e-137">Enter (TraceSource, String, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-137">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="0a15e-138">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-138">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-139">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-139">Parameters</span></span>

- <span data-ttu-id="0a15e-140">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-140">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-141">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-141">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-142">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-142">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-143">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-143">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-144">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-144">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-145">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0a15e-145">The method that is being entered.</span></span>

- <span data-ttu-id="0a15e-146">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-146">`param` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-147">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-147">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="0a15e-148">Enter (TraceSource, String, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-148">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="0a15e-149">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-149">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-150">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-150">Parameters</span></span>

- <span data-ttu-id="0a15e-151">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-151">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-152">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-152">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-153">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-153">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-154">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-154">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-155">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-155">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-156">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0a15e-156">The method that is being entered.</span></span>

- <span data-ttu-id="0a15e-157">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-157">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-158">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-158">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="0a15e-159">Enter (TraceSource, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-159">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="0a15e-160">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-160">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-161">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-161">Parameters</span></span>

- <span data-ttu-id="0a15e-162">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-162">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-163">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-163">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-164">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-164">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-165">Método que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0a15e-165">The method that is being entered.</span></span>

- <span data-ttu-id="0a15e-166">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-166">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-167">Los parámetros que se pasaron al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-167">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="0a15e-168">Enter (TraceSource, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-168">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="0a15e-169">Registra la entrada a un método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-169">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-170">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-170">Parameters</span></span>

- <span data-ttu-id="0a15e-171">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-171">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-172">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-172">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-173">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-173">`msg` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-174">Mensaje de entrada que se va a registrar en el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-174">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="0a15e-175">Exception (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-175">Exception method</span></span>

<span data-ttu-id="0a15e-176">Registra una excepción y restaura la sangría.</span><span class="sxs-lookup"><span data-stu-id="0a15e-176">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-177">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-177">Parameters</span></span>

- <span data-ttu-id="0a15e-178">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-178">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-179">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-179">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-180">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-180">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-181">Objeto en el que se llamó al método que inició una excepción.</span><span class="sxs-lookup"><span data-stu-id="0a15e-181">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="0a15e-182">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-182">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-183">El método que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="0a15e-183">The method that threw the exception.</span></span>

- <span data-ttu-id="0a15e-184">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="0a15e-184">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="0a15e-185">La excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="0a15e-185">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="0a15e-186">Exit (TraceSource, Object, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-186">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="0a15e-187">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="0a15e-187">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-188">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-188">Parameters</span></span>

- <span data-ttu-id="0a15e-189">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-189">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-190">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-190">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-191">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-191">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-192">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-192">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-193">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-193">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-194">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="0a15e-194">The method that is being exited.</span></span>

- <span data-ttu-id="0a15e-195">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-195">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-196">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-196">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="0a15e-197">Exit (TraceSource, String, String, Object) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-197">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="0a15e-198">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="0a15e-198">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-199">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-199">Parameters</span></span>

- <span data-ttu-id="0a15e-200">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-200">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-201">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-201">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-202">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-202">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-203">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-203">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-204">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-204">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-205">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="0a15e-205">The method that is being exited.</span></span>

- <span data-ttu-id="0a15e-206">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-206">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-207">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-207">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="0a15e-208">Exit (TraceSource, Object, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-208">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="0a15e-209">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="0a15e-209">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-210">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-210">Parameters</span></span>

- <span data-ttu-id="0a15e-211">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-211">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-212">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-212">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-213">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="0a15e-213">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="0a15e-214">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-214">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-215">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-215">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-216">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="0a15e-216">The method that is being exited.</span></span>

- <span data-ttu-id="0a15e-217">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-217">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-218">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-218">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="0a15e-219">Exit (TraceSource, cadena, cadena, cadena) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-219">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="0a15e-220">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="0a15e-220">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-221">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-221">Parameters</span></span>

- <span data-ttu-id="0a15e-222">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-222">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-223">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-223">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-224">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-224">`obj` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-225">Objeto en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-225">The object that the method was called on.</span></span>

- <span data-ttu-id="0a15e-226">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-226">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-227">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="0a15e-227">The method that is being exited.</span></span>

- <span data-ttu-id="0a15e-228">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-228">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-229">Valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="0a15e-229">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="0a15e-230">Exit (TraceSource, String, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-230">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="0a15e-231">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="0a15e-231">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-232">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-232">Parameters</span></span>

- <span data-ttu-id="0a15e-233">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-233">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-234">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-234">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-235">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-235">`method` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-236">El método que se está saliendo.</span><span class="sxs-lookup"><span data-stu-id="0a15e-236">The method that is being exited.</span></span>

- <span data-ttu-id="0a15e-237">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-237">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-238">Los parámetros que se pasaron al método que se está cerrando.</span><span class="sxs-lookup"><span data-stu-id="0a15e-238">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="0a15e-239">Exit (TraceSource, String) (método)</span><span class="sxs-lookup"><span data-stu-id="0a15e-239">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="0a15e-240">Los registros salen de una función.</span><span class="sxs-lookup"><span data-stu-id="0a15e-240">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="0a15e-241">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a15e-241">Parameters</span></span>

- <span data-ttu-id="0a15e-242">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="0a15e-242">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="0a15e-243">Origen de seguimiento en el que se va a registrar el evento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-243">The trace source to log the event to.</span></span>

- <span data-ttu-id="0a15e-244">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a15e-244">`msg` <xref:System.String></span></span>

  <span data-ttu-id="0a15e-245">Mensaje de salida que se va a registrar en el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a15e-245">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="0a15e-246">Propiedad http</span><span class="sxs-lookup"><span data-stu-id="0a15e-246">Http property</span></span>

<span data-ttu-id="0a15e-247">Obtiene el origen de seguimiento para "System .net. http".</span><span class="sxs-lookup"><span data-stu-id="0a15e-247">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="0a15e-248">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="0a15e-248">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="0a15e-249">El origen de seguimiento para "System .net. http" o `null` si el registro no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0a15e-249">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="0a15e-250">On (propiedad)</span><span class="sxs-lookup"><span data-stu-id="0a15e-250">On property</span></span>

<span data-ttu-id="0a15e-251">Obtiene un valor que indica si el registro está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0a15e-251">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="0a15e-252">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="0a15e-252">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="0a15e-253">`true` si el registro está habilitado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0a15e-253">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a15e-254">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a15e-254">Requirements</span></span>

<span data-ttu-id="0a15e-255">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0a15e-255">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0a15e-256">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="0a15e-256">**Assembly:** System (in System.dll)</span></span>
