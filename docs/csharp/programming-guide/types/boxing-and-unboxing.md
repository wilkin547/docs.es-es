---
title: "Conversión boxing y unboxing (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 893ef47c5e7522581b5d02489100942e47023a63
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="d4cb0-102">Conversión boxing y unboxing (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d4cb0-102">Boxing and Unboxing (C# Programming Guide)</span></span>
<span data-ttu-id="d4cb0-103">La conversión boxing es el proceso de convertir un [tipo de valor](../../../csharp/language-reference/keywords/value-types.md) en el tipo `object` o en cualquier tipo de interfaz implementado por este tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-103">Boxing is the process of converting a [value type](../../../csharp/language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="d4cb0-104">Cuando CLR aplica la conversión boxing a un tipo de valor, ajusta el valor dentro de una clase System.Object y lo almacena en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-104">When the CLR boxes a value type, it wraps the value inside a System.Object and stores it on the managed heap.</span></span> <span data-ttu-id="d4cb0-105">La conversión unboxing extrae el tipo de valor del objeto.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="d4cb0-106">La conversión boxing es implícita y la conversión unboxing es explícita.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="d4cb0-107">El concepto de conversión boxing y unboxing es la base de la vista unificada del sistema de tipos de C#, en el que un valor de cualquier tipo se puede tratar como objeto.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>  
  
 <span data-ttu-id="d4cb0-108">En el ejemplo siguiente, se aplica *conversión boxing* a la variable de entero `i` y esta se asigna al objeto `o`.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#14](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_1.cs)]  
  
 <span data-ttu-id="d4cb0-109">Luego se puede aplicar conversión unboxing al objeto `o` y asignarlo a la variable de entero `i`:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-109">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>  
  
 [!code-csharp[csProgGuideTypes#15](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_2.cs)]  
  
 <span data-ttu-id="d4cb0-110">En los ejemplos siguientes se muestra cómo usar la conversión boxing en C#.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-110">The following examples illustrate how boxing is used in C#.</span></span>  
  
 [!code-csharp[csProgGuideTypes#47](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_3.cs)]  
  
## <a name="performance"></a><span data-ttu-id="d4cb0-111">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="d4cb0-111">Performance</span></span>  
 <span data-ttu-id="d4cb0-112">Con relación a las asignaciones simples, las conversiones boxing y unboxing son procesos que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-112">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="d4cb0-113">Cuando se aplica la conversión boxing a un tipo de valor, se debe asignar y construir un objeto completamente nuevo.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-113">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="d4cb0-114">En menor grado, la conversión de tipos requerida para aplicar la conversión unboxing también es costosa.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-114">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="d4cb0-115">Para más información, vea [Rendimiento](https://msdn.microsoft.com/library/ms173196(VS.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="d4cb0-115">For more information, see [Performance](https://msdn.microsoft.com/library/ms173196(VS.110).aspx).</span></span>  
  
## <a name="boxing"></a><span data-ttu-id="d4cb0-116">Boxing</span><span class="sxs-lookup"><span data-stu-id="d4cb0-116">Boxing</span></span>  
 <span data-ttu-id="d4cb0-117">La conversión boxing se utiliza para almacenar tipos de valor en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-117">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="d4cb0-118">La conversión boxing es una conversión implícita de un [tipo de valor](../../../csharp/language-reference/keywords/value-types.md) en el tipo `object` o en cualquier tipo de interfaz implementado por este tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-118">Boxing is an implicit conversion of a [value type](../../../csharp/language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="d4cb0-119">Al aplicar la conversión boxing a un tipo de valor se asigna una instancia de objeto en el montón y se copia el valor en el nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-119">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>  
  
 <span data-ttu-id="d4cb0-120">Considere la siguiente declaración de una variable de tipo de valor:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-120">Consider the following declaration of a value-type variable:</span></span>  
  
 [!code-csharp[csProgGuideTypes#17](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_4.cs)]  
  
 <span data-ttu-id="d4cb0-121">La siguiente instrucción aplica implícitamente la operación de conversión boxing en la variable `i`:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-121">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>  
  
 [!code-csharp[csProgGuideTypes#18](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_5.cs)]  
  
 <span data-ttu-id="d4cb0-122">El resultado de esta instrucción es crear una referencia de objeto `o` en la pila que hace referencia a un valor del tipo `int` en el montón.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-122">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="d4cb0-123">Este valor es una copia del tipo de valor asignado a la variable `i`.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-123">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="d4cb0-124">La diferencia entre las dos variables, `i` y `o`, se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-124">The difference between the two variables, `i` and `o`, is illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="d4cb0-125">![Gráfico BoxingConversion](../../../csharp/programming-guide/types/media/vcboxingconversion.gif "vcBoxingConversion")</span><span class="sxs-lookup"><span data-stu-id="d4cb0-125">![BoxingConversion graphic](../../../csharp/programming-guide/types/media/vcboxingconversion.gif "vcBoxingConversion")</span></span>  
<span data-ttu-id="d4cb0-126">Conversión boxing</span><span class="sxs-lookup"><span data-stu-id="d4cb0-126">Boxing Conversion</span></span>  
  
 <span data-ttu-id="d4cb0-127">También es posible realizar la conversión boxing de manera explícita, tal como se muestra en el ejemplo siguiente, pero esta nunca es necesaria:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-127">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>  
  
 [!code-csharp[csProgGuideTypes#19](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_6.cs)]  
  
## <a name="description"></a><span data-ttu-id="d4cb0-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4cb0-128">Description</span></span>  
 <span data-ttu-id="d4cb0-129">Este ejemplo convierte una variable de entero `i` en un objeto `o` mediante la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-129">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="d4cb0-130">A continuación, el valor almacenado en la variable `i` se cambia de `123` a `456`.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-130">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="d4cb0-131">El ejemplo muestra que el tipo de valor original y el objeto al que se ha aplicado la conversión boxing usan ubicaciones de memoria independientes y, por consiguiente, pueden almacenar valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-131">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4cb0-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4cb0-132">Example</span></span>  
 [!code-csharp[csProgGuideTypes#16](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_7.cs)]  
  
## <a name="unboxing"></a><span data-ttu-id="d4cb0-133">Conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="d4cb0-133">Unboxing</span></span>  
 <span data-ttu-id="d4cb0-134">La conversión unboxing es una conversión explícita del tipo `object` en un [tipo de valor](../../../csharp/language-reference/keywords/value-types.md) o de un tipo de interfaz en un tipo de valor que implementa la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-134">Unboxing is an explicit conversion from the type `object` to a [value type](../../../csharp/language-reference/keywords/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="d4cb0-135">Una operación de conversión unboxing consiste en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-135">An unboxing operation consists of:</span></span>  
  
-   <span data-ttu-id="d4cb0-136">Comprobar la instancia de objeto para asegurarse de que se trata de un valor de conversión boxing del tipo de valor dado.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-136">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>  
  
-   <span data-ttu-id="d4cb0-137">Copiar el valor de la instancia en la variable de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-137">Copying the value from the instance into the value-type variable.</span></span>  
  
 <span data-ttu-id="d4cb0-138">Las siguientes instrucciones muestran las operaciones de conversión boxing y unboxing:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-138">The following statements demonstrate both boxing and unboxing operations:</span></span>  
  
 [!code-csharp[csProgGuideTypes#21](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_8.cs)]  
  
 <span data-ttu-id="d4cb0-139">En la figura siguiente se muestra el resultado de las instrucciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-139">The following figure demonstrates the result of the previous statements.</span></span>  
  
 <span data-ttu-id="d4cb0-140">![Gráfico de conversión unboxing](../../../csharp/programming-guide/types/media/vcunboxingconversion.gif "vcUnBoxingConversion")</span><span class="sxs-lookup"><span data-stu-id="d4cb0-140">![UnBoxing Conversion graphic](../../../csharp/programming-guide/types/media/vcunboxingconversion.gif "vcUnBoxingConversion")</span></span>  
<span data-ttu-id="d4cb0-141">Conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="d4cb0-141">Unboxing Conversion</span></span>  
  
 <span data-ttu-id="d4cb0-142">Para que la conversión unboxing de tipos de valor sea correcta en tiempo de ejecución, el elemento al que se aplica debe ser una referencia a un objeto creado previamente mediante la conversión boxing de una instancia de ese tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-142">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="d4cb0-143">Si se intenta aplicar la conversión unboxing a `null`, se producirá una excepción <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-143">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="d4cb0-144">Si se intenta aplicar la conversión unboxing a una referencia de un tipo de valor incompatible, se producirá una excepción <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-144">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4cb0-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4cb0-145">Example</span></span>  
 <span data-ttu-id="d4cb0-146">El ejemplo siguiente muestra un caso de conversión unboxing no válida y la excepción `InvalidCastException` resultante.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-146">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="d4cb0-147">Si se utiliza `try` y `catch`, se muestra un mensaje de error cuando se produce el error.</span><span class="sxs-lookup"><span data-stu-id="d4cb0-147">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>  
  
 [!code-csharp[csProgGuideTypes#20](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_9.cs)]  
  
 <span data-ttu-id="d4cb0-148">Este programa produce el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-148">This program outputs:</span></span>  
  
 `Specified cast is not valid. Error: Incorrect unboxing.`  
  
 <span data-ttu-id="d4cb0-149">Si cambia la instrucción:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-149">If you change the statement:</span></span>  
  
```  
int j = (short) o;  
```  
  
 <span data-ttu-id="d4cb0-150">a:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-150">to:</span></span>  
  
```  
int j = (int) o;  
```  
  
 <span data-ttu-id="d4cb0-151">la conversión se realizará y se obtendrá el resultado:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-151">the conversion will be performed, and you will get the output:</span></span>  
  
 `Unboxing OK.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="d4cb0-152">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d4cb0-152">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="related-sections"></a><span data-ttu-id="d4cb0-153">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d4cb0-153">Related Sections</span></span>  
 <span data-ttu-id="d4cb0-154">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="d4cb0-154">For more information:</span></span>  
  
-   [<span data-ttu-id="d4cb0-155">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="d4cb0-155">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="d4cb0-156">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="d4cb0-156">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="d4cb0-157">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d4cb0-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4cb0-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4cb0-158">See Also</span></span>  
 [<span data-ttu-id="d4cb0-159">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d4cb0-159">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
