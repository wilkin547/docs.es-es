---
title: "Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c5daa8525f45c123dabb0f59dfd29385b9e50354
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="5790a-102">Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5790a-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="5790a-103">Dado que los objetos son polimórficos, es posible que una variable de un tipo de clase base contenga un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="5790a-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="5790a-104">Para tener acceso al método del tipo derivado, es necesario volver a convertir el valor al tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="5790a-104">To access the derived type's method, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="5790a-105">En cambio, el intento de realizar una conversión de tipos sencilla en estos casos conlleva el riesgo de producir una excepción <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="5790a-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="5790a-106">Por esa razón, C# proporciona los operadores [is](../../../csharp/language-reference/keywords/is.md) y [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="5790a-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="5790a-107">Puede usar estos operadores para comprobar si una conversión de tipo se realizará correctamente sin hacer que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="5790a-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="5790a-108">En general, el operador `as` suele ser más eficaz, ya que devuelve el valor de la conversión de tipo si esta puede realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="5790a-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="5790a-109">El operador `is` devuelve solamente un valor Boolean.</span><span class="sxs-lookup"><span data-stu-id="5790a-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="5790a-110">Así, puede usarse cuando simplemente quiera determinar el tipo de un objeto pero no tenga que realizar una conversión de tipo del mismo.</span><span class="sxs-lookup"><span data-stu-id="5790a-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5790a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5790a-111">Example</span></span>  
 <span data-ttu-id="5790a-112">En los ejemplos siguientes se muestra cómo usar los operadores `is` y `as` para realizar una conversión de un tipo de referencia a otro sin el riesgo de que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="5790a-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="5790a-113">En el ejemplo también se muestra cómo usar el operador `as` con tipos de valor que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5790a-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 <span data-ttu-id="5790a-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5790a-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5790a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5790a-115">See Also</span></span>  
 <span data-ttu-id="5790a-116">[Types](../../../csharp/programming-guide/types/index.md)  (Tipos [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="5790a-116">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="5790a-117">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  (Conversiones de tipos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="5790a-117">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="5790a-118">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="5790a-118">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)

