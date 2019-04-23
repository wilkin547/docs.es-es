---
title: Procedimiento Declarar un objeto usando un inicializador de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 775c40cbb62272f913297d5a58914a0c82c5a7d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305317"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="cfb6f-102">Procedimiento Declarar un objeto usando un inicializador de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfb6f-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="cfb6f-103">Los inicializadores de objeto permiten declarar y crear una instancia de una clase en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="cfb6f-104">Además, puede inicializar a uno o varios miembros de la instancia al mismo tiempo, sin invocar un constructor parametrizado.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="cfb6f-105">Cuando se usa un inicializador de objeto para crear una instancia de un tipo con nombre, el constructor predeterminado para la clase se llama, seguido de la inicialización de los miembros designados en el orden que especifique.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="cfb6f-106">El siguiente procedimiento muestra cómo crear una instancia de un `Student` clase de tres maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="cfb6f-107">La clase tiene el nombre, apellido y propiedades de año de la clase, entre otros.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="cfb6f-108">Cada una de las tres declaraciones crea una nueva instancia de `Student`, con la propiedad `First` establecido en "Michael," propiedad `Last` establecida en "Tucker" y todos los demás miembros que se establezca en sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="cfb6f-109">El resultado de cada declaración en el procedimiento es equivalente al ejemplo siguiente, que no usa a un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="cfb6f-110">Para obtener una implementación de la `Student` de clases, vea [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="cfb6f-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="cfb6f-111">Puede copiar el código en ese tema para configurar la clase y crear una lista de `Student` para trabajar con los objetos.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="cfb6f-112">Para crear un objeto de una clase con nombre mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="cfb6f-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="cfb6f-113">Comience la declaración como si planea utilizar un constructor.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="cfb6f-114">Escriba la palabra clave `With`, seguido de una lista de inicialización entre llaves.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="cfb6f-115">En la lista de inicialización, incluya cada propiedad que desea inicializar y asignarle un valor inicial.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="cfb6f-116">El nombre de la propiedad está precedido por un punto.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="cfb6f-117">Puede inicializar a uno o varios miembros de la clase.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="cfb6f-118">Como alternativa, puede declarar una nueva instancia de la clase y, a continuación, asignarle un valor.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="cfb6f-119">En primer lugar, declare una instancia de `Student`:</span><span class="sxs-lookup"><span data-stu-id="cfb6f-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="cfb6f-120">Comience la creación de una instancia de `Student` de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="cfb6f-121">Tipo `With` y, a continuación, un inicializador de objeto para inicializar uno o varios miembros de la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="cfb6f-122">Puede simplificar la definición en el paso anterior omitiendo `As Student`.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="cfb6f-123">Si lo hace, el compilador determina que `student3` es una instancia de `Student` mediante el uso de la inferencia de tipo local.</span><span class="sxs-lookup"><span data-stu-id="cfb6f-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="cfb6f-124">Para obtener más información, consulte [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="cfb6f-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb6f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfb6f-125">See also</span></span>

- [<span data-ttu-id="cfb6f-126">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="cfb6f-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="cfb6f-127">Cómo: Crear una lista de elementos</span><span class="sxs-lookup"><span data-stu-id="cfb6f-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="cfb6f-128">Inicializadores de objeto: Tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="cfb6f-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="cfb6f-129">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="cfb6f-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
