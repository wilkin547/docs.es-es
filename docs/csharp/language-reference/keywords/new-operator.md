---
title: new (Operador, Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
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
ms.openlocfilehash: 59e1cc2006548df9a7a10283a34044040e5c2fef
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="new-operator-c-reference"></a><span data-ttu-id="4c9a1-102">new (Operador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4c9a1-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="4c9a1-103">Se usa para crear objetos e invocar constructores.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="4c9a1-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c9a1-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="4c9a1-105">También se usa para crear instancias de tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="4c9a1-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="4c9a1-106">El operador `new` también se usa para invocar el constructor predeterminado para tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="4c9a1-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c9a1-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="4c9a1-108">En la instrucción anterior, `i` se ha inicializado en `0`, que es el valor predeterminado para el tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="4c9a1-109">La instrucción tiene el mismo efecto que lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c9a1-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="4c9a1-110">Para obtener una lista completa de valores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="4c9a1-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="4c9a1-111">Recuerde que es un error declarar un constructor predeterminado para una [struct](../../../csharp/language-reference/keywords/struct.md), ya que cada tipo de valor tiene implícitamente un constructor predeterminado público.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="4c9a1-112">Es posible declarar constructores parametrizados en un tipo struct para establecer sus valores iniciales, pero esto solo es necesario si se requieren valores distintos de los predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="4c9a1-113">Los objetos de tipo de valor (como los structs) se crean en la pila, mientras que los objetos de tipo de referencia (como las clases) se crean en el montón.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="4c9a1-114">Ambos tipos de objetos se destruyen automáticamente, pero los objetos basados en tipos de valor se destruyen cuando salen del ámbito, mientras que los objetos basados en tipos de referencia se destruyen en un momento no especificado después de que se haya quitado la última referencia a ellos.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="4c9a1-115">En el caso de los tipos de referencia que consumen recursos fijos, como grandes cantidades de memoria, identificadores de archivo o conexiones de red, a veces es conveniente emplear la finalización determinista para asegurarse de que el objeto se destruya en cuanto sea posible.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="4c9a1-116">Para obtener más información, vea [Instrucción using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4c9a1-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="4c9a1-117">El operador `new` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="4c9a1-118">Si el operador `new` no puede asignar memoria, se produce la excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c9a1-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c9a1-119">Example</span></span>  
 <span data-ttu-id="4c9a1-120">En el ejemplo siguiente, se crean y se inicializan un objeto `struct` y un objeto de clase mediante el operador `new` y, después, se les asignan valores.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="4c9a1-121">Se muestran el valor predeterminado y los valores asignados.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-121">The default and the assigned values are displayed.</span></span>  
  
 <span data-ttu-id="4c9a1-122">[!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4c9a1-122">[!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="4c9a1-123">Observe en el ejemplo que el valor predeterminado de una cadena es `null`.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-123">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="4c9a1-124">Por lo tanto, no se muestra.</span><span class="sxs-lookup"><span data-stu-id="4c9a1-124">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4c9a1-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4c9a1-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4c9a1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c9a1-126">See Also</span></span>  
 <span data-ttu-id="4c9a1-127">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a1-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4c9a1-128">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a1-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4c9a1-129">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a1-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4c9a1-130">[Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a1-130">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="4c9a1-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="4c9a1-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="4c9a1-132">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="4c9a1-132">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

