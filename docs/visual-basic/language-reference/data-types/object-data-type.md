---
title: Object Data Type
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a><span data-ttu-id="9fccf-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="9fccf-102">Object Data Type</span></span>
<span data-ttu-id="9fccf-103">Contiene direcciones que hacen referencia a objetos.</span><span class="sxs-lookup"><span data-stu-id="9fccf-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="9fccf-104">Puede asignar cualquier tipo de referencia (cadena, matriz, clase o interfaz) a una `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="9fccf-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="9fccf-105">Un `Object` variable también puede hacer referencia a los datos de cualquier tipo de valor (numérico, `Boolean`, `Char`, `Date`, estructura o enumeración).</span><span class="sxs-lookup"><span data-stu-id="9fccf-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fccf-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9fccf-106">Remarks</span></span>  
 <span data-ttu-id="9fccf-107">El `Object` tipo de datos puede señalar a datos de cualquier tipo de datos, incluidas las instancias de objeto reconoce la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9fccf-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="9fccf-108">Utilice `Object` cuando no se conoce en tiempo de compilación puede señalar el tipo de datos de la variable a.</span><span class="sxs-lookup"><span data-stu-id="9fccf-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="9fccf-109">El valor predeterminado de `Object` es `Nothing` (una referencia nula).</span><span class="sxs-lookup"><span data-stu-id="9fccf-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="9fccf-110">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9fccf-110">Data Types</span></span>  
 <span data-ttu-id="9fccf-111">Puede asignar una variable, una constante o una expresión de cualquier tipo de datos para un `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="9fccf-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="9fccf-112">Para determinar el tipo de datos un `Object` variable hace referencia actualmente a, puede usar el <xref:System.Type.GetTypeCode%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="9fccf-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9fccf-113">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9fccf-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="9fccf-114">El `Object` tipo de datos es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="9fccf-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="9fccf-115">Sin embargo, Visual Basic trata un `Object` variable como un tipo de valor al que hace referencia a los datos de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9fccf-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="9fccf-116">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="9fccf-116">Storage</span></span>  
 <span data-ttu-id="9fccf-117">Cualquier tipo de datos que se hace referencia a un `Object` variable no contiene el valor de datos propia, sino un puntero al valor.</span><span class="sxs-lookup"><span data-stu-id="9fccf-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="9fccf-118">Siempre utiliza cuatro bytes en la memoria del equipo, pero esto no incluye el almacenamiento para los datos que representa el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="9fccf-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="9fccf-119">Debido al código que usa el puntero para localizar los datos, `Object` las variables que contienen tipos de valor son ligeramente más lentas tener acceso de forma explícita las variables con tipo.</span><span class="sxs-lookup"><span data-stu-id="9fccf-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="9fccf-120">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="9fccf-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="9fccf-121">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="9fccf-121">**Interop Considerations.**</span></span> <span data-ttu-id="9fccf-122">Si interactúa con componentes no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos de puntero en otros entornos no son compatibles con Visual Basic `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="9fccf-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="9fccf-123">**Rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="9fccf-123">**Performance.**</span></span> <span data-ttu-id="9fccf-124">Una variable se declara con el `Object` es lo suficientemente flexible como para contener una referencia a cualquier objeto de tipo.</span><span class="sxs-lookup"><span data-stu-id="9fccf-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="9fccf-125">Sin embargo, cuando se invoca un método o propiedad en una variable de este tipo, se produce siempre *enlace más tarde* (en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="9fccf-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="9fccf-126">Para forzar *el enlace anticipado* (en tiempo de compilación) y un mejor rendimiento, declare la variable con un nombre de clase específico o convertirlo al tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="9fccf-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="9fccf-127">Cuando se declara una variable de objeto, pruebe a utilizar un tipo de clase concreto, por ejemplo <xref:System.OperatingSystem>, en lugar de la generalizado `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="9fccf-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="9fccf-128">También debe utilizar la clase más específica disponible, como <xref:System.Windows.Forms.TextBox> en lugar de <xref:System.Windows.Forms.Control>, de modo que puede tener acceso a sus propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="9fccf-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="9fccf-129">Se suele usar el **clases** lista en la **Examinador de objetos** para buscar nombres de clase disponibles.</span><span class="sxs-lookup"><span data-stu-id="9fccf-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="9fccf-130">**De ampliación.**</span><span class="sxs-lookup"><span data-stu-id="9fccf-130">**Widening.**</span></span> <span data-ttu-id="9fccf-131">Todos los tipos de datos y todos los tipos de referencia se amplían a los `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9fccf-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="9fccf-132">Esto significa que puede convertir cualquier tipo a `Object` sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="9fccf-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="9fccf-133">Sin embargo, si convierte entre tipos de valor y `Object`, Visual Basic realiza operaciones llamadas *conversión boxing* y *unboxing*, que ralentizan la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9fccf-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="9fccf-134">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="9fccf-134">**Type Characters.**</span></span> <span data-ttu-id="9fccf-135">`Object`no tiene ningún carácter de tipo literal ni caracteres de tipo identificador.</span><span class="sxs-lookup"><span data-stu-id="9fccf-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="9fccf-136">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="9fccf-136">**Framework Type.**</span></span> <span data-ttu-id="9fccf-137">El tipo correspondiente en .NET Framework es la <xref:System.Object?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="9fccf-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fccf-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fccf-138">Example</span></span>  
 <span data-ttu-id="9fccf-139">En el ejemplo siguiente se muestra un `Object` variable que apunta a una instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="9fccf-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fccf-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fccf-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="9fccf-141">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9fccf-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="9fccf-142">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="9fccf-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9fccf-143">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="9fccf-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="9fccf-144">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9fccf-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="9fccf-145">Determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="9fccf-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="9fccf-146">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="9fccf-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
