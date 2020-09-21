---
title: Tipos que pueden o que no pueden transferirse en bloque de bits
description: Aprenda sobre tipos que pueden o que no pueden transferirse en bloque de bits. Los tipos de datos que pueden representarse como tipos que pueden transferirse en bloque de bits se representan normalmente en la memoria administrada y no administrada y no necesitan un control especial.
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 8bbf9c72143033cec22b38cc26cbe8ceb44f790b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556276"
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="25e84-104">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="25e84-104">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="25e84-105">La mayoría de los tipos de datos tienen una representación común en la memoria administrada y no administrada, y no requieren un tratamiento especial por parte del serializador de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="25e84-105">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="25e84-106">Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión cuando se pasan entre código administrado y código no administrado.</span><span class="sxs-lookup"><span data-stu-id="25e84-106">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="25e84-107">Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos que pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="25e84-107">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="25e84-108">La invocación de plataforma no admite estructuras que no pueden transferirse en bloque de bits como tipos de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="25e84-108">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="25e84-109">Los siguientes tipos del espacio de nombres <xref:System> son tipos que pueden transferirse en bloque de bits:</span><span class="sxs-lookup"><span data-stu-id="25e84-109">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="25e84-110">Los siguientes tipos complejos también son tipos que pueden transferirse en bloque de bits:</span><span class="sxs-lookup"><span data-stu-id="25e84-110">The following complex types are also blittable types:</span></span>  
  
- <span data-ttu-id="25e84-111">Las matrices unidimensionales de tipos que pueden transferirse en bloque de bits, como una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="25e84-111">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="25e84-112">Pero un tipo que contiene una matriz variable de tipos que pueden transferirse en bloque de bits no se puede transferir en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="25e84-112">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
- <span data-ttu-id="25e84-113">Los tipos de valor con formato que solo contienen tipos que pueden transferirse en bloque de bits (y clases si se serializan como tipos con formato).</span><span class="sxs-lookup"><span data-stu-id="25e84-113">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="25e84-114">Para obtener más información sobre los tipos de valor con formato, vea [Serialización predeterminada para tipos de valor](default-marshaling-behavior.md#default-marshaling-for-value-types).</span><span class="sxs-lookup"><span data-stu-id="25e84-114">For more information about formatted value types, see [Default marshaling for value types](default-marshaling-behavior.md#default-marshaling-for-value-types).</span></span>  
  
 <span data-ttu-id="25e84-115">Las referencias a objetos no pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="25e84-115">Object references are not blittable.</span></span> <span data-ttu-id="25e84-116">Esto incluye una matriz de referencias a objetos que pueden transferirse en bloque de bits por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="25e84-116">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="25e84-117">Por ejemplo, se puede definir una estructura que puede transferirse en bloque de bits, pero no se puede definir un tipo que puede transferirse en bloque de bits que contiene una matriz de referencias a esas estructuras.</span><span class="sxs-lookup"><span data-stu-id="25e84-117">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="25e84-118">Como optimización, las matrices de tipos que pueden transferirse en bloque de bits y las clases que solo contienen miembros que pueden transferirse en bloque de bits se [anclan](copying-and-pinning.md) en lugar de copiarse durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="25e84-118">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="25e84-119">Estos tipos pueden parecer serializados como parámetros In/Out cuando el autor y el destinatario de la llamada están en el mismo contenedor.</span><span class="sxs-lookup"><span data-stu-id="25e84-119">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="25e84-120">Pero estos tipos se serializan realmente como parámetros In y se deben aplicar los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> si se quiere serializar el argumento como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="25e84-120">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="25e84-121">Algunos tipos de datos administrados requieren una representación diferente en un entorno sin administrar.</span><span class="sxs-lookup"><span data-stu-id="25e84-121">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="25e84-122">Estos tipos de datos que no pueden transferirse en bloque de bits se deben convertir a un formato que se pueda serializar.</span><span class="sxs-lookup"><span data-stu-id="25e84-122">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="25e84-123">Por ejemplo, las cadenas administradas son tipos que no pueden transferirse en bloque de bits porque se deben convertir en objetos de cadena antes de que se puedan serializar.</span><span class="sxs-lookup"><span data-stu-id="25e84-123">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="25e84-124">En la tabla siguiente se enumeran los tipos del espacio de nombres <xref:System> que no pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="25e84-124">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="25e84-125">[Delegados](default-marshaling-behavior.md#default-marshaling-for-delegates), que son estructuras de datos que hacen referencia a un método estático o a una instancia de clase, y que tampoco pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="25e84-125">[Delegates](default-marshaling-behavior.md#default-marshaling-for-delegates), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="25e84-126">Tipo que no puede transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="25e84-126">Non-blittable type</span></span>|<span data-ttu-id="25e84-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="25e84-127">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="25e84-128">System.Array</span><span class="sxs-lookup"><span data-stu-id="25e84-128">System.Array</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="25e84-129">Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="25e84-129">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="25e84-130">[System.Boolean](/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="25e84-130">[System.Boolean](/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span></span>|<span data-ttu-id="25e84-131">Se convierte a un valor de uno, dos o cuatro bytes con `true` como 1 o -1.</span><span class="sxs-lookup"><span data-stu-id="25e84-131">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="25e84-132">[System.Char](/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="25e84-132">[System.Char](/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span></span>|<span data-ttu-id="25e84-133">Se convierte a un carácter ANSI o Unicode.</span><span class="sxs-lookup"><span data-stu-id="25e84-133">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="25e84-134">[System.Class](/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="25e84-134">[System.Class](/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span></span>|<span data-ttu-id="25e84-135">Se convierte a una interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="25e84-135">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="25e84-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="25e84-136">System.Object</span></span>](default-marshaling-for-objects.md)|<span data-ttu-id="25e84-137">Se convierte a una variante o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="25e84-137">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="25e84-138">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="25e84-138">System.Mdarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="25e84-139">Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="25e84-139">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="25e84-140">System.String</span><span class="sxs-lookup"><span data-stu-id="25e84-140">System.String</span></span>](default-marshaling-for-strings.md)|<span data-ttu-id="25e84-141">Se convierte a una cadena que termina en una referencia nula o a un tipo BSTR.</span><span class="sxs-lookup"><span data-stu-id="25e84-141">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="25e84-142">[System.Valuetype](/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="25e84-142">[System.Valuetype](/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span></span>|<span data-ttu-id="25e84-143">Se convierte a una estructura con un diseño de memoria fijo.</span><span class="sxs-lookup"><span data-stu-id="25e84-143">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="25e84-144">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="25e84-144">System.Szarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="25e84-145">Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="25e84-145">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="25e84-146">Solo se admiten los tipos de clase y objeto con la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="25e84-146">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="25e84-147">Para obtener los tipos correspondientes en Visual Basic, C# y C++, vea el artículo de [introducción a la biblioteca de clases](../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="25e84-147">For corresponding types in Visual Basic, C#, and C++, see the [Class Library Overview](../../standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e84-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="25e84-148">See also</span></span>

- [<span data-ttu-id="25e84-149">Comportamiento predeterminado del cálculo de referencias</span><span class="sxs-lookup"><span data-stu-id="25e84-149">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
