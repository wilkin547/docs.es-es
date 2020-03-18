---
title: Procedimiento para crear una unión de C o C++ mediante atributos (C#)
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: ff8ce560444581a28b257820573224f89a274cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141575"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="834d3-102">Procedimiento para crear una unión de C o C++ mediante atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="834d3-102">How to create a C/C++ union by using attributes (C#)</span></span>

<span data-ttu-id="834d3-103">Mediante el uso de atributos, puede personalizar la manera en que los structs se disponen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="834d3-103">By using attributes, you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="834d3-104">Por ejemplo, puede crear lo que se conoce como una unión en C/ C++ mediante los atributos `StructLayout(LayoutKind.Explicit)` y `FieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="834d3-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="834d3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="834d3-105">Example</span></span>

<span data-ttu-id="834d3-106">En este segmento de código, todos los campos de `TestUnion` empiezan en la misma ubicación en la memoria.</span><span class="sxs-lookup"><span data-stu-id="834d3-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestUnion
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public byte b;
}
```

## <a name="example"></a><span data-ttu-id="834d3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="834d3-107">Example</span></span>

<span data-ttu-id="834d3-108">A continuación se muestra otro ejemplo en el que los campos empiezan en ubicaciones diferentes establecidas explícitamente.</span><span class="sxs-lookup"><span data-stu-id="834d3-108">The following is another example where fields start at different explicitly set locations.</span></span>

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestExplicit
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public long lg;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i1;

    [System.Runtime.InteropServices.FieldOffset(4)]
    public int i2;

    [System.Runtime.InteropServices.FieldOffset(8)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(12)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(14)]
    public byte b;
}
```

<span data-ttu-id="834d3-109">Los dos campos enteros, `i1` e `i2`, tiene las mismas ubicaciones en la memoria que `lg`.</span><span class="sxs-lookup"><span data-stu-id="834d3-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="834d3-110">Este tipo de control sobre el diseño del struct es útil cuando se usa la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="834d3-110">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="834d3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="834d3-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="834d3-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="834d3-112">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="834d3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="834d3-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="834d3-114">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="834d3-114">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="834d3-115">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="834d3-115">Attributes (C#)</span></span>](index.md)
- [<span data-ttu-id="834d3-116">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="834d3-116">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="834d3-117">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="834d3-117">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
