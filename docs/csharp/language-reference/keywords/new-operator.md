---
title: new (Operador, Referencia de C#)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 2ba3c574897ae5f1ec66e3810e23f0af74bd8872
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268926"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="172bd-102">new (Operador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="172bd-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="172bd-103">Se usa para crear objetos e invocar constructores.</span><span class="sxs-lookup"><span data-stu-id="172bd-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="172bd-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="172bd-104">For example:</span></span>  
  
```csharp
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="172bd-105">También se usa para crear instancias de tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="172bd-105">It is also used to create instances of anonymous types:</span></span>  
  
```csharp
var query = from cust in customers  
            select new { Name = cust.Name, Address = cust.PrimaryAddress };  
```  
  
 <span data-ttu-id="172bd-106">El operador `new` también se usa para invocar el constructor predeterminado para tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="172bd-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="172bd-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="172bd-107">For example:</span></span>  
  
```csharp
int i = new int();  
```  
  
 <span data-ttu-id="172bd-108">En la instrucción anterior, `i` se ha inicializado en `0`, que es el valor predeterminado para el tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="172bd-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="172bd-109">La instrucción tiene el mismo efecto que lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="172bd-109">The statement has the same effect as the following:</span></span>  
  
```csharp
int i = 0;  
```  
  
 <span data-ttu-id="172bd-110">Para obtener una lista completa de valores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="172bd-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="172bd-111">Recuerde que es un error declarar un constructor predeterminado para una [struct](../../../csharp/language-reference/keywords/struct.md), ya que cada tipo de valor tiene implícitamente un constructor predeterminado público.</span><span class="sxs-lookup"><span data-stu-id="172bd-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="172bd-112">Es posible declarar constructores parametrizados en un tipo struct para establecer sus valores iniciales, pero esto solo es necesario si se requieren valores distintos de los predeterminados.</span><span class="sxs-lookup"><span data-stu-id="172bd-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="172bd-113">Los objetos de tipo de valor, como las estructuras, y los objetos de tipo de referencia, como las clases, se destruyen automáticamente, pero los objetos de tipo de valor se destruyen junto al contexto que los contiene. En el caso de los objetos de tipo de referencia, los destruye el recolector de elementos no utilizados en un momento no especificado después de que se haya quitado la última referencia a ellos.</span><span class="sxs-lookup"><span data-stu-id="172bd-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="172bd-114">Para los tipos que contienen recursos como identificadores de archivos o conexiones de red, lo recomendable es llevar a cabo una limpieza determinista para asegurarse de que los recursos que contienen se liberan tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="172bd-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="172bd-115">Para obtener más información, vea [Instrucción using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="172bd-115">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="172bd-116">El operador `new` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="172bd-116">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="172bd-117">Si el operador `new` no puede asignar memoria, se produce la excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="172bd-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="172bd-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="172bd-118">Example</span></span>  
 <span data-ttu-id="172bd-119">En el ejemplo siguiente, se crean y se inicializan un objeto `struct` y un objeto de clase mediante el operador `new` y, después, se les asignan valores.</span><span class="sxs-lookup"><span data-stu-id="172bd-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="172bd-120">Se muestran el valor predeterminado y los valores asignados.</span><span class="sxs-lookup"><span data-stu-id="172bd-120">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="172bd-121">Observe en el ejemplo que el valor predeterminado de una cadena es `null`.</span><span class="sxs-lookup"><span data-stu-id="172bd-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="172bd-122">Por lo tanto, no se muestra.</span><span class="sxs-lookup"><span data-stu-id="172bd-122">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="172bd-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="172bd-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="172bd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="172bd-124">See Also</span></span>  
 [<span data-ttu-id="172bd-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="172bd-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="172bd-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="172bd-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="172bd-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="172bd-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="172bd-128">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="172bd-128">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="172bd-129">new</span><span class="sxs-lookup"><span data-stu-id="172bd-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="172bd-130">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="172bd-130">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
