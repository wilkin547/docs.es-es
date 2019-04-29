---
title: Procedimiento Crear una unión de C/C ++ mediante atributos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: 0c3ebf248f5d2f20e2fff25fb8326a294b51d153
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789095"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="f455c-102">Procedimiento Crear una unión de C/c ++ mediante atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f455c-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="f455c-103">Mediante el uso de atributos, puede personalizar la manera en que los structs se disponen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="f455c-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="f455c-104">Por ejemplo, puede crear lo que se conoce como una unión en C/ C++ mediante los atributos `StructLayout(LayoutKind.Explicit)` y `FieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="f455c-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f455c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f455c-105">Example</span></span>  
 <span data-ttu-id="f455c-106">En este segmento de código, todos los campos de `TestUnion` empiezan en la misma ubicación en la memoria.</span><span class="sxs-lookup"><span data-stu-id="f455c-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="f455c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f455c-107">Example</span></span>  
 <span data-ttu-id="f455c-108">A continuación se muestra otro ejemplo en el que los campos empiezan en ubicaciones diferentes establecidas explícitamente.</span><span class="sxs-lookup"><span data-stu-id="f455c-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="f455c-109">Los dos campos enteros, `i1` e `i2`, tiene las mismas ubicaciones en la memoria que `lg`.</span><span class="sxs-lookup"><span data-stu-id="f455c-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="f455c-110">Este tipo de control sobre el diseño del struct es útil cuando se usa la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="f455c-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f455c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f455c-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="f455c-112">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f455c-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="f455c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f455c-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="f455c-114">Reflexión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f455c-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="f455c-115">Atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f455c-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- <span data-ttu-id="f455c-116">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="f455c-116">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>
- <span data-ttu-id="f455c-117">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="f455c-117">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
