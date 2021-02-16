---
description: 'Más información sobre: Cómo: declarar un objeto usando un inicializador de objeto (Visual Basic)'
title: Procedimiento para declarar un objeto mediante un inicializador de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 12f64dc4d1efb3ed2654084203241e6606ad4da6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483916"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="96a76-103">Cómo: Declarar un objeto usando un inicializador de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96a76-103">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>

<span data-ttu-id="96a76-104">Los inicializadores de objeto permiten declarar y crear instancias de una instancia de una clase en una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="96a76-104">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="96a76-105">Además, puede inicializar uno o más miembros de la instancia al mismo tiempo, sin invocar un constructor con parámetros.</span><span class="sxs-lookup"><span data-stu-id="96a76-105">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="96a76-106">Cuando se usa un inicializador de objeto para crear una instancia de un tipo con nombre, se llama al constructor sin parámetros para la clase, seguido de la inicialización de los miembros designados en el orden que se especifique.</span><span class="sxs-lookup"><span data-stu-id="96a76-106">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="96a76-107">En el siguiente procedimiento se muestra cómo crear una instancia de una `Student` clase de tres maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="96a76-107">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="96a76-108">La clase tiene las propiedades nombre, apellidos y año de clase, entre otras.</span><span class="sxs-lookup"><span data-stu-id="96a76-108">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="96a76-109">Cada una de las tres declaraciones crea una nueva instancia de `Student` , con `First` la propiedad establecida en "Michael", `Last` la propiedad establecida en "Tucker" y todos los demás miembros establecidos en sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="96a76-109">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="96a76-110">El resultado de cada declaración en el procedimiento es equivalente al ejemplo siguiente, que no usa un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="96a76-110">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="96a76-111">Para obtener una implementación de la `Student` clase, vea [Cómo: crear una lista de elementos](../../concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="96a76-111">For an implementation of the `Student` class, see [How to: Create a List of Items](../../concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="96a76-112">Puede copiar el código de ese tema para configurar la clase y crear una lista de `Student` objetos con los que trabajar.</span><span class="sxs-lookup"><span data-stu-id="96a76-112">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="96a76-113">Para crear un objeto de una clase con nombre mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="96a76-113">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="96a76-114">Comience la declaración como si hubiera planeado utilizar un constructor.</span><span class="sxs-lookup"><span data-stu-id="96a76-114">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="96a76-115">Escriba la palabra clave `With` , seguida de una lista de inicialización entre llaves.</span><span class="sxs-lookup"><span data-stu-id="96a76-115">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="96a76-116">En la lista de inicialización, incluya cada propiedad que desee inicializar y asígnele un valor inicial.</span><span class="sxs-lookup"><span data-stu-id="96a76-116">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="96a76-117">El nombre de la propiedad va precedido de un punto.</span><span class="sxs-lookup"><span data-stu-id="96a76-117">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="96a76-118">Puede inicializar uno o más miembros de la clase.</span><span class="sxs-lookup"><span data-stu-id="96a76-118">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="96a76-119">Como alternativa, puede declarar una nueva instancia de la clase y, a continuación, asignarle un valor.</span><span class="sxs-lookup"><span data-stu-id="96a76-119">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="96a76-120">En primer lugar, declare una instancia de `Student` :</span><span class="sxs-lookup"><span data-stu-id="96a76-120">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="96a76-121">Comience la creación de una instancia de de `Student` la manera normal.</span><span class="sxs-lookup"><span data-stu-id="96a76-121">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="96a76-122">Escriba `With` y, a continuación, un inicializador de objeto para inicializar uno o más miembros de la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="96a76-122">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="96a76-123">Puede simplificar la definición en el paso anterior si omite `As Student` .</span><span class="sxs-lookup"><span data-stu-id="96a76-123">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="96a76-124">Si lo hace, el compilador determina que `student3` es una instancia de mediante la `Student` inferencia de tipo de local.</span><span class="sxs-lookup"><span data-stu-id="96a76-124">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="96a76-125">Para obtener más información, vea [inferencia de tipo local](../variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="96a76-125">For more information, see [Local Type Inference](../variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a76-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96a76-126">See also</span></span>

- [<span data-ttu-id="96a76-127">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="96a76-127">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="96a76-128">Procedimiento para crear una lista de elementos</span><span class="sxs-lookup"><span data-stu-id="96a76-128">How to: Create a List of Items</span></span>](../../concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="96a76-129">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="96a76-129">Object Initializers: Named and Anonymous Types</span></span>](object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="96a76-130">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="96a76-130">Anonymous Types</span></span>](anonymous-types.md)
