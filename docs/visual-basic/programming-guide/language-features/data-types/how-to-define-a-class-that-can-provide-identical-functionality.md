---
title: Procedimiento Definición de clases capaces de proporcionar la misma funcionalidad en tipos de datos diferentes
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 268daf333dc5463e5436304cec188a9e6d477166
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077129"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a><span data-ttu-id="73a6e-102">Cómo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73a6e-102">How to: Define a Class That Can Provide Identical Functionality on Different Data Types (Visual Basic)</span></span>

<span data-ttu-id="73a6e-103">Puede definir una clase desde la que se puedan crear objetos que proporcionen una funcionalidad idéntica en tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="73a6e-103">You can define a class from which you can create objects that provide identical functionality on different data types.</span></span> <span data-ttu-id="73a6e-104">Para ello, especifique uno o más *parámetros de tipo* en la definición.</span><span class="sxs-lookup"><span data-stu-id="73a6e-104">To do this, you specify one or more *type parameters* in the definition.</span></span> <span data-ttu-id="73a6e-105">Posteriormente, la clase puede servir de plantilla para los objetos que usan distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="73a6e-105">The class can then serve as a template for objects that use various data types.</span></span> <span data-ttu-id="73a6e-106">Una clase definida de esta manera se denomina *clase genérica*.</span><span class="sxs-lookup"><span data-stu-id="73a6e-106">A class defined in this way is called a *generic class*.</span></span>  
  
 <span data-ttu-id="73a6e-107">La ventaja de definir una clase genérica es que se define una sola vez y, después, el código puede usarla para crear muchos objetos que emplean una gran variedad de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="73a6e-107">The advantage of defining a generic class is that you define it just once, and your code can use it to create many objects that use a wide variety of data types.</span></span> <span data-ttu-id="73a6e-108">El resultado es rendimiento mayor que al definir la clase con el tipo `Object` .</span><span class="sxs-lookup"><span data-stu-id="73a6e-108">This results in better performance than defining the class with the `Object` type.</span></span>  
  
 <span data-ttu-id="73a6e-109">Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.</span><span class="sxs-lookup"><span data-stu-id="73a6e-109">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
### <a name="to-define-a-class-with-a-type-parameter"></a><span data-ttu-id="73a6e-110">Para definir una clase con un parámetro de tipo</span><span class="sxs-lookup"><span data-stu-id="73a6e-110">To define a class with a type parameter</span></span>  
  
1. <span data-ttu-id="73a6e-111">Defina la clase de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="73a6e-111">Define the class in the normal way.</span></span>  
  
2. <span data-ttu-id="73a6e-112">Agregue `(Of` *typeparameter* `)` inmediatamente después del nombre de clase para especificar un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="73a6e-112">Add `(Of` *typeparameter*`)` immediately after the class name to specify a type parameter.</span></span>  
  
3. <span data-ttu-id="73a6e-113">Si tiene más de un parámetro de tipo, realice una lista separada por comas entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="73a6e-113">If you have more than one type parameter, make a comma-separated list inside the parentheses.</span></span> <span data-ttu-id="73a6e-114">No repita la palabra clave `Of` .</span><span class="sxs-lookup"><span data-stu-id="73a6e-114">Do not repeat the `Of` keyword.</span></span>  
  
4. <span data-ttu-id="73a6e-115">Si el código realiza operaciones en un parámetro de tipo distintas de la asignación simple, siga ese parámetro de tipo con una cláusula `As` para agregar una o más *restricciones*.</span><span class="sxs-lookup"><span data-stu-id="73a6e-115">If your code performs operations on a type parameter other than simple assignment, follow that type parameter with an `As` clause to add one or more *constraints*.</span></span> <span data-ttu-id="73a6e-116">Una restricción garantiza que el tipo proporcionado para ese parámetro de tipo satisfaga un requisito como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="73a6e-116">A constraint guarantees that the type supplied for that type parameter satisfies a requirement such as the following:</span></span>  
  
    - <span data-ttu-id="73a6e-117">Admitir una operación, como `>`, que realice el código.</span><span class="sxs-lookup"><span data-stu-id="73a6e-117">Supports an operation, such as `>`, that your code performs</span></span>  
  
    - <span data-ttu-id="73a6e-118">Admita a un miembro, como un método, al que accede el código.</span><span class="sxs-lookup"><span data-stu-id="73a6e-118">Supports a member, such as a method, that your code accesses</span></span>  
  
    - <span data-ttu-id="73a6e-119">Exponer un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="73a6e-119">Exposes a parameterless constructor</span></span>  
  
     <span data-ttu-id="73a6e-120">Si no especifica ninguna restricción, las únicas operaciones y miembros que el código podrá usar son las que admite el [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="73a6e-120">If you do not specify any constraints, the only operations and members your code can use are those supported by the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="73a6e-121">Para obtener más información, consulta [Type List](../../../language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="73a6e-121">For more information, see [Type List](../../../language-reference/statements/type-list.md).</span></span>  
  
5. <span data-ttu-id="73a6e-122">Identifique cada miembro de clase que se va a declarar con un tipo suministrado y declárelo `As` `typeparameter` .</span><span class="sxs-lookup"><span data-stu-id="73a6e-122">Identify every class member that is to be declared with a supplied type, and declare it `As` `typeparameter`.</span></span> <span data-ttu-id="73a6e-123">Esto se aplica al almacenamiento interno, los parámetros de procedimiento y los valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="73a6e-123">This applies to internal storage, procedure parameters, and return values.</span></span>  
  
6. <span data-ttu-id="73a6e-124">Asegúrese de que el código solo usa operaciones y métodos admitidos por cualquier tipo de datos que pueda proporcionar a `itemType`.</span><span class="sxs-lookup"><span data-stu-id="73a6e-124">Be sure your code uses only operations and methods that are supported by any data type it can supply to `itemType`.</span></span>  
  
     <span data-ttu-id="73a6e-125">En el ejemplo siguiente se define una clase que administra una lista muy simple.</span><span class="sxs-lookup"><span data-stu-id="73a6e-125">The following example defines a class that manages a very simple list.</span></span> <span data-ttu-id="73a6e-126">Contiene la lista de la matriz interna `items`y el código que la usa puede declarar el tipo de datos de los elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="73a6e-126">It holds the list in the internal array `items`, and the using code can declare the data type of the list elements.</span></span> <span data-ttu-id="73a6e-127">Un constructor con parámetros permite que el código de uso establezca el límite superior de `items` , y el constructor sin parámetros lo establece en 9 (para un total de 10 elementos).</span><span class="sxs-lookup"><span data-stu-id="73a6e-127">A parameterized constructor allows the using code to set the upper bound of `items`, and the parameterless constructor sets this to 9 (for a total of 10 items).</span></span>  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     <span data-ttu-id="73a6e-128">Puede declarar una clase de `simpleList` para que contenga una lista de valores `Integer` , otra para que contenga una lista de valores `String` y otra para que contenga valores `Date` .</span><span class="sxs-lookup"><span data-stu-id="73a6e-128">You can declare a class from `simpleList` to hold a list of `Integer` values, another class to hold a list of `String` values, and another to hold `Date` values.</span></span> <span data-ttu-id="73a6e-129">Excepto para el tipo de datos de los miembros de la lista, los objetos creados a partir de todas estas clases se comportan exactamente igual.</span><span class="sxs-lookup"><span data-stu-id="73a6e-129">Except for the data type of the list members, objects created from all these classes behave identically.</span></span>  
  
     <span data-ttu-id="73a6e-130">El argumento de tipo que el código que lo usa proporciona a `itemType` puede ser un tipo intrínseco como `Boolean` o `Double`, una estructura, una enumeración o cualquier tipo de clase, incluida una que defina la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73a6e-130">The type argument that the using code supplies to `itemType` can be an intrinsic type such as `Boolean` or `Double`, a structure, an enumeration, or any type of class, including one that your application defines.</span></span>  
  
     <span data-ttu-id="73a6e-131">Puede probar la clase `simpleList` con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="73a6e-131">You can test the class `simpleList` with the following code.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="73a6e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="73a6e-132">See also</span></span>

- [<span data-ttu-id="73a6e-133">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="73a6e-133">Data Types</span></span>](index.md)
- [<span data-ttu-id="73a6e-134">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73a6e-134">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="73a6e-135">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="73a6e-135">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="73a6e-136">De</span><span class="sxs-lookup"><span data-stu-id="73a6e-136">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="73a6e-137">Type List</span><span class="sxs-lookup"><span data-stu-id="73a6e-137">Type List</span></span>](../../../language-reference/statements/type-list.md)
- [<span data-ttu-id="73a6e-138">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="73a6e-138">How to: Use a Generic Class</span></span>](how-to-use-a-generic-class.md)
- [<span data-ttu-id="73a6e-139">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="73a6e-139">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
