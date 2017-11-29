---
title: "Métodos parciales (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ebedd6f8173e3c349240d24ddaf16e4841f67a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="6bef7-102">Métodos parciales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6bef7-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="6bef7-103">Los métodos parciales permiten a los desarrolladores insertar lógica personalizada en código.</span><span class="sxs-lookup"><span data-stu-id="6bef7-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="6bef7-104">Normalmente, el código es parte de una clase generada por el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6bef7-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="6bef7-105">Métodos parciales se definen en una clase parcial que se crea un generador de código y se suelen usar para proporcionar una notificación que algo ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="6bef7-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="6bef7-106">Le permiten al programador especificar un comportamiento personalizado en respuesta al cambio.</span><span class="sxs-lookup"><span data-stu-id="6bef7-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="6bef7-107">El diseñador del generador de código define sólo la firma del método y una o más llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="6bef7-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="6bef7-108">Los desarrolladores pueden proporcionar, a continuación, las implementaciones del método si desea personalizar el comportamiento del código generado.</span><span class="sxs-lookup"><span data-stu-id="6bef7-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="6bef7-109">Cuando no se proporciona ninguna implementación, se quitan las llamadas al método por el compilador, lo que da lugar ninguna sobrecarga de rendimiento adicional.</span><span class="sxs-lookup"><span data-stu-id="6bef7-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="6bef7-110">Declaración</span><span class="sxs-lookup"><span data-stu-id="6bef7-110">Declaration</span></span>  
 <span data-ttu-id="6bef7-111">El código generado marca la definición de un método parcial mediante la colocación de la palabra clave `Partial` al principio de la línea de firma.</span><span class="sxs-lookup"><span data-stu-id="6bef7-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="6bef7-112">La definición debe cumplir las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6bef7-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="6bef7-113">El método debe ser un `Sub`, no un `Function`.</span><span class="sxs-lookup"><span data-stu-id="6bef7-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="6bef7-114">El cuerpo del método se debe dejar vacío.</span><span class="sxs-lookup"><span data-stu-id="6bef7-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="6bef7-115">El modificador de acceso debe ser `Private`.</span><span class="sxs-lookup"><span data-stu-id="6bef7-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="6bef7-116">Implementación</span><span class="sxs-lookup"><span data-stu-id="6bef7-116">Implementation</span></span>  
 <span data-ttu-id="6bef7-117">La implementación consiste principalmente en rellenar en el cuerpo del método parcial.</span><span class="sxs-lookup"><span data-stu-id="6bef7-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="6bef7-118">La implementación está normalmente en una clase parcial independiente de la definición y se escribe por un desarrollador que desea ampliar el código generado.</span><span class="sxs-lookup"><span data-stu-id="6bef7-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="6bef7-119">El ejemplo anterior duplica la firma en la declaración exactamente, pero son posibles las variaciones.</span><span class="sxs-lookup"><span data-stu-id="6bef7-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="6bef7-120">En concreto, otros modificadores pueden agregarse, como `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="6bef7-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="6bef7-121">Solo un `Overrides` se permite el modificador.</span><span class="sxs-lookup"><span data-stu-id="6bef7-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="6bef7-122">Para obtener más información acerca de los modificadores de método, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6bef7-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="6bef7-123">Uso</span><span class="sxs-lookup"><span data-stu-id="6bef7-123">Use</span></span>  
 <span data-ttu-id="6bef7-124">Se llama a un método parcial como llamaría a cualquier otro `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6bef7-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="6bef7-125">Si el método se ha implementado, se evalúan los argumentos y se ejecuta el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="6bef7-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="6bef7-126">Sin embargo, recuerde que implementa un método parcial es opcional.</span><span class="sxs-lookup"><span data-stu-id="6bef7-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="6bef7-127">Si no se implementa el método, una llamada a éste no tiene ningún efecto y no se evalúan las expresiones pasadas como argumentos al método.</span><span class="sxs-lookup"><span data-stu-id="6bef7-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bef7-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6bef7-128">Example</span></span>  
 <span data-ttu-id="6bef7-129">En un archivo denominado Product.Designer.vb, defina un `Product` clase que tiene un `Quantity` propiedad.</span><span class="sxs-lookup"><span data-stu-id="6bef7-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 <span data-ttu-id="6bef7-130">En un archivo denominado Product.vb, proporcione una implementación para `QuantityChanged`.</span><span class="sxs-lookup"><span data-stu-id="6bef7-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 <span data-ttu-id="6bef7-131">Por último, en el método Main de un proyecto, declare un `Product` instancia y proporcionar un valor inicial para su `Quantity` propiedad.</span><span class="sxs-lookup"><span data-stu-id="6bef7-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 <span data-ttu-id="6bef7-132">Debe aparecer un cuadro de mensaje que muestra este mensaje:</span><span class="sxs-lookup"><span data-stu-id="6bef7-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="6bef7-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bef7-133">See Also</span></span>  
 [<span data-ttu-id="6bef7-134">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6bef7-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="6bef7-135">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="6bef7-135">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="6bef7-136">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="6bef7-136">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="6bef7-137">Partial</span><span class="sxs-lookup"><span data-stu-id="6bef7-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="6bef7-138">Generación de código en LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6bef7-138">Code Generation in LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb399400)  
 [<span data-ttu-id="6bef7-139">Agregar lógica de negocios utilizando métodos parciales</span><span class="sxs-lookup"><span data-stu-id="6bef7-139">Adding Business Logic By Using Partial Methods</span></span>](https://msdn.microsoft.com/library/bb546176)
