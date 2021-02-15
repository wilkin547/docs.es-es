---
description: 'Más información sobre: tipos genéricos en Visual Basic (Visual Basic)'
title: Tipos genéricos
ms.date: 07/20/2015
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
ms.openlocfilehash: 1164513825240b1e83fbce2aeb6478430b0bc250
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428550"
---
# <a name="generic-types-in-visual-basic-visual-basic"></a><span data-ttu-id="08c71-103">Tipos genéricos en Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08c71-103">Generic Types in Visual Basic (Visual Basic)</span></span>

<span data-ttu-id="08c71-104">Un *tipo genérico* es un elemento de programación único que se adapta para ejecutar la misma funcionalidad para distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="08c71-104">A *generic type* is a single programming element that adapts to perform the same functionality for a variety of data types.</span></span> <span data-ttu-id="08c71-105">Cuando se define una clase o un procedimiento genérico, no es necesario definir una versión independiente para cada tipo de datos para el que quiera ejecutar esa funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="08c71-105">When you define a generic class or procedure, you do not have to define a separate version for each data type for which you might want to perform that functionality.</span></span>  
  
 <span data-ttu-id="08c71-106">Una analogía es un juego de destornilladores con puntas extraíbles.</span><span class="sxs-lookup"><span data-stu-id="08c71-106">An analogy is a screwdriver set with removable heads.</span></span> <span data-ttu-id="08c71-107">Inspeccione el tornillo que quiere roscar y seleccione la punta adecuada (plana, de cruz o de estrella).</span><span class="sxs-lookup"><span data-stu-id="08c71-107">You inspect the screw you need to turn and select the correct head for that screw (slotted, crossed, starred).</span></span> <span data-ttu-id="08c71-108">Una vez insertada la punta correcta en el mango del destornillador, realiza la misma función exacta con el destornillador, es decir, roscar el tornillo.</span><span class="sxs-lookup"><span data-stu-id="08c71-108">Once you insert the correct head in the screwdriver handle, you perform the exact same function with the screwdriver, namely turning the screw.</span></span>  
  
 ![Diagrama de un conjunto de destornilladores con distintos cabezales.](./media/generic-types/generic-screwdriver-set.gif)  
  
 <span data-ttu-id="08c71-110">Al definir un tipo genérico, lo puede parametrizar con uno o más tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="08c71-110">When you define a generic type, you parameterize it with one or more data types.</span></span> <span data-ttu-id="08c71-111">Esto permite que el código que los usa se adapte los tipos de datos a sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="08c71-111">This allows the using code to tailor the data types to its requirements.</span></span> <span data-ttu-id="08c71-112">Su código puede declarar varios elementos de programación diferentes a partir del elemento genérico y cada uno de ellos actúa en un conjunto distinto de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="08c71-112">Your code can declare several different programming elements from the generic element, each one acting on a different set of data types.</span></span> <span data-ttu-id="08c71-113">Pero todos los elementos declarados funcionan con la misma lógica, independientemente de los tipos de datos que usen.</span><span class="sxs-lookup"><span data-stu-id="08c71-113">But the declared elements all perform the identical logic, no matter what data types they are using.</span></span>  
  
 <span data-ttu-id="08c71-114">Por ejemplo, puede que quiera crear y usar una clase de cola que funcione en un tipo de datos concreto, como `String`.</span><span class="sxs-lookup"><span data-stu-id="08c71-114">For example, you might want to create and use a queue class that operates on a specific data type such as `String`.</span></span> <span data-ttu-id="08c71-115">Puede declarar esta clase desde <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="08c71-115">You can declare such a class from <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#1)]  
  
 <span data-ttu-id="08c71-116">Ahora puede usar `stringQ` para trabajar exclusivamente con valores `String` .</span><span class="sxs-lookup"><span data-stu-id="08c71-116">You can now use `stringQ` to work exclusively with `String` values.</span></span> <span data-ttu-id="08c71-117">Dado que `stringQ` es específico de `String` en lugar de generalizarse para los valores `Object` , no dispone de enlace en tiempo de ejecución ni conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="08c71-117">Because `stringQ` is specific for `String` instead of being generalized for `Object` values, you do not have late binding or type conversion.</span></span> <span data-ttu-id="08c71-118">Esto ahorra tiempo de ejecución y reduce los errores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="08c71-118">This saves execution time and reduces run-time errors.</span></span>  
  
 <span data-ttu-id="08c71-119">Para obtener más información sobre el uso de un tipo genérico, vea [How to: Use a Generic Class](how-to-use-a-generic-class.md).</span><span class="sxs-lookup"><span data-stu-id="08c71-119">For more information on using a generic type, see [How to: Use a Generic Class](how-to-use-a-generic-class.md).</span></span>  
  
## <a name="example-of-a-generic-class"></a><span data-ttu-id="08c71-120">Ejemplo de una clase genérica</span><span class="sxs-lookup"><span data-stu-id="08c71-120">Example of a Generic Class</span></span>  

 <span data-ttu-id="08c71-121">En el ejemplo siguiente se muestra un esquema de definición de una clase genérica.</span><span class="sxs-lookup"><span data-stu-id="08c71-121">The following example shows a skeleton definition of a generic class.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#2)]  
  
 <span data-ttu-id="08c71-122">En el esquema anterior, `t` es un *parámetro de tipo*, es decir, un marcador de posición para un tipo de datos proporcionado al declarar la clase.</span><span class="sxs-lookup"><span data-stu-id="08c71-122">In the preceding skeleton, `t` is a *type parameter*, that is, a placeholder for a data type that you supply when you declare the class.</span></span> <span data-ttu-id="08c71-123">En otro lugar del código, puede declarar distintas versiones de `classHolder` proporcionando diversos tipos de datos para `t`.</span><span class="sxs-lookup"><span data-stu-id="08c71-123">Elsewhere in your code, you can declare various versions of `classHolder` by supplying various data types for `t`.</span></span> <span data-ttu-id="08c71-124">En el ejemplo siguiente se muestran dos declaraciones de este tipo.</span><span class="sxs-lookup"><span data-stu-id="08c71-124">The following example shows two such declarations.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#3)]  
  
 <span data-ttu-id="08c71-125">Las instrucciones anteriores declaran *clases construidas*, en las que un tipo específico reemplaza el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="08c71-125">The preceding statements declare *constructed classes*, in which a specific type replaces the type parameter.</span></span> <span data-ttu-id="08c71-126">Este reemplazo se propaga por todo el código en la clase construida.</span><span class="sxs-lookup"><span data-stu-id="08c71-126">This replacement is propagated throughout the code within the constructed class.</span></span> <span data-ttu-id="08c71-127">En el ejemplo siguiente se muestra el aspecto del procedimiento `processNewItem` en `integerClass`.</span><span class="sxs-lookup"><span data-stu-id="08c71-127">The following example shows what the `processNewItem` procedure looks like in `integerClass`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#4)]  
  
 <span data-ttu-id="08c71-128">Para obtener un ejemplo más completo, vea [Cómo: definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](how-to-define-a-class-that-can-provide-identical-functionality.md).</span><span class="sxs-lookup"><span data-stu-id="08c71-128">For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](how-to-define-a-class-that-can-provide-identical-functionality.md).</span></span>  
  
## <a name="eligible-programming-elements"></a><span data-ttu-id="08c71-129">Elementos de programación válidos</span><span class="sxs-lookup"><span data-stu-id="08c71-129">Eligible Programming Elements</span></span>  

 <span data-ttu-id="08c71-130">Puede definir y usar clases genéricas, estructuras, interfaces, procedimientos y delegados.</span><span class="sxs-lookup"><span data-stu-id="08c71-130">You can define and use generic classes, structures, interfaces, procedures, and delegates.</span></span> <span data-ttu-id="08c71-131">Tenga en cuenta que el .NET Framework define varias clases, estructuras e interfaces genéricas que representan los elementos genéricos que se usan habitualmente.</span><span class="sxs-lookup"><span data-stu-id="08c71-131">Note that the .NET Framework defines several generic classes, structures, and interfaces that represent commonly used generic elements.</span></span> <span data-ttu-id="08c71-132">El espacio de nombres <xref:System.Collections.Generic?displayProperty=nameWithType> proporciona diccionarios, listas, colas y pilas.</span><span class="sxs-lookup"><span data-stu-id="08c71-132">The <xref:System.Collections.Generic?displayProperty=nameWithType> namespace provides dictionaries, lists, queues, and stacks.</span></span> <span data-ttu-id="08c71-133">Antes de definir su propio elemento genérico, vea si ya está disponible en <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08c71-133">Before defining your own generic element, see if it is already available in <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="08c71-134">Los procedimientos no son tipos, pero puede definir y usar procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="08c71-134">Procedures are not types, but you can define and use generic procedures.</span></span> <span data-ttu-id="08c71-135">Vea [Generic Procedures in Visual Basic](generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="08c71-135">See [Generic Procedures in Visual Basic](generic-procedures.md).</span></span>  
  
## <a name="advantages-of-generic-types"></a><span data-ttu-id="08c71-136">Ventajas de los tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="08c71-136">Advantages of Generic Types</span></span>  

 <span data-ttu-id="08c71-137">Un tipo genérico sirve como base para declarar varios elementos de programación diferentes, cada uno de los cuales actúa en un tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="08c71-137">A generic type serves as a basis for declaring several different programming elements, each of which operates on a specific data type.</span></span> <span data-ttu-id="08c71-138">Las alternativas a un tipo genérico son:</span><span class="sxs-lookup"><span data-stu-id="08c71-138">The alternatives to a generic type are:</span></span>  
  
1. <span data-ttu-id="08c71-139">Un tipo único que actúe en el tipo de datos `Object` .</span><span class="sxs-lookup"><span data-stu-id="08c71-139">A single type operating on the `Object` data type.</span></span>  
  
2. <span data-ttu-id="08c71-140">Un conjunto de versiones *específicas* del tipo del tipo, cada versión codificada individualmente y funcionando en un tipo de datos concreto como `String` , `Integer` o un tipo definido por el usuario como `customer` .</span><span class="sxs-lookup"><span data-stu-id="08c71-140">A set of *type-specific* versions of the type, each version individually coded and operating on one specific data type such as `String`, `Integer`, or a user-defined type such as `customer`.</span></span>  
  
 <span data-ttu-id="08c71-141">Un tipo genérico tiene las ventajas siguientes sobre estas alternativas:</span><span class="sxs-lookup"><span data-stu-id="08c71-141">A generic type has the following advantages over these alternatives:</span></span>  
  
- <span data-ttu-id="08c71-142">**Seguridad de tipos.**</span><span class="sxs-lookup"><span data-stu-id="08c71-142">**Type Safety.**</span></span> <span data-ttu-id="08c71-143">Los tipos genéricos fuerzan la comprobación de tipos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="08c71-143">Generic types enforce compile-time type checking.</span></span> <span data-ttu-id="08c71-144">Los tipos basados en `Object` aceptan cualquier tipo de datos; debe escribir código para comprobar si un tipo de datos de entrada es aceptable.</span><span class="sxs-lookup"><span data-stu-id="08c71-144">Types based on `Object` accept any data type, and you must write code to check whether an input data type is acceptable.</span></span> <span data-ttu-id="08c71-145">Con los tipos genéricos, el compilador puede detectar errores de coincidencia de tipo antes del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="08c71-145">With generic types, the compiler can catch type mismatches before run time.</span></span>  
  
- <span data-ttu-id="08c71-146">**Rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="08c71-146">**Performance.**</span></span> <span data-ttu-id="08c71-147">No es necesario que los tipos genéricos apliquen la conversión *boxing* y *unboxinging* a los datos, ya que cada uno está diseñado para un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="08c71-147">Generic types do not have to *box* and *unbox* data, because each one is specialized for one data type.</span></span> <span data-ttu-id="08c71-148">Las operaciones basadas en `Object` deben aplicar la conversión boxing a los tipos de datos de entrada para convertirlos a `Object` y aplicar la conversión unboxing a los datos destinados a la salida.</span><span class="sxs-lookup"><span data-stu-id="08c71-148">Operations based on `Object` must box input data types to convert them to `Object` and unbox data destined for output.</span></span> <span data-ttu-id="08c71-149">La conversión boxing y la conversión unboxing reducen el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="08c71-149">Boxing and unboxing reduce performance.</span></span>  
  
     <span data-ttu-id="08c71-150">Los tipos basados en `Object` también se enlazan en tiempo de ejecución, lo que significa que el acceso a sus miembros requiere código adicional en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="08c71-150">Types based on `Object` are also late-bound, which means that accessing their members requires extra code at run time.</span></span> <span data-ttu-id="08c71-151">Esto también reduce el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="08c71-151">This also reduces performance.</span></span>  
  
- <span data-ttu-id="08c71-152">**Consolidación del código.**</span><span class="sxs-lookup"><span data-stu-id="08c71-152">**Code Consolidation.**</span></span> <span data-ttu-id="08c71-153">El código de un tipo genérico debe definirse una sola vez.</span><span class="sxs-lookup"><span data-stu-id="08c71-153">The code in a generic type has to be defined only once.</span></span> <span data-ttu-id="08c71-154">Un conjunto de versiones específicas del tipo de un tipo debe replicar el mismo código en cada versión, a excepción del tipo de datos específico de la versión.</span><span class="sxs-lookup"><span data-stu-id="08c71-154">A set of type-specific versions of a type must replicate the same code in each version, with the only difference being the specific data type for that version.</span></span> <span data-ttu-id="08c71-155">Con los tipos genéricos, las versiones específicas del tipo se generan a partir del tipo genérico original.</span><span class="sxs-lookup"><span data-stu-id="08c71-155">With generic types, the type-specific versions are all generated from the original generic type.</span></span>  
  
- <span data-ttu-id="08c71-156">**Reutilización del código.**</span><span class="sxs-lookup"><span data-stu-id="08c71-156">**Code Reuse.**</span></span> <span data-ttu-id="08c71-157">El código que no depende de un tipo de datos determinado se puede reutilizar con distintos tipos de datos si es genérico.</span><span class="sxs-lookup"><span data-stu-id="08c71-157">Code that does not depend on a particular data type can be reused with various data types if it is generic.</span></span> <span data-ttu-id="08c71-158">A menudo se puede reutilizar incluso con un tipo de datos no previsto originalmente.</span><span class="sxs-lookup"><span data-stu-id="08c71-158">You can often reuse it even with a data type that you did not originally predict.</span></span>  
  
- <span data-ttu-id="08c71-159">**Compatibilidad con IDE.**</span><span class="sxs-lookup"><span data-stu-id="08c71-159">**IDE Support.**</span></span> <span data-ttu-id="08c71-160">Si usa un tipo construido declarado a partir de un tipo genérico, el entorno de desarrollo integrado (IDE) puede proporcionarle más soporte mientras desarrolla el código.</span><span class="sxs-lookup"><span data-stu-id="08c71-160">When you use a constructed type declared from a generic type, the integrated development environment (IDE) can give you more support while you are developing your code.</span></span> <span data-ttu-id="08c71-161">Por ejemplo, IntelliSense puede mostrarle las opciones específicas del tipo de un argumento para un constructor o un método.</span><span class="sxs-lookup"><span data-stu-id="08c71-161">For example, IntelliSense can show you the type-specific options for an argument to a constructor or method.</span></span>  
  
- <span data-ttu-id="08c71-162">**Algoritmos genéricos.**</span><span class="sxs-lookup"><span data-stu-id="08c71-162">**Generic Algorithms.**</span></span> <span data-ttu-id="08c71-163">Los algoritmos abstractos que son independientes del tipo son buenos candidatos para los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="08c71-163">Abstract algorithms that are type-independent are good candidates for generic types.</span></span> <span data-ttu-id="08c71-164">Por ejemplo, un procedimiento genérico que ordena los elementos mediante la interfaz <xref:System.IComparable> puede usarse con cualquier tipo de datos que implemente <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="08c71-164">For example, a generic procedure that sorts items using the <xref:System.IComparable> interface can be used with any data type that implements <xref:System.IComparable>.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="08c71-165">Restricciones</span><span class="sxs-lookup"><span data-stu-id="08c71-165">Constraints</span></span>  

 <span data-ttu-id="08c71-166">Aunque el código de una definición de tipo genérico debe ser tan independiente del tipo como sea posible, puede que tenga que requerir una funcionalidad concreta de cualquier tipo de datos proporcionado a su tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="08c71-166">Although the code in a generic type definition should be as type-independent as possible, you might need to require a certain capability of any data type supplied to your generic type.</span></span> <span data-ttu-id="08c71-167">Por ejemplo, si desea comparar dos elementos con el fin de ordenarlos o intercalarlos, su tipo de datos debe implementar la interfaz <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="08c71-167">For example, if you want to compare two items for the purpose of sorting or collating, their data type must implement the <xref:System.IComparable> interface.</span></span> <span data-ttu-id="08c71-168">Para imponer este requisito, puede agregar una *restricción* al parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="08c71-168">You can enforce this requirement by adding a *constraint* to the type parameter.</span></span>  
  
### <a name="example-of-a-constraint"></a><span data-ttu-id="08c71-169">Ejemplo de una restricción</span><span class="sxs-lookup"><span data-stu-id="08c71-169">Example of a Constraint</span></span>  

 <span data-ttu-id="08c71-170">En el ejemplo siguiente se muestra un esquema de definición de una clase con una restricción que requiere que el argumento de tipo implemente <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="08c71-170">The following example shows a skeleton definition of a class with a constraint that requires the type argument to implement <xref:System.IComparable>.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#5)]  
  
 <span data-ttu-id="08c71-171">Si el código subsiguiente intenta construir una clase a partir de `itemManager` proporcionando un tipo que no implemente <xref:System.IComparable>, el compilador indicará un error.</span><span class="sxs-lookup"><span data-stu-id="08c71-171">If subsequent code attempts to construct a class from `itemManager` supplying a type that does not implement <xref:System.IComparable>, the compiler signals an error.</span></span>  
  
### <a name="types-of-constraints"></a><span data-ttu-id="08c71-172">Tipos de restricciones</span><span class="sxs-lookup"><span data-stu-id="08c71-172">Types of Constraints</span></span>  

 <span data-ttu-id="08c71-173">La restricción puede especificar los requisitos siguientes en cualquier combinación:</span><span class="sxs-lookup"><span data-stu-id="08c71-173">Your constraint can specify the following requirements in any combination:</span></span>  
  
- <span data-ttu-id="08c71-174">El argumento de tipo debe implementar una o varias interfaces</span><span class="sxs-lookup"><span data-stu-id="08c71-174">The type argument must implement one or more interfaces</span></span>  
  
- <span data-ttu-id="08c71-175">El argumento de tipo debe ser del tipo de una clase como máximo, o bien heredarse a lo sumo de una clase.</span><span class="sxs-lookup"><span data-stu-id="08c71-175">The type argument must be of the type of, or inherit from, at most one class</span></span>  
  
- <span data-ttu-id="08c71-176">El argumento de tipo debe exponer un constructor sin parámetros accesible para el código que crea objetos a partir de él.</span><span class="sxs-lookup"><span data-stu-id="08c71-176">The type argument must expose a parameterless constructor accessible to the code that creates objects from it</span></span>  
  
- <span data-ttu-id="08c71-177">El argumento de tipo debe ser un *tipo de referencia* o debe ser un *tipo de valor*</span><span class="sxs-lookup"><span data-stu-id="08c71-177">The type argument must be a *reference type*, or it must be a *value type*</span></span>  
  
 <span data-ttu-id="08c71-178">Si necesita imponer más que un requisito, use una *lista de restricciones* separadas por comas entre llaves (`{ }`).</span><span class="sxs-lookup"><span data-stu-id="08c71-178">If you need to impose more than one requirement, you use a comma-separated *constraint list* inside braces (`{ }`).</span></span> <span data-ttu-id="08c71-179">Para requerir un constructor accesible, incluya la palabra clave [New Operator](../../../language-reference/operators/new-operator.md) en la lista.</span><span class="sxs-lookup"><span data-stu-id="08c71-179">To require an accessible constructor, you include the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the list.</span></span> <span data-ttu-id="08c71-180">Para requerir un tipo de referencia, incluya la palabra clave `Class` ; para requerir un tipo de valor, incluya la palabra clave `Structure` .</span><span class="sxs-lookup"><span data-stu-id="08c71-180">To require a reference type, you include the `Class` keyword; to require a value type, you include the `Structure` keyword.</span></span>  
  
 <span data-ttu-id="08c71-181">Para más información sobre las restricciones, vea [Type List](../../../language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="08c71-181">For more information on constraints, see [Type List](../../../language-reference/statements/type-list.md).</span></span>  
  
### <a name="example-of-multiple-constraints"></a><span data-ttu-id="08c71-182">Ejemplo de varias restricciones</span><span class="sxs-lookup"><span data-stu-id="08c71-182">Example of Multiple Constraints</span></span>  

 <span data-ttu-id="08c71-183">En el ejemplo siguiente se muestra un esquema de definición de una clase genérica con una lista de restricciones en el parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="08c71-183">The following example shows a skeleton definition of a generic class with a constraint list on the type parameter.</span></span> <span data-ttu-id="08c71-184">En el código que crea una instancia de esta clase, el argumento de tipo debe implementar ambas interfaces <xref:System.IComparable> y <xref:System.IDisposable> , ser un tipo de referencia y exponer un constructor sin parámetros accesible.</span><span class="sxs-lookup"><span data-stu-id="08c71-184">In the code that creates an instance of this class, the type argument must implement both the <xref:System.IComparable> and <xref:System.IDisposable> interfaces, be a reference type, and expose an accessible parameterless constructor.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#6)]  
  
## <a name="important-terms"></a><span data-ttu-id="08c71-185">Condiciones importantes</span><span class="sxs-lookup"><span data-stu-id="08c71-185">Important Terms</span></span>  

 <span data-ttu-id="08c71-186">Los tipos genéricos introducen y usan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="08c71-186">Generic types introduce and use the following terms:</span></span>  
  
- <span data-ttu-id="08c71-187">*Tipo genérico*.</span><span class="sxs-lookup"><span data-stu-id="08c71-187">*Generic Type*.</span></span> <span data-ttu-id="08c71-188">Definición de clase, estructura, interfaz, procedimiento o delegado para la que proporciona al menos un tipo de datos cuando la declara.</span><span class="sxs-lookup"><span data-stu-id="08c71-188">A definition of a class, structure, interface, procedure, or delegate for which you supply at least one data type when you declare it.</span></span>  
  
- <span data-ttu-id="08c71-189">*Parámetro de tipo*.</span><span class="sxs-lookup"><span data-stu-id="08c71-189">*Type Parameter*.</span></span> <span data-ttu-id="08c71-190">En una definición de tipo genérico, marcador de posición para un tipo de datos que proporciona al declarar el tipo.</span><span class="sxs-lookup"><span data-stu-id="08c71-190">In a generic type definition, a placeholder for a data type you supply when you declare the type.</span></span>  
  
- <span data-ttu-id="08c71-191">*Argumento de tipo*.</span><span class="sxs-lookup"><span data-stu-id="08c71-191">*Type Argument*.</span></span> <span data-ttu-id="08c71-192">Tipo de datos específico que reemplaza un parámetro de tipo cuando declara un tipo construido a partir de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="08c71-192">A specific data type that replaces a type parameter when you declare a constructed type from a generic type.</span></span>  
  
- <span data-ttu-id="08c71-193">*Restricción*.</span><span class="sxs-lookup"><span data-stu-id="08c71-193">*Constraint*.</span></span> <span data-ttu-id="08c71-194">Condición en un parámetro de tipo que restringe el argumento de tipo puede proporcionar para este.</span><span class="sxs-lookup"><span data-stu-id="08c71-194">A condition on a type parameter that restricts the type argument you can supply for it.</span></span> <span data-ttu-id="08c71-195">Una restricción puede requerir que el argumento de tipo implemente una interfaz determinada, sea de una clase concreta o se herede de esta, tenga un constructor sin parámetros accesible o sea un tipo de referencia o un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="08c71-195">A constraint can require that the type argument must implement a particular interface, be or inherit from a particular class, have an accessible parameterless constructor, or be a reference type or a value type.</span></span> <span data-ttu-id="08c71-196">Puede combinar estas restricciones, pero puede especificar una clase como máximo.</span><span class="sxs-lookup"><span data-stu-id="08c71-196">You can combine these constraints, but you can specify at most one class.</span></span>  
  
- <span data-ttu-id="08c71-197">*Tipo construido*.</span><span class="sxs-lookup"><span data-stu-id="08c71-197">*Constructed Type*.</span></span> <span data-ttu-id="08c71-198">Clase, estructura, interfaz, procedimiento o delegado que se declara a partir de un tipo genérico proporcionando argumentos de tipo para sus parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="08c71-198">A class, structure, interface, procedure, or delegate declared from a generic type by supplying type arguments for its type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c71-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08c71-199">See also</span></span>

- [<span data-ttu-id="08c71-200">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="08c71-200">Data Types</span></span>](index.md)
- [<span data-ttu-id="08c71-201">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="08c71-201">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="08c71-202">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="08c71-202">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="08c71-203">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="08c71-203">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="08c71-204">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="08c71-204">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="08c71-205">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="08c71-205">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="08c71-206">De</span><span class="sxs-lookup"><span data-stu-id="08c71-206">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="08c71-207">Aplicar</span><span class="sxs-lookup"><span data-stu-id="08c71-207">As</span></span>](../../../language-reference/statements/as-clause.md)
- [<span data-ttu-id="08c71-208">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="08c71-208">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="08c71-209">Covarianza y contravarianza</span><span class="sxs-lookup"><span data-stu-id="08c71-209">Covariance and Contravariance</span></span>](../../concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="08c71-210">Iteradores</span><span class="sxs-lookup"><span data-stu-id="08c71-210">Iterators</span></span>](../../concepts/iterators.md)
