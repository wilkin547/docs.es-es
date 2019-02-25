---
title: Serialización de tipos (.NET)
description: Obtenga información sobre cómo .NET serializa los tipos en una representación nativa.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 2c62581d34e77f208b7764f955dfa37613615ee4
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411476"
---
# <a name="type-marshalling"></a><span data-ttu-id="44252-103">Serializar tipos</span><span class="sxs-lookup"><span data-stu-id="44252-103">Type marshalling</span></span>

<span data-ttu-id="44252-104">La **serialización** es el proceso de transformación de tipos cuando tienen que cruzar el límite entre administrado y nativo.</span><span class="sxs-lookup"><span data-stu-id="44252-104">**Marshalling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="44252-105">La serialización es necesaria porque los tipos del código administrado y del código no administrado son diferentes.</span><span class="sxs-lookup"><span data-stu-id="44252-105">Marshalling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="44252-106">En el código administrado, por ejemplo, tiene `String`, mientras que en el entorno no administrado, las cadenas pueden ser Unicode ("anchas"), no Unicode, terminadas en un valor nulo, ASCII, etc. De forma predeterminada, el subsistema de P/Invoke intenta hacer "lo correcto" según el comportamiento predeterminado, tal y como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="44252-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="44252-107">Pero en aquellas situaciones en las que necesita un control adicional, puede emplear el atributo [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) para especificar qué tipo se espera en el lado no administrado.</span><span class="sxs-lookup"><span data-stu-id="44252-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="44252-108">Por ejemplo, si queremos que la cadena se envíe como una cadena ANSI terminada en un valor nulo, podemos hacerlo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="44252-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshalling-common-types"></a><span data-ttu-id="44252-109">Reglas predeterminadas para serializar tipos comunes</span><span class="sxs-lookup"><span data-stu-id="44252-109">Default rules for marshalling common types</span></span>

<span data-ttu-id="44252-110">Por lo general, el entorno de ejecución intenta hacer "lo correcto" al serializar para requerir la menor cantidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="44252-110">Generally, the runtime tries to do the "right thing" when marshalling to require the least amount of work from you.</span></span> <span data-ttu-id="44252-111">En las tablas siguientes se describen cómo se serializa cada tipo de forma predeterminada cuando se utiliza en un parámetro o campo.</span><span class="sxs-lookup"><span data-stu-id="44252-111">The following tables describe how each type is marshalled by default when used in a parameter or field.</span></span> <span data-ttu-id="44252-112">El entero de ancho fijo C99/C++11 y los tipos de caracteres se usan para garantizar que la tabla siguiente es correcta para todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="44252-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="44252-113">Puede usar cualquier tipo nativo que tenga la misma alineación y los requisitos de tamaño que estos tipos.</span><span class="sxs-lookup"><span data-stu-id="44252-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="44252-114">Esta primera tabla describe las asignaciones para distintos tipos para los que la serialización es el misma que en la serialización de campos y de P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="44252-114">This first table describes the mappings for various types for whom the marshalling is the same for both P/Invoke and field marshalling.</span></span>

| <span data-ttu-id="44252-115">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="44252-115">.NET Type</span></span> | <span data-ttu-id="44252-116">Tipo nativo</span><span class="sxs-lookup"><span data-stu-id="44252-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="44252-117">`char` o `char16_t` según el elemento `CharSet` de la estructura o P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="44252-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="44252-118">Consulte la [documentación de juego de caracteres](/.charset.md).</span><span class="sxs-lookup"><span data-stu-id="44252-118">See the [charset documentation](/.charset.md).</span></span> |
| `string`  | <span data-ttu-id="44252-119">`char*` o `char16_t*` según el elemento `CharSet` de la estructura o P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="44252-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="44252-120">Consulte la [documentación de juego de caracteres](/.charset.md).</span><span class="sxs-lookup"><span data-stu-id="44252-120">See the [charset documentation](/.charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="44252-121">Tipos de puntero de .NET (por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="44252-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="44252-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="44252-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="44252-123">Tipo derivado de `System.Runtime.InteropServices.SafeHandle`</span><span class="sxs-lookup"><span data-stu-id="44252-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="44252-124">Tipo derivado de `System.Runtime.InteropServices.CriticalHandle`</span><span class="sxs-lookup"><span data-stu-id="44252-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="44252-125">Tipo `BOOL` de Win32</span><span class="sxs-lookup"><span data-stu-id="44252-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="44252-126">Estructura `DECIMAL` de COM</span><span class="sxs-lookup"><span data-stu-id="44252-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="44252-127">Delegado de .NET</span><span class="sxs-lookup"><span data-stu-id="44252-127">.NET Delegate</span></span> | <span data-ttu-id="44252-128">Puntero de función nativa</span><span class="sxs-lookup"><span data-stu-id="44252-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="44252-129">Tipo `DATE` de Win32</span><span class="sxs-lookup"><span data-stu-id="44252-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="44252-130">Tipo `GUID` de Win32</span><span class="sxs-lookup"><span data-stu-id="44252-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="44252-131">Algunas categorías de serialización tienen distintos valores predeterminados si está serializando un parámetro o una estructura.</span><span class="sxs-lookup"><span data-stu-id="44252-131">A few categories of marshalling have different defaults if you're marshalling as a parameter or structure.</span></span>

| <span data-ttu-id="44252-132">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="44252-132">.NET Type</span></span> | <span data-ttu-id="44252-133">Tipo nativo (parámetro)</span><span class="sxs-lookup"><span data-stu-id="44252-133">Native Type (Parameter)</span></span> | <span data-ttu-id="44252-134">Tipo nativo (campo)</span><span class="sxs-lookup"><span data-stu-id="44252-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="44252-135">Matriz de .NET</span><span class="sxs-lookup"><span data-stu-id="44252-135">.NET array</span></span> | <span data-ttu-id="44252-136">Un puntero al inicio de una matriz de representaciones nativas de los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="44252-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="44252-137">No se permite sin un atributo `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="44252-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="44252-138">Una clase con `LayoutKind` de `Sequential` o `Explicit`</span><span class="sxs-lookup"><span data-stu-id="44252-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="44252-139">Un puntero a la representación nativa de la clase</span><span class="sxs-lookup"><span data-stu-id="44252-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="44252-140">Representación nativa de la clase</span><span class="sxs-lookup"><span data-stu-id="44252-140">The native representation of the class</span></span> |

<span data-ttu-id="44252-141">En la tabla siguiente se incluyen las reglas de serialización predeterminadas que son solo de Windows.</span><span class="sxs-lookup"><span data-stu-id="44252-141">The following table includes the default marshalling rules that are Windows-only.</span></span> <span data-ttu-id="44252-142">En las plataformas que no sean Windows, no puede serializar estos tipos.</span><span class="sxs-lookup"><span data-stu-id="44252-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="44252-143">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="44252-143">.NET Type</span></span> | <span data-ttu-id="44252-144">Tipo nativo (parámetro)</span><span class="sxs-lookup"><span data-stu-id="44252-144">Native Type (Parameter)</span></span> | <span data-ttu-id="44252-145">Tipo nativo (campo)</span><span class="sxs-lookup"><span data-stu-id="44252-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="44252-146">Interfaz COM</span><span class="sxs-lookup"><span data-stu-id="44252-146">COM interface</span></span> | <span data-ttu-id="44252-147">No se permite sin un atributo `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="44252-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="44252-148">No permitido</span><span class="sxs-lookup"><span data-stu-id="44252-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="44252-149">No permitido</span><span class="sxs-lookup"><span data-stu-id="44252-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="44252-150">No permitido</span><span class="sxs-lookup"><span data-stu-id="44252-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="44252-151">`int64_t` que representa el número de tics desde la medianoche del 1 de enero de 1601</span><span class="sxs-lookup"><span data-stu-id="44252-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="44252-152">`int64_t` que representa el número de tics desde la medianoche del 1 de enero de 1601</span><span class="sxs-lookup"><span data-stu-id="44252-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="44252-153">Algunos tipos solo pueden serializarse como parámetros y no como campos.</span><span class="sxs-lookup"><span data-stu-id="44252-153">Some types can only be marshalled as parameters and not as fields.</span></span> <span data-ttu-id="44252-154">Estas herramientas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="44252-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="44252-155">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="44252-155">.NET Type</span></span> | <span data-ttu-id="44252-156">Tipo nativo (solo parámetros)</span><span class="sxs-lookup"><span data-stu-id="44252-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="44252-157">`char*` o `char16_t*` según el elemento `CharSet` de P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="44252-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="44252-158">Consulte la [documentación de juego de caracteres](/.charset.md).</span><span class="sxs-lookup"><span data-stu-id="44252-158">See the [charset documentation](/.charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="44252-159">`va_list` (solo en Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="44252-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="44252-160">Si estos valores predeterminados no hacen exactamente lo que desea, puede personalizar cómo serializar los parámetros.</span><span class="sxs-lookup"><span data-stu-id="44252-160">If these defaults don't do exactly what you want, you can customize how parameters are marshalled.</span></span> <span data-ttu-id="44252-161">El artículo sobre [serialización de parámetros](customize-parameter-marshalling.md) explica cómo personalizar la forma en que se serializan los diferentes tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="44252-161">The [parameter marshalling](customize-parameter-marshalling.md) article walks you through how to customize how different parameter types are marshalled.</span></span>

## <a name="marshalling-classes-and-structs"></a><span data-ttu-id="44252-162">Serializar clases y estructuras</span><span class="sxs-lookup"><span data-stu-id="44252-162">Marshalling classes and structs</span></span>

<span data-ttu-id="44252-163">Otro aspecto de la serialización de tipos es cómo pasar una estructura a un método no administrado.</span><span class="sxs-lookup"><span data-stu-id="44252-163">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="44252-164">Por ejemplo, algunos métodos no administrados requieren una estructura como parámetro.</span><span class="sxs-lookup"><span data-stu-id="44252-164">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="44252-165">En estos casos, debemos crear una clase o una estructura correspondiente en la parte administrada del entorno para usarla como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="44252-165">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="44252-166">Pero no basta con definir simplemente la clase. También es necesario indicarle al contador de referencias cómo asignar campos de la clase a la estructura no administrada.</span><span class="sxs-lookup"><span data-stu-id="44252-166">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="44252-167">Aquí el atributo `StructLayout` resulta útil.</span><span class="sxs-lookup"><span data-stu-id="44252-167">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="44252-168">En el ejemplo anterior se muestra un ejemplo simple de una llamada a la función `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="44252-168">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="44252-169">La parte interesante está en la línea 4.</span><span class="sxs-lookup"><span data-stu-id="44252-169">The interesting bit is on line 4.</span></span> <span data-ttu-id="44252-170">El atributo especifica que los campos de la clase se deben asignar secuencialmente a la estructura en el otro lado (el lado no administrado).</span><span class="sxs-lookup"><span data-stu-id="44252-170">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="44252-171">Esto significa que la denominación de los campos no es importante. Solo su orden es importante, ya que es necesario que coincida con la estructura no administrada, tal como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="44252-171">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="44252-172">A veces, la serialización predeterminada para la estructura no hace lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="44252-172">Sometimes the default marshalling for your structure doesn't do what you need.</span></span> <span data-ttu-id="44252-173">El artículo [Personalización de la serialización de estructuras](./customize-struct-marshalling.md) le enseña cómo personalizar para serializar una estructura.</span><span class="sxs-lookup"><span data-stu-id="44252-173">The [Customizing structure marshalling](./customize-struct-marshalling.md) article teaches you how to customize how your structure is marshaled.</span></span>
