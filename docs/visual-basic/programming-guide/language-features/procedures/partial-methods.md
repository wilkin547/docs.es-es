---
description: 'Más información acerca de: métodos parciales (Visual Basic)'
title: Métodos Partial
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: d9be2d318ca0da9e1197949c88db5332832bdb3b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466723"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="385af-103">Métodos parciales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="385af-103">Partial Methods (Visual Basic)</span></span>

<span data-ttu-id="385af-104">Los métodos parciales permiten a los desarrolladores insertar lógica personalizada en el código.</span><span class="sxs-lookup"><span data-stu-id="385af-104">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="385af-105">Normalmente, el código forma parte de una clase generada por el diseñador.</span><span class="sxs-lookup"><span data-stu-id="385af-105">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="385af-106">Los métodos parciales se definen en una clase parcial que se crea mediante un generador de código y se suelen usar para proporcionar una notificación de que se ha cambiado algo.</span><span class="sxs-lookup"><span data-stu-id="385af-106">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="385af-107">Permiten al desarrollador especificar el comportamiento personalizado en respuesta al cambio.</span><span class="sxs-lookup"><span data-stu-id="385af-107">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="385af-108">El diseñador del generador de código solo define la firma del método y una o varias llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="385af-108">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="385af-109">Después, los desarrolladores pueden proporcionar implementaciones para el método si quieren personalizar el comportamiento del código generado.</span><span class="sxs-lookup"><span data-stu-id="385af-109">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="385af-110">Cuando no se proporciona ninguna implementación, el compilador quita las llamadas al método, lo que da lugar a una sobrecarga de rendimiento adicional.</span><span class="sxs-lookup"><span data-stu-id="385af-110">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="385af-111">Declaración</span><span class="sxs-lookup"><span data-stu-id="385af-111">Declaration</span></span>  

 <span data-ttu-id="385af-112">El código generado marca la definición de un método parcial colocando la palabra clave `Partial` al principio de la línea de firma.</span><span class="sxs-lookup"><span data-stu-id="385af-112">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="385af-113">La definición debe cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="385af-113">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="385af-114">El método debe ser un `Sub` , no un `Function` .</span><span class="sxs-lookup"><span data-stu-id="385af-114">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="385af-115">El cuerpo del método debe dejarse vacío.</span><span class="sxs-lookup"><span data-stu-id="385af-115">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="385af-116">El modificador de acceso debe ser `Private` .</span><span class="sxs-lookup"><span data-stu-id="385af-116">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="385af-117">Implementación</span><span class="sxs-lookup"><span data-stu-id="385af-117">Implementation</span></span>  

 <span data-ttu-id="385af-118">La implementación consiste principalmente en rellenar el cuerpo del método parcial.</span><span class="sxs-lookup"><span data-stu-id="385af-118">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="385af-119">La implementación está normalmente en una clase parcial independiente de la definición y está escrita por un desarrollador que desea extender el código generado.</span><span class="sxs-lookup"><span data-stu-id="385af-119">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="385af-120">En el ejemplo anterior se duplica exactamente la firma en la declaración, pero son posibles las variaciones.</span><span class="sxs-lookup"><span data-stu-id="385af-120">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="385af-121">En concreto, se pueden agregar otros modificadores, como `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="385af-121">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="385af-122">Solo `Overrides` se permite un modificador.</span><span class="sxs-lookup"><span data-stu-id="385af-122">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="385af-123">Para obtener más información sobre los modificadores de método, vea [Sub Statement](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="385af-123">For more information about method modifiers, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="385af-124">Uso</span><span class="sxs-lookup"><span data-stu-id="385af-124">Use</span></span>  

 <span data-ttu-id="385af-125">Se llama a un método parcial como se llamaría a cualquier otro `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="385af-125">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="385af-126">Si se ha implementado el método, se evalúan los argumentos y se ejecuta el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="385af-126">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="385af-127">Sin embargo, recuerde que la implementación de un método parcial es opcional.</span><span class="sxs-lookup"><span data-stu-id="385af-127">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="385af-128">Si no se implementa el método, no se evalúa ninguna llamada a él y no se evalúan las expresiones que se pasan como argumentos al método.</span><span class="sxs-lookup"><span data-stu-id="385af-128">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="385af-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="385af-129">Example</span></span>  

 <span data-ttu-id="385af-130">En un archivo denominado product. Designer. VB, defina una `Product` clase que tenga una `Quantity` propiedad.</span><span class="sxs-lookup"><span data-stu-id="385af-130">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="385af-131">En un archivo denominado product. VB, proporcione una implementación para `QuantityChanged` .</span><span class="sxs-lookup"><span data-stu-id="385af-131">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="385af-132">Por último, en el método Main de un proyecto, declare una `Product` instancia de y proporcione un valor inicial para su `Quantity` propiedad.</span><span class="sxs-lookup"><span data-stu-id="385af-132">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="385af-133">Debería aparecer un cuadro de mensaje que muestra este mensaje:</span><span class="sxs-lookup"><span data-stu-id="385af-133">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="385af-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="385af-134">See also</span></span>

- [<span data-ttu-id="385af-135">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="385af-135">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="385af-136">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="385af-136">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="385af-137">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="385af-137">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="385af-138">Partial</span><span class="sxs-lookup"><span data-stu-id="385af-138">Partial</span></span>](../../../language-reference/modifiers/partial.md)
- [<span data-ttu-id="385af-139">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="385af-139">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="385af-140">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="385af-140">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
