---
title: Procedimiento para examinar y crear instancias de tipos genéricos mediante la reflexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
ms.openlocfilehash: 62e4e066740d0422f8f7045b043a5725278c209c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130131"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a><span data-ttu-id="6ae4f-102">Procedimiento para examinar y crear instancias de tipos genéricos mediante la reflexión</span><span class="sxs-lookup"><span data-stu-id="6ae4f-102">How to: Examine and Instantiate Generic Types with Reflection</span></span>
<span data-ttu-id="6ae4f-103">La información sobre los tipos genéricos se obtiene de la misma manera que la información sobre otros tipos: mediante el examen de un objeto <xref:System.Type> que representa el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-103">Information about generic types is obtained in the same way as information about other types: by examining a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="6ae4f-104">La diferencia principal es que un tipo genérico tiene una lista de objetos <xref:System.Type> que representan sus parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-104">The principle difference is that a generic type has a list of <xref:System.Type> objects representing its generic type parameters.</span></span> <span data-ttu-id="6ae4f-105">En el primer procedimiento de esta sección se examinan tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-105">The first procedure in this section examines generic types.</span></span>  
  
 <span data-ttu-id="6ae4f-106">Puede crear un objeto <xref:System.Type> que representa un tipo construido. Para ello, se enlazan los argumentos de tipo a los parámetros de tipo de una definición de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-106">You can create a <xref:System.Type> object that represents a constructed type by binding type arguments to the type parameters of a generic type definition.</span></span> <span data-ttu-id="6ae4f-107">En el segundo procedimiento se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-107">The second procedure demonstrates this.</span></span>  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a><span data-ttu-id="6ae4f-108">Para examinar un tipo genérico y sus parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6ae4f-108">To examine a generic type and its type parameters</span></span>  
  
1. <span data-ttu-id="6ae4f-109">Obtenga una instancia de <xref:System.Type> que representa el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-109">Get an instance of <xref:System.Type> that represents the generic type.</span></span> <span data-ttu-id="6ae4f-110">En el código siguiente, el tipo se obtiene con el operador de C# `typeof` (`GetType` en Visual Basic y `typeid` en Visual C++).</span><span class="sxs-lookup"><span data-stu-id="6ae4f-110">In the following code, the type is obtained using the C# `typeof` operator (`GetType` in Visual Basic, `typeid` in Visual C++).</span></span> <span data-ttu-id="6ae4f-111">Vea el tema de la clase <xref:System.Type> para conocer otras formas de obtener un objeto <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-111">See the <xref:System.Type> class topic for other ways to get a <xref:System.Type> object.</span></span> <span data-ttu-id="6ae4f-112">Tenga en cuenta que en el resto de este procedimiento, el tipo está incluido en un parámetro de método denominado `t`.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-112">Note that in the rest of this procedure, the type is contained in a method parameter named `t`.</span></span>  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2. <span data-ttu-id="6ae4f-113">Use la propiedad <xref:System.Type.IsGenericType%2A> para determinar si el tipo es genérico y la propiedad <xref:System.Type.IsGenericTypeDefinition%2A> para determinar si el tipo es una definición de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-113">Use the <xref:System.Type.IsGenericType%2A> property to determine whether the type is generic, and use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether the type is a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3. <span data-ttu-id="6ae4f-114">Obtenga una matriz que contiene los argumentos de tipo genérico con el método <xref:System.Type.GetGenericArguments%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-114">Get an array that contains the generic type arguments, using the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4. <span data-ttu-id="6ae4f-115">Para cada argumento de tipo, determine si es un parámetro de tipo (por ejemplo, en una definición de tipo genérico) o un tipo que se ha especificado para un parámetro de tipo (por ejemplo, en un tipo construido) mediante la propiedad <xref:System.Type.IsGenericParameter%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-115">For each type argument, determine whether it is a type parameter (for example, in a generic type definition) or a type that has been specified for a type parameter (for example, in a constructed type), using the <xref:System.Type.IsGenericParameter%2A> property.</span></span>  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5. <span data-ttu-id="6ae4f-116">En el sistema de tipos, un parámetro de tipo genérico se representa mediante una instancia de <xref:System.Type>, igual que los tipos normales.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-116">In the type system, a generic type parameter is represented by an instance of <xref:System.Type>, just as ordinary types are.</span></span> <span data-ttu-id="6ae4f-117">El siguiente código muestra el nombre y la posición del parámetro de un objeto <xref:System.Type> que representa un parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-117">The following code displays the name and parameter position of a <xref:System.Type> object that represents a generic type parameter.</span></span> <span data-ttu-id="6ae4f-118">La posición del parámetro es información trivial en este caso; resulta más interesante al examinar un parámetro de tipo que se ha usado como un argumento de tipo de otro tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-118">The parameter position is trivial information here; it is of more interest when you are examining a type parameter that has been used as a type argument of another generic type.</span></span>  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6. <span data-ttu-id="6ae4f-119">Use el método <xref:System.Type.GetGenericParameterConstraints%2A> para obtener todas las restricciones de una sola matriz y determinar la restricción de tipo base y las restricciones de interfaz de un parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-119">Determine the base type constraint and the interface constraints of a generic type parameter by using the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain all the constraints in a single array.</span></span> <span data-ttu-id="6ae4f-120">No se garantiza que las restricciones estén en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-120">Constraints are not guaranteed to be in any particular order.</span></span>  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7. <span data-ttu-id="6ae4f-121">Use la propiedad <xref:System.Type.GenericParameterAttributes%2A> para detectar las restricciones especiales de un parámetro de tipo, como la exigencia de que sea un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-121">Use the <xref:System.Type.GenericParameterAttributes%2A> property to discover the special constraints on a type parameter, such as requiring that it be a reference type.</span></span> <span data-ttu-id="6ae4f-122">La propiedad también incluye valores que representan la varianza, que se puede enmascarar como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-122">The property also includes values that represent variance, which you can mask off as shown in the following code.</span></span>  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8. <span data-ttu-id="6ae4f-123">Los atributos de las restricciones especiales son marcas; la misma marca (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) que no representa ninguna restricción especial no representa tampoco ninguna covarianza ni contravarianza.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-123">The special constraint attributes are flags, and the same flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) that represents no special constraints also represents no covariance or contravariance.</span></span> <span data-ttu-id="6ae4f-124">Por lo tanto, para probar cualquiera de estas condiciones, debe usar la máscara apropiada.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-124">Thus, to test for either of these conditions you must use the appropriate mask.</span></span> <span data-ttu-id="6ae4f-125">En este caso, use <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> para aislar las marcas de restricciones especiales.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-125">In this case, use <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> to isolate the special constraint flags.</span></span>  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a><span data-ttu-id="6ae4f-126">Creación de una instancia de un tipo genérico</span><span class="sxs-lookup"><span data-stu-id="6ae4f-126">Constructing an Instance of a Generic Type</span></span>  
 <span data-ttu-id="6ae4f-127">Un tipo genérico es como una plantilla.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-127">A generic type is like a template.</span></span> <span data-ttu-id="6ae4f-128">No se pueden crear instancias de él, a menos que se especifiquen tipos reales para sus parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-128">You cannot create instances of it unless you specify real types for its generic type parameters.</span></span> <span data-ttu-id="6ae4f-129">Para hacerlo en tiempo de ejecución con la reflexión, se necesita el método <xref:System.Type.MakeGenericType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-129">To do this at run time, using reflection, requires the <xref:System.Type.MakeGenericType%2A> method.</span></span>  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a><span data-ttu-id="6ae4f-130">Para crear una instancia de un tipo genérico</span><span class="sxs-lookup"><span data-stu-id="6ae4f-130">To construct an instance of a generic type</span></span>  
  
1. <span data-ttu-id="6ae4f-131">Obtenga un objeto <xref:System.Type> que representa el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-131">Get a <xref:System.Type> object that represents the generic type.</span></span> <span data-ttu-id="6ae4f-132">El código siguiente obtiene el tipo genérico <xref:System.Collections.Generic.Dictionary%602> de dos maneras: mediante la sobrecarga del método <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> con una cadena que describe el tipo y mediante la llamada al método <xref:System.Type.GetGenericTypeDefinition%2A> en el tipo construido `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6ae4f-132">The following code gets the generic type <xref:System.Collections.Generic.Dictionary%602> in two different ways: by using the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method overload with a string describing the type, and by calling the <xref:System.Type.GetGenericTypeDefinition%2A> method on the constructed type `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic).</span></span> <span data-ttu-id="6ae4f-133">El método <xref:System.Type.MakeGenericType%2A> exige una definición de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-133">The <xref:System.Type.MakeGenericType%2A> method requires a generic type definition.</span></span>  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2. <span data-ttu-id="6ae4f-134">Cree una matriz de argumentos de tipo para sustituir a los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-134">Construct an array of type arguments to substitute for the type parameters.</span></span> <span data-ttu-id="6ae4f-135">La matriz debe contener el número correcto de objetos <xref:System.Type>, en el mismo orden en que aparecen en la lista de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-135">The array must contain the correct number of <xref:System.Type> objects, in the same order as they appear in the type parameter list.</span></span> <span data-ttu-id="6ae4f-136">En este caso, la clave (el primer parámetro de tipo) es de tipo <xref:System.String> y los valores del diccionario son instancias de una clase denominada `Example`.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-136">In this case, the key (first type parameter) is of type <xref:System.String>, and the values in the dictionary are instances of a class named `Example`.</span></span>  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3. <span data-ttu-id="6ae4f-137">Llame al método <xref:System.Type.MakeGenericType%2A> para enlazar los argumentos de tipo a los parámetros de tipo y crear el tipo.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-137">Call the <xref:System.Type.MakeGenericType%2A> method to bind the type arguments to the type parameters and construct the type.</span></span>  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4. <span data-ttu-id="6ae4f-138">Use la sobrecarga del método <xref:System.Activator.CreateInstance%28System.Type%29> para crear un objeto del tipo construido.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-138">Use the <xref:System.Activator.CreateInstance%28System.Type%29> method overload to create an object of the constructed type.</span></span> <span data-ttu-id="6ae4f-139">El código siguiente almacena dos instancias de la clase `Example` en el objeto `Dictionary<String, Example>` resultante.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-139">The following code stores two instances of the `Example` class in the resulting `Dictionary<String, Example>` object.</span></span>  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="6ae4f-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ae4f-140">Example</span></span>  
 <span data-ttu-id="6ae4f-141">En el ejemplo de código siguiente se define un método `DisplayGenericType` para examinar las definiciones de tipo genérico y los tipos construidos usados en el código y mostrar su información.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-141">The following code example defines a `DisplayGenericType` method to examine the generic type definitions and constructed types used in the code and display their information.</span></span> <span data-ttu-id="6ae4f-142">El método `DisplayGenericType` muestra cómo usar las propiedades <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> y <xref:System.Type.GenericParameterPosition%2A>, y el método <xref:System.Type.GetGenericArguments%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-142">The `DisplayGenericType` method shows how to use the <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A>, and <xref:System.Type.GenericParameterPosition%2A> properties and the <xref:System.Type.GetGenericArguments%2A> method.</span></span>  
  
 <span data-ttu-id="6ae4f-143">En el ejemplo también se define un método `DisplayGenericParameter` para examinar un parámetro de tipo genérico y mostrar sus restricciones.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-143">The example also defines a `DisplayGenericParameter` method to examine a generic type parameter and display its constraints.</span></span>  
  
 <span data-ttu-id="6ae4f-144">En el ejemplo de código se define un conjunto de tipos de prueba, incluido un tipo genérico que ilustra las restricciones de parámetro de tipo, y se muestra cómo visualizar información sobre estos tipos.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-144">The code example defines a set of test types, including a generic type that illustrates type parameter constraints, and shows how to display information about these types.</span></span>  
  
 <span data-ttu-id="6ae4f-145">El ejemplo crea un tipo a partir de la clase <xref:System.Collections.Generic.Dictionary%602> al crear una matriz de argumentos de tipo y llamar al método <xref:System.Type.MakeGenericType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-145">The example constructs a type from the <xref:System.Collections.Generic.Dictionary%602> class by creating an array of type arguments and calling the <xref:System.Type.MakeGenericType%2A> method.</span></span> <span data-ttu-id="6ae4f-146">El programa compara el objeto <xref:System.Type> construido mediante <xref:System.Type.MakeGenericType%2A> con un objeto <xref:System.Type> obtenido mediante `typeof` (`GetType` en Visual Basic) y muestra que son iguales.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-146">The program compares the <xref:System.Type> object constructed using <xref:System.Type.MakeGenericType%2A> with a <xref:System.Type> object obtained using `typeof` (`GetType` in Visual Basic), demonstrating that they are the same.</span></span> <span data-ttu-id="6ae4f-147">Del mismo modo, el programa usa el método <xref:System.Type.GetGenericTypeDefinition%2A> para obtener la definición de tipo genérico del tipo construido y lo compara con el objeto <xref:System.Type> que representa a la clase <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="6ae4f-147">Similarly, the program uses the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition of the constructed type, and compares it to the <xref:System.Type> object representing the <xref:System.Collections.Generic.Dictionary%602> class.</span></span>  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ae4f-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ae4f-148">See also</span></span>

- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="6ae4f-149">Reflexión y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="6ae4f-149">Reflection and Generic Types</span></span>](reflection-and-generic-types.md)
- [<span data-ttu-id="6ae4f-150">Ver información tipos</span><span class="sxs-lookup"><span data-stu-id="6ae4f-150">Viewing Type Information</span></span>](viewing-type-information.md)
- [<span data-ttu-id="6ae4f-151">Genéricos</span><span class="sxs-lookup"><span data-stu-id="6ae4f-151">Generics</span></span>](../../standard/generics/index.md)
