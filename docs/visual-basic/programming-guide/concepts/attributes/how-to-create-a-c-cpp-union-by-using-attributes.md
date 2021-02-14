---
description: 'Más información acerca de cómo: crear una Unión de C/C++ mediante atributos (Visual Basic)'
title: 'Cómo: crear una Unión de C/C++ mediante atributos'
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: 10717ec97efe866f4c3993cc26789f29d97b148a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100437753"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="0a463-103">How to: Create a C/C++ Union by Using Attributes (Visual Basic) (Creación de uniones de C/C++ mediante la utilización de atributos [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0a463-103">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>

<span data-ttu-id="0a463-104">Mediante el uso de atributos, puede personalizar la manera en que los structs se disponen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="0a463-104">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="0a463-105">Por ejemplo, puede crear lo que se conoce como una unión en C/ C++ mediante los atributos `StructLayout(LayoutKind.Explicit)` y `FieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="0a463-105">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="0a463-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a463-106">Example</span></span>

<span data-ttu-id="0a463-107">En este segmento de código, todos los campos de `TestUnion` empiezan en la misma ubicación en la memoria.</span><span class="sxs-lookup"><span data-stu-id="0a463-107">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

```vb
' Add an Imports statement for System.Runtime.InteropServices.

<System.Runtime.InteropServices.StructLayout(
      System.Runtime.InteropServices.LayoutKind.Explicit)>
Structure TestUnion
    <System.Runtime.InteropServices.FieldOffset(0)>
    Public i As Integer

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public d As Double

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public c As Char

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public b As Byte
End Structure
```

## <a name="example"></a><span data-ttu-id="0a463-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a463-108">Example</span></span>

<span data-ttu-id="0a463-109">A continuación se muestra otro ejemplo en el que los campos empiezan en ubicaciones diferentes establecidas explícitamente.</span><span class="sxs-lookup"><span data-stu-id="0a463-109">The following is another example where fields start at different explicitly set locations.</span></span>

```vb
' Add an Imports statement for System.Runtime.InteropServices.

 <System.Runtime.InteropServices.StructLayout(
      System.Runtime.InteropServices.LayoutKind.Explicit)>
Structure TestExplicit
     <System.Runtime.InteropServices.FieldOffset(0)>
     Public lg As Long

     <System.Runtime.InteropServices.FieldOffset(0)>
     Public i1 As Integer

     <System.Runtime.InteropServices.FieldOffset(4)>
     Public i2 As Integer

     <System.Runtime.InteropServices.FieldOffset(8)>
     Public d As Double

     <System.Runtime.InteropServices.FieldOffset(12)>
     Public c As Char

     <System.Runtime.InteropServices.FieldOffset(14)>
     Public b As Byte
 End Structure
```

<span data-ttu-id="0a463-110">Los dos campos enteros, `i1` e `i2`, tiene las mismas ubicaciones en la memoria que `lg`.</span><span class="sxs-lookup"><span data-stu-id="0a463-110">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="0a463-111">Este tipo de control sobre el diseño del struct es útil cuando se usa la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="0a463-111">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a463-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a463-112">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="0a463-113">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a463-113">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="0a463-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="0a463-114">Attributes</span></span>](../../../../standard/attributes/index.md)
- <span data-ttu-id="0a463-115">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0a463-115">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="0a463-116">Atributos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a463-116">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- <span data-ttu-id="0a463-117">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0a463-117">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md)</span></span>
- <span data-ttu-id="0a463-118">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="0a463-118">[Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)</span></span>
