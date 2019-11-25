---
title: 'How to: Convert an Object to Another Type'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 19708d03b0514f4572c2baa53e05781e5949766b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350070"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="be1f8-102">Cómo: Convertir un objeto en otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be1f8-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="be1f8-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="be1f8-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be1f8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be1f8-104">Example</span></span>  
 <span data-ttu-id="be1f8-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span><span class="sxs-lookup"><span data-stu-id="be1f8-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="be1f8-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span><span class="sxs-lookup"><span data-stu-id="be1f8-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="be1f8-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span><span class="sxs-lookup"><span data-stu-id="be1f8-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="be1f8-108">These operations all take extra execution time and make your performance slower.</span><span class="sxs-lookup"><span data-stu-id="be1f8-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be1f8-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="be1f8-109">Compiling the Code</span></span>  
 <span data-ttu-id="be1f8-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="be1f8-110">This example requires:</span></span>  
  
- <span data-ttu-id="be1f8-111">Una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be1f8-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1f8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="be1f8-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="be1f8-113">Type Conversions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be1f8-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="be1f8-114">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="be1f8-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="be1f8-115">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="be1f8-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="be1f8-116">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="be1f8-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="be1f8-117">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="be1f8-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="be1f8-118">Estructuras</span><span class="sxs-lookup"><span data-stu-id="be1f8-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="be1f8-119">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="be1f8-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="be1f8-120">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="be1f8-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
