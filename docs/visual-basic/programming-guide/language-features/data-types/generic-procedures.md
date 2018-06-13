---
title: Procedimientos genéricos en Visual Basic
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
ms.openlocfilehash: 686087e4520ea5e6e69e5906c628af3ad54749da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649401"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="88427-102">Procedimientos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88427-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="88427-103">A *procedimiento genérico*, también denominado una *método genérico*, es un procedimiento definido con al menos un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="88427-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="88427-104">Esto permite que el código de llamada para personalizar los tipos de datos a sus requisitos cada vez que llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="88427-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="88427-105">Un procedimiento no es genérico el simple hecho de que se define dentro de una clase genérica o una estructura genérica.</span><span class="sxs-lookup"><span data-stu-id="88427-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="88427-106">Para ser genérico, el procedimiento debe tomar al menos un parámetro de tipo, además de los parámetros normales, puede tardar.</span><span class="sxs-lookup"><span data-stu-id="88427-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="88427-107">Una clase o estructura genérica puede contener procedimientos genéricos y una clase no genérica, estructura o módulo puede contener procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="88427-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="88427-108">Un procedimiento genérico puede usar sus parámetros de tipo en su lista de parámetros normales, en su tipo de valor devuelto, si existe una y en su procedimiento código.</span><span class="sxs-lookup"><span data-stu-id="88427-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="88427-109">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="88427-109">Type Inference</span></span>  
 <span data-ttu-id="88427-110">Puede llamar a un procedimiento genérico sin proporcionar ningún argumento de tipo en absoluto.</span><span class="sxs-lookup"><span data-stu-id="88427-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="88427-111">Si se le llama de esta forma, el compilador intenta determinar los tipos de datos adecuado para pasar a los argumentos de tipo del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="88427-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="88427-112">Esto se denomina *inferencia de tipo*.</span><span class="sxs-lookup"><span data-stu-id="88427-112">This is called *type inference*.</span></span> <span data-ttu-id="88427-113">El código siguiente muestra una llamada en la que el compilador deduce que debe pasar el tipo `String` al parámetro de tipo `t`.</span><span class="sxs-lookup"><span data-stu-id="88427-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 <span data-ttu-id="88427-114">Si el compilador no puede inferir los argumentos de tipo desde el contexto de la llamada, notifica un error.</span><span class="sxs-lookup"><span data-stu-id="88427-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="88427-115">Una posible causa de este tipo de error es un error de coincidencia de rango de matriz.</span><span class="sxs-lookup"><span data-stu-id="88427-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="88427-116">Por ejemplo, supongamos que define un parámetro normal como una matriz de un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="88427-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="88427-117">Si se llama al procedimiento genérico proporcionando una matriz de un rango diferente (número de dimensiones), hace que la falta de correspondencia producirá un error de inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="88427-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="88427-118">El código siguiente muestra una llamada en la que se pasa una matriz bidimensional a un procedimiento que espera una matriz unidimensional.</span><span class="sxs-lookup"><span data-stu-id="88427-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 <span data-ttu-id="88427-119">Puede invocar la inferencia de tipo omitiendo todos los argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="88427-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="88427-120">Si se proporciona un argumento de tipo, debe proporcionar todas ellas.</span><span class="sxs-lookup"><span data-stu-id="88427-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="88427-121">Inferencia de tipos solo se admite para los procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="88427-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="88427-122">No se puede invocar la inferencia de tipo en clases genéricas, estructuras, interfaces o delegados.</span><span class="sxs-lookup"><span data-stu-id="88427-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88427-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88427-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="88427-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="88427-124">Description</span></span>  
 <span data-ttu-id="88427-125">En el ejemplo siguiente se define un tipo genérico `Function` procedimiento para buscar un elemento determinado en una matriz.</span><span class="sxs-lookup"><span data-stu-id="88427-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="88427-126">Define un parámetro de tipo y lo utiliza para construir los dos parámetros en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="88427-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="88427-127">Código</span><span class="sxs-lookup"><span data-stu-id="88427-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="88427-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88427-128">Comments</span></span>  
 <span data-ttu-id="88427-129">En el ejemplo anterior, se requiere la capacidad para comparar `searchValue` con cada elemento de `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="88427-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="88427-130">Para garantizar esta capacidad, restringe el parámetro de tipo `T` para implementar la <xref:System.IComparable%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="88427-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="88427-131">El código usa el <xref:System.IComparable%601.CompareTo%2A> en lugar del método la `=` (operador), porque no hay ninguna garantía de que un argumento de tipo proporcionado para `T` es compatible con la `=` operador.</span><span class="sxs-lookup"><span data-stu-id="88427-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="88427-132">Puede probar el `findElement` procedimiento con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88427-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 <span data-ttu-id="88427-133">Los anteriores llamadas a `MsgBox` muestran respectivamente "0", "1" y "-1".</span><span class="sxs-lookup"><span data-stu-id="88427-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88427-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="88427-134">See Also</span></span>  
 [<span data-ttu-id="88427-135">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88427-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="88427-136">Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes</span><span class="sxs-lookup"><span data-stu-id="88427-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="88427-137">Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="88427-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="88427-138">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="88427-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="88427-139">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="88427-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="88427-140">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="88427-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="88427-141">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="88427-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
