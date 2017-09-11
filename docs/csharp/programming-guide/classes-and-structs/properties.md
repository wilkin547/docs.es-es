---
title: "Propiedades (Guía de programación de C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.properties
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 127299a617cacee15f87964a12bb3877a2586204
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="properties-c-programming-guide"></a><span data-ttu-id="e8e6b-102">Propiedades (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e8e6b-102">Properties (C# Programming Guide)</span></span>

<span data-ttu-id="e8e6b-103">Una propiedad es un miembro que proporciona un mecanismo flexible para leer, escribir o calcular el valor de un campo privado.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-103">A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field.</span></span> <span data-ttu-id="e8e6b-104">Las propiedades se pueden usar como si fueran miembros de datos públicos, pero en realidad son métodos especiales denominados *descriptores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-104">Properties can be used as if they are public data members, but they are actually special methods called *accessors*.</span></span> <span data-ttu-id="e8e6b-105">Esto permite acceder fácilmente a los datos a la vez que proporciona la seguridad y la flexibilidad de los métodos.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-105">This enables data to be accessed easily and still helps promote the safety and flexibility of methods.</span></span>  

## <a name="properties-overview"></a><span data-ttu-id="e8e6b-106">Información general sobre propiedades</span><span class="sxs-lookup"><span data-stu-id="e8e6b-106">Properties overview</span></span>  
  
- <span data-ttu-id="e8e6b-107">Las propiedades permiten que una clase exponga una manera pública de obtener y establecer valores, a la vez que se oculta el código de implementación o comprobación.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-107">Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.</span></span>  
  
- <span data-ttu-id="e8e6b-108">Para devolver el valor de la propiedad se usa un descriptor de acceso de propiedad [get](../../../csharp/language-reference/keywords/get.md), mientras que para asignar un nuevo valor se emplea un descriptor de acceso de propiedad [set](../../../csharp/language-reference/keywords/set.md).</span><span class="sxs-lookup"><span data-stu-id="e8e6b-108">A [get](../../../csharp/language-reference/keywords/get.md) property accessor is used to return the property value, and a [set](../../../csharp/language-reference/keywords/set.md) property accessor is used to assign a new value.</span></span> <span data-ttu-id="e8e6b-109">Estos descriptores de acceso pueden tener diferentes niveles de acceso.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-109">These accessors can have different access levels.</span></span> <span data-ttu-id="e8e6b-110">Para más información, vea [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="e8e6b-110">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
- <span data-ttu-id="e8e6b-111">La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor que va a asignar el descriptor de acceso `set`.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-111">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
- <span data-ttu-id="e8e6b-112">Las propiedades pueden ser *de lectura y escritura* (en ambos casos tienen un descriptor de acceso `get` y `set`), *de solo lectura* (tienen un descriptor de acceso `get`, pero no `set`) o *de solo escritura* (tienen un descriptor de acceso `set`, pero no `get`).</span><span class="sxs-lookup"><span data-stu-id="e8e6b-112">Properties can be *read-write* (they have both a `get` and a `set` accessor), *read-only* (they have a `get` accessor but no `set` accessor), or *write-only* (they have a `set` accessor, but no `get` accessor).</span></span> <span data-ttu-id="e8e6b-113">Las propiedades de solo escritura son poco frecuentes y se suelen usar para restringir el acceso a datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-113">Write-only properties are rare and are most commonly used to restrict access to sensitive data.</span></span>

- <span data-ttu-id="e8e6b-114">Las propiedades simples que no necesitan ningún código de descriptor de acceso personalizado se pueden implementar como definiciones de cuerpos de expresión o como [propiedades implementadas automáticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e8e6b-114">Simple properties that require no custom accessor code can be implemented either as expression body definitions or as [auto-implemented properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>
 
## <a name="properties-with-backing-fields"></a><span data-ttu-id="e8e6b-115">Propiedades con campos de respaldo</span><span class="sxs-lookup"><span data-stu-id="e8e6b-115">Properties with backing fields</span></span>

<span data-ttu-id="e8e6b-116">Un patrón básico para implementar una propiedad conlleva el uso de un campo de respaldo privado para establecer y recuperar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-116">One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value.</span></span> <span data-ttu-id="e8e6b-117">El descriptor de acceso `get` devuelve el valor del campo privado y el descriptor de acceso `set` puede realizar alguna validación de datos antes de asignar un valor al campo privado.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-117">The `get` accessor returns the value of the private field, and the `set` accessor may perform some data validation before assigning a value to the private field.</span></span> <span data-ttu-id="e8e6b-118">Ambos descriptores de acceso además pueden realizar algún cálculo o conversión en los datos antes de que se almacenen o se devuelvan.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-118">Both accessors may also perform some conversion or computation on the data before it is stored or returned.</span></span>

<span data-ttu-id="e8e6b-119">En el ejemplo siguiente se muestra este patrón.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-119">The following example illustrates this pattern.</span></span> <span data-ttu-id="e8e6b-120">En este ejemplo, la clase `TimePeriod` representa un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-120">In this example, the `TimePeriod` class represents an interval of time.</span></span> <span data-ttu-id="e8e6b-121">Internamente, la clase almacena el intervalo de tiempo en segundos en un campo privado denominado `seconds`.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-121">Internally, the class stores the time interval in seconds in a private field named `seconds`.</span></span> <span data-ttu-id="e8e6b-122">Una propiedad de lectura y escritura denominada `Hours` permite al cliente especificar el intervalo de tiempo en horas.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-122">A read-write property named `Hours` allows the customer to specify the time interval in hours.</span></span> <span data-ttu-id="e8e6b-123">Los descriptores de acceso `get` y `set` realizan la conversión necesaria entre horas y segundos.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-123">Both the `get` and the `set` accessors perform the necessary conversion between hours and seconds.</span></span> <span data-ttu-id="e8e6b-124">Además, el descriptor de acceso `set` valida los datos e inicia una excepción @System.ArgumentOutOfRangeException si el número de horas no es válido.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-124">In addition, the `set` accessor validates the data and throws an @System.ArgumentOutOfRangeException if the number of hours is invalid.</span></span> 
   
 <span data-ttu-id="e8e6b-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8e6b-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="e8e6b-126">Definiciones de cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="e8e6b-126">Expression body definitions</span></span>  

 <span data-ttu-id="e8e6b-127">Los descriptores de acceso de propiedad suelen constar de instrucciones de una sola línea que simplemente asignan o devuelven el resultado de una expresión.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-127">Property accessors often consist of single-line statements that just assign or return the result of an expression.</span></span> <span data-ttu-id="e8e6b-128">Puede implementar estas propiedades como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-128">You can implement these properties as expression-bodied members.</span></span> <span data-ttu-id="e8e6b-129">Las definiciones de cuerpos de expresión constan del símbolo `=>` seguido de la expresión que se va a asignar a la propiedad o a recuperar de ella.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-129">Expression body definitions consist of the `=>` symbol followed by the expression to assign to or retrieve from the property.</span></span>

 <span data-ttu-id="e8e6b-130">A partir de C# 6, las propiedades de solo lectura pueden implementar el descriptor de acceso `get` como miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-130">Starting with C# 6, read-only properties can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="e8e6b-131">En este caso, no se usan ni la palabra clave del descriptor de acceso `get` ni la palabra clave `return`.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-131">In this case, neither the `get` accessor keyword nor the `return` keyword is used.</span></span> <span data-ttu-id="e8e6b-132">En el ejemplo siguiente se implementa la propiedad de solo lectura `Name` como miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-132">The following example implements the read-only `Name` property as an expression-bodied member.</span></span>

 <span data-ttu-id="e8e6b-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8e6b-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span></span>  

 <span data-ttu-id="e8e6b-134">A partir de C# 7, los descriptores de acceso `get` y `set` se pueden implementar como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-134">Starting with C# 7, both the `get` and the `set` accessor can be implemented as expression-bodied members.</span></span> <span data-ttu-id="e8e6b-135">En este caso, las palabras clave `get` y `set` deben estar presentes.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-135">In this case, the `get` and `set` keywords must be present.</span></span> <span data-ttu-id="e8e6b-136">En el ejemplo siguiente se muestra el uso de definiciones de cuerpos de expresión para ambos descriptores de acceso.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-136">The following example illustrates the use of expression body definitions for both accessors.</span></span> <span data-ttu-id="e8e6b-137">Observe que no se usa la palabra clave `return` con el descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-137">Note that the `return` keyword is not used with the `get` accessor.</span></span>
 
  <span data-ttu-id="e8e6b-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8e6b-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span></span>  

## <a name="auto-implemented-properties"></a><span data-ttu-id="e8e6b-139">Propiedades implementadas automáticamente</span><span class="sxs-lookup"><span data-stu-id="e8e6b-139">Auto-implemented properties</span></span>

<span data-ttu-id="e8e6b-140">En algunos casos, los descriptores de acceso de propiedad `get` y `set` simplemente asignan un valor a un campo de respaldo o recuperan un valor de él sin incluir ninguna lógica adicional.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-140">In some cases, property `get` and `set` accessors just assign a value to or retrieve a value from a backing field without including any additional logic.</span></span> <span data-ttu-id="e8e6b-141">Mediante las propiedades implementadas automáticamente, puede simplificar el código y conseguir que el compilador de C# le proporcione el campo de respaldo de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-141">By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.</span></span> 

<span data-ttu-id="e8e6b-142">Si una propiedad tiene un descriptor de acceso `get` y `set`, ambos deben ser implementados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-142">If a property has both a `get` and a `set` accessor, both must be auto-implemented.</span></span> <span data-ttu-id="e8e6b-143">Una propiedad implementada automáticamente se define mediante las palabras clave `get` y `set` sin proporcionar ninguna implementación.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-143">You define an auto-implemented property by using the `get` and `set` keywords without providing any implementation.</span></span> <span data-ttu-id="e8e6b-144">El ejemplo siguiente repite el anterior, salvo que `Name` y `Price` son propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e8e6b-144">The following example repeats the previous one, except that `Name` and `Price` are auto-implemented properties.</span></span> <span data-ttu-id="e8e6b-145">Observe que en el ejemplo también se quita el constructor parametrizado, por lo que los objetos `SaleItem` ahora se inicializan con una llamada al constructor predeterminado y un [inicializador de objeto](object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="e8e6b-145">Note that the example also removes the parameterized constructor, so that `SaleItem` objects are now initialized with a call to the default constructor and an [object initializer](object-and-collection-initializers.md).</span></span>

  <span data-ttu-id="e8e6b-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8e6b-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span></span>  

## <a name="related-sections"></a><span data-ttu-id="e8e6b-147">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e8e6b-147">Related sections</span></span>  
  
-   [<span data-ttu-id="e8e6b-148">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="e8e6b-148">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="e8e6b-149">Propiedades de interfaz</span><span class="sxs-lookup"><span data-stu-id="e8e6b-149">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="e8e6b-150">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="e8e6b-150">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="e8e6b-151">Restringir la accesibilidad del descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="e8e6b-151">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [<span data-ttu-id="e8e6b-152">Propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="e8e6b-152">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="e8e6b-153">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e8e6b-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8e6b-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8e6b-154">See also</span></span>
 <span data-ttu-id="e8e6b-155">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8e6b-155">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e8e6b-156">[Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e8e6b-156">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="e8e6b-157">[Indizadores](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8e6b-157">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="e8e6b-158">[get (palabra clave)](../../../csharp/language-reference/keywords/get.md)  </span><span class="sxs-lookup"><span data-stu-id="e8e6b-158">[get keyword](../../../csharp/language-reference/keywords/get.md)  </span></span>  
 [<span data-ttu-id="e8e6b-159">set (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="e8e6b-159">set keyword</span></span>](../../../csharp/language-reference/keywords/set.md)    

