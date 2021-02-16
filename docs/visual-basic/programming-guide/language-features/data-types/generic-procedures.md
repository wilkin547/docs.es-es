---
description: 'Más información sobre: procedimientos genéricos en Visual Basic'
title: Procedimientos genéricos
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: c8f26d66f7b657e00382ea94ed0d6093211a3e96
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434711"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="0e0e4-103">Procedimientos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e0e4-103">Generic Procedures in Visual Basic</span></span>

<span data-ttu-id="0e0e4-104">Un *procedimiento genérico*, también denominado *método genérico*, es un procedimiento definido con al menos un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-104">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="0e0e4-105">Esto permite que el código de llamada adapte los tipos de datos a sus requisitos cada vez que llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-105">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="0e0e4-106">Un procedimiento no es genérico simplemente en virtud de definirse dentro de una clase genérica o en una estructura genérica.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-106">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="0e0e4-107">Para que sea genérico, el procedimiento debe tomar al menos un parámetro de tipo, además de los parámetros normales que puede llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-107">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="0e0e4-108">Una clase o estructura genérica puede contener procedimientos no genéricos, y una clase, estructura o módulo no genéricos pueden contener procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-108">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="0e0e4-109">Un procedimiento genérico puede usar sus parámetros de tipo en su lista de parámetros normal, en su tipo de valor devuelto si tiene uno, y en su código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-109">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="0e0e4-110">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="0e0e4-110">Type Inference</span></span>  

 <span data-ttu-id="0e0e4-111">Puede llamar a un procedimiento genérico sin proporcionar ningún argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-111">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="0e0e4-112">Si se llama de esta manera, el compilador intenta determinar los tipos de datos adecuados que se van a pasar a los argumentos de tipo del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-112">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="0e0e4-113">Esto se denomina *inferencia de tipos*.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-113">This is called *type inference*.</span></span> <span data-ttu-id="0e0e4-114">En el código siguiente se muestra una llamada en la que el compilador deduce que debe pasar `String` el tipo al parámetro de tipo `t` .</span><span class="sxs-lookup"><span data-stu-id="0e0e4-114">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="0e0e4-115">Si el compilador no puede inferir los argumentos de tipo del contexto de la llamada, notifica un error.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-115">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="0e0e4-116">Una posible causa de este error es que la clasificación de una matriz no coincide.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-116">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="0e0e4-117">Por ejemplo, supongamos que define un parámetro normal como una matriz de un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-117">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="0e0e4-118">Si llama al procedimiento genérico que proporciona una matriz de un rango diferente (número de dimensiones), la incoherencia provocará un error en la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-118">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="0e0e4-119">En el código siguiente se muestra una llamada en la que se pasa una matriz bidimensional a un procedimiento que espera una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-119">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="0e0e4-120">Solo se puede invocar la inferencia de tipos si se omiten todos los argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-120">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="0e0e4-121">Si proporciona un argumento de tipo, debe proporcionarlos todos.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-121">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="0e0e4-122">La inferencia de tipos solo se admite para los procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-122">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="0e0e4-123">No se puede invocar la inferencia de tipos en clases, estructuras, interfaces o delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-123">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e0e4-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e0e4-124">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0e0e4-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e0e4-125">Description</span></span>  

 <span data-ttu-id="0e0e4-126">En el ejemplo siguiente se define un `Function` procedimiento genérico para buscar un elemento determinado en una matriz.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-126">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="0e0e4-127">Define un parámetro de tipo y lo usa para construir los dos parámetros en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-127">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0e0e4-128">Código</span><span class="sxs-lookup"><span data-stu-id="0e0e4-128">Code</span></span>  

 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="0e0e4-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e0e4-129">Comments</span></span>  

 <span data-ttu-id="0e0e4-130">En el ejemplo anterior se requiere la capacidad de comparar `searchValue` con cada elemento de `searchArray` .</span><span class="sxs-lookup"><span data-stu-id="0e0e4-130">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="0e0e4-131">Para garantizar esta capacidad, restringe el parámetro de tipo `T` para implementar la <xref:System.IComparable%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-131">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="0e0e4-132">El código utiliza el <xref:System.IComparable%601.CompareTo%2A> método en lugar del `=` operador, porque no hay ninguna garantía de que un argumento de tipo proporcionado para `T` admita el `=` operador.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-132">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="0e0e4-133">Puede probar el `findElement` procedimiento con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-133">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="0e0e4-134">Las llamadas anteriores para `MsgBox` Mostrar "0", "1" y "-1", respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-134">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0e4-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e0e4-135">See also</span></span>

- [<span data-ttu-id="0e0e4-136">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e0e4-136">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="0e0e4-137">Procedimiento Definición de clases capaces de proporcionar la misma funcionalidad en tipos de datos diferentes</span><span class="sxs-lookup"><span data-stu-id="0e0e4-137">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="0e0e4-138">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="0e0e4-138">How to: Use a Generic Class</span></span>](how-to-use-a-generic-class.md)
- [<span data-ttu-id="0e0e4-139">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0e0e4-139">Procedures</span></span>](../procedures/index.md)
- [<span data-ttu-id="0e0e4-140">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="0e0e4-140">Procedure Parameters and Arguments</span></span>](../procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0e0e4-141">Type List</span><span class="sxs-lookup"><span data-stu-id="0e0e4-141">Type List</span></span>](../../../language-reference/statements/type-list.md)
- [<span data-ttu-id="0e0e4-142">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="0e0e4-142">Parameter List</span></span>](../../../language-reference/statements/parameter-list.md)
