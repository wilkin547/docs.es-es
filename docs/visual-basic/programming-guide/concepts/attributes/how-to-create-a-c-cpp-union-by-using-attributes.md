---
title: 'Cómo: crear una Unión deC++ C mediante atributos'
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: acb8dc781e2872ae46e5aa058a98b3dd98f3e064
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349496"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="ab505-102">Cómo: crear una Unión de CC++ /mediante atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab505-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>

<span data-ttu-id="ab505-103">Mediante el uso de atributos, puede personalizar la manera en que los structs se disponen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ab505-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="ab505-104">Por ejemplo, puede crear lo que se conoce como una unión en C/ C++ mediante los atributos `StructLayout(LayoutKind.Explicit)` y `FieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="ab505-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="ab505-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab505-105">Example</span></span>

<span data-ttu-id="ab505-106">En este segmento de código, todos los campos de `TestUnion` empiezan en la misma ubicación en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ab505-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

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

## <a name="example"></a><span data-ttu-id="ab505-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab505-107">Example</span></span>

<span data-ttu-id="ab505-108">A continuación se muestra otro ejemplo en el que los campos empiezan en ubicaciones diferentes establecidas explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ab505-108">The following is another example where fields start at different explicitly set locations.</span></span>

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

<span data-ttu-id="ab505-109">Los dos campos enteros, `i1` e `i2`, tiene las mismas ubicaciones en la memoria que `lg`.</span><span class="sxs-lookup"><span data-stu-id="ab505-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="ab505-110">Este tipo de control sobre el diseño del struct es útil cuando se usa la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="ab505-110">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab505-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab505-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="ab505-112">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab505-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="ab505-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab505-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="ab505-114">Reflexión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab505-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="ab505-115">Atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab505-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- <span data-ttu-id="ab505-116">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="ab505-116">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>
- <span data-ttu-id="ab505-117">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="ab505-117">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
