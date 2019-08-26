---
title: Tipos que pueden o que no pueden transferirse en bloque de bits
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2cdaa312c037714a34e25e62ad318c9bc745ea7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953189"
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="d33a2-102">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="d33a2-102">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="d33a2-103">La mayoría de los tipos de datos tienen una representación común en la memoria administrada y no administrada, y no requieren un tratamiento especial por parte del serializador de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="d33a2-103">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="d33a2-104">Estos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no requieren conversión cuando se pasan entre código administrado y código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d33a2-104">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="d33a2-105">Las estructuras que se devuelven de llamadas de invocación de plataforma deben ser tipos que pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="d33a2-105">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="d33a2-106">La invocación de plataforma no admite estructuras que no pueden transferirse en bloque de bits como tipos de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d33a2-106">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="d33a2-107">Los siguientes tipos del espacio de nombres <xref:System> son tipos que pueden transferirse en bloque de bits:</span><span class="sxs-lookup"><span data-stu-id="d33a2-107">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
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
  
 <span data-ttu-id="d33a2-108">Los siguientes tipos complejos también son tipos que pueden transferirse en bloque de bits:</span><span class="sxs-lookup"><span data-stu-id="d33a2-108">The following complex types are also blittable types:</span></span>  
  
- <span data-ttu-id="d33a2-109">Las matrices unidimensionales de tipos que pueden transferirse en bloque de bits, como una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="d33a2-109">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="d33a2-110">Pero un tipo que contiene una matriz variable de tipos que pueden transferirse en bloque de bits no se puede transferir en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="d33a2-110">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
- <span data-ttu-id="d33a2-111">Los tipos de valor con formato que solo contienen tipos que pueden transferirse en bloque de bits (y clases si se serializan como tipos con formato).</span><span class="sxs-lookup"><span data-stu-id="d33a2-111">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="d33a2-112">Para obtener más información sobre los tipos de valor con formato, vea [Serialización predeterminada para tipos de valor](default-marshaling-behavior.md#default-marshaling-for-value-types).</span><span class="sxs-lookup"><span data-stu-id="d33a2-112">For more information about formatted value types, see [Default marshaling for value types](default-marshaling-behavior.md#default-marshaling-for-value-types).</span></span>  
  
 <span data-ttu-id="d33a2-113">Las referencias a objetos no pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="d33a2-113">Object references are not blittable.</span></span> <span data-ttu-id="d33a2-114">Esto incluye una matriz de referencias a objetos que pueden transferirse en bloque de bits por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="d33a2-114">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="d33a2-115">Por ejemplo, se puede definir una estructura que puede transferirse en bloque de bits, pero no se puede definir un tipo que puede transferirse en bloque de bits que contiene una matriz de referencias a esas estructuras.</span><span class="sxs-lookup"><span data-stu-id="d33a2-115">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="d33a2-116">Como optimización, las matrices de tipos que pueden transferirse en bloque de bits y las clases que solo contienen miembros que pueden transferirse en bloque de bits se [anclan](../../../docs/framework/interop/copying-and-pinning.md) en lugar de copiarse durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="d33a2-116">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](../../../docs/framework/interop/copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="d33a2-117">Estos tipos pueden parecer serializados como parámetros In/Out cuando el autor y el destinatario de la llamada están en el mismo contenedor.</span><span class="sxs-lookup"><span data-stu-id="d33a2-117">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="d33a2-118">Pero estos tipos se serializan realmente como parámetros In y se deben aplicar los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> si se quiere serializar el argumento como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="d33a2-118">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="d33a2-119">Algunos tipos de datos administrados requieren una representación diferente en un entorno sin administrar.</span><span class="sxs-lookup"><span data-stu-id="d33a2-119">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="d33a2-120">Estos tipos de datos que no pueden transferirse en bloque de bits se deben convertir a un formato que se pueda serializar.</span><span class="sxs-lookup"><span data-stu-id="d33a2-120">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="d33a2-121">Por ejemplo, las cadenas administradas son tipos que no pueden transferirse en bloque de bits porque se deben convertir en objetos de cadena antes de que se puedan serializar.</span><span class="sxs-lookup"><span data-stu-id="d33a2-121">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="d33a2-122">En la tabla siguiente se enumeran los tipos del espacio de nombres <xref:System> que no pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="d33a2-122">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="d33a2-123">[Delegados](default-marshaling-behavior.md#default-marshaling-for-delegates), que son estructuras de datos que hacen referencia a un método estático o a una instancia de clase, y que tampoco pueden transferirse en bloque de bits.</span><span class="sxs-lookup"><span data-stu-id="d33a2-123">[Delegates](default-marshaling-behavior.md#default-marshaling-for-delegates), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="d33a2-124">Tipo que no puede transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="d33a2-124">Non-blittable type</span></span>|<span data-ttu-id="d33a2-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d33a2-125">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="d33a2-126">System.Array</span><span class="sxs-lookup"><span data-stu-id="d33a2-126">System.Array</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="d33a2-127">Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="d33a2-127">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="d33a2-128">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d33a2-128">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span></span>|<span data-ttu-id="d33a2-129">Se convierte a un valor de uno, dos o cuatro bytes con `true` como 1 o -1.</span><span class="sxs-lookup"><span data-stu-id="d33a2-129">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="d33a2-130">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d33a2-130">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span></span>|<span data-ttu-id="d33a2-131">Se convierte a un carácter ANSI o Unicode.</span><span class="sxs-lookup"><span data-stu-id="d33a2-131">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="d33a2-132">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d33a2-132">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span></span>|<span data-ttu-id="d33a2-133">Se convierte a una interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="d33a2-133">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="d33a2-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="d33a2-134">System.Object</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)|<span data-ttu-id="d33a2-135">Se convierte a una variante o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="d33a2-135">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="d33a2-136">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="d33a2-136">System.Mdarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="d33a2-137">Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="d33a2-137">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="d33a2-138">System.String</span><span class="sxs-lookup"><span data-stu-id="d33a2-138">System.String</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)|<span data-ttu-id="d33a2-139">Se convierte a una cadena que termina en una referencia nula o a un tipo BSTR.</span><span class="sxs-lookup"><span data-stu-id="d33a2-139">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="d33a2-140">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d33a2-140">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span></span>|<span data-ttu-id="d33a2-141">Se convierte a una estructura con un diseño de memoria fijo.</span><span class="sxs-lookup"><span data-stu-id="d33a2-141">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="d33a2-142">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="d33a2-142">System.Szarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="d33a2-143">Se convierte a una matriz de estilo de C o a una `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="d33a2-143">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="d33a2-144">Solo se admiten los tipos de clase y objeto con la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="d33a2-144">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="d33a2-145">Para obtener los tipos correspondientes en Visual Basic, C# y C++, vea el artículo de [introducción a la biblioteca de clases](../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d33a2-145">For corresponding types in Visual Basic, C#, and C++, see the [Class Library Overview](../../standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33a2-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d33a2-146">See also</span></span>

- [<span data-ttu-id="d33a2-147">Comportamiento predeterminado del cálculo de referencias</span><span class="sxs-lookup"><span data-stu-id="d33a2-147">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)
