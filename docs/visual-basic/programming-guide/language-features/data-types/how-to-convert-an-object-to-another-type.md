---
title: Procedimiento Conversión de un objeto a otro tipo
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393966"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="a3aee-102">Cómo: Convertir un objeto en otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3aee-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="a3aee-103">Para convertir una `Object` variable en otro tipo de datos, use una palabra clave de conversión como la [función ctype](../../../language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="a3aee-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3aee-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3aee-104">Example</span></span>  
 <span data-ttu-id="a3aee-105">En el ejemplo siguiente se convierte una `Object` variable en `Integer` y `String` .</span><span class="sxs-lookup"><span data-stu-id="a3aee-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="a3aee-106">Si sabe que el contenido de una `Object` variable es de un tipo de datos determinado, es mejor convertir la variable a ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a3aee-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="a3aee-107">Si continúa usando la `Object` variable, incurrirá en la *conversión boxing* y la conversión *unboxing* (para un tipo de valor) o en el *enlace en tiempo de ejecución* (para un tipo de referencia).</span><span class="sxs-lookup"><span data-stu-id="a3aee-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="a3aee-108">Estas operaciones tienen un tiempo de ejecución adicional y hacen que el rendimiento sea más lento.</span><span class="sxs-lookup"><span data-stu-id="a3aee-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="a3aee-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a3aee-109">Compile the code</span></span>  
 <span data-ttu-id="a3aee-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a3aee-110">This example requires:</span></span>  
  
- <span data-ttu-id="a3aee-111">Una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3aee-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3aee-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3aee-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="a3aee-113">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3aee-113">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="a3aee-114">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="a3aee-114">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a3aee-115">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="a3aee-115">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="a3aee-116">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="a3aee-116">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="a3aee-117">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="a3aee-117">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="a3aee-118">Estructuras</span><span class="sxs-lookup"><span data-stu-id="a3aee-118">Structures</span></span>](structures.md)
- [<span data-ttu-id="a3aee-119">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a3aee-119">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="a3aee-120">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="a3aee-120">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
