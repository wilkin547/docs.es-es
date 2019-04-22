---
title: Procedimiento Convertir un objeto a otro tipo en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 1e515c0f4ce8e787754c61a9b53d247fa93c49f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814385"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="21931-102">Procedimiento Convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21931-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="21931-103">Convierte un `Object` variable a otro tipo de datos con una palabra clave de conversión como [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="21931-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21931-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21931-104">Example</span></span>  
 <span data-ttu-id="21931-105">El ejemplo siguiente se convierte un `Object` variable a un `Integer` y un `String`.</span><span class="sxs-lookup"><span data-stu-id="21931-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="21931-106">Si sabe que el contenido de un `Object` son variable de un tipo de datos determinado, es mejor convertir la variable a ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="21931-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="21931-107">Si se sigue usando el `Object` variable, se incurre en cualquiera *boxing* y *unboxing* (para un tipo de valor) o *enlace más tarde* (para un tipo de referencia).</span><span class="sxs-lookup"><span data-stu-id="21931-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="21931-108">Estas operaciones toman tiempo de ejecución adicional y ralentizan el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="21931-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21931-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="21931-109">Compiling the Code</span></span>  
 <span data-ttu-id="21931-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="21931-110">This example requires:</span></span>  
  
-   <span data-ttu-id="21931-111">Una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="21931-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21931-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="21931-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="21931-113">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21931-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="21931-114">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="21931-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="21931-115">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="21931-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="21931-116">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="21931-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="21931-117">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="21931-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="21931-118">Estructuras</span><span class="sxs-lookup"><span data-stu-id="21931-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="21931-119">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="21931-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="21931-120">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="21931-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
