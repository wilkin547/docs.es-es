---
description: 'Más información sobre: inicializadores de objeto: tipos con nombre y anónimos (Visual Basic)'
title: 'Inicializadores de objeto: tipos con nombre y anónimos'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 47182653e74b16b9911f4b727eb1595bf3eceba6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455254"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="b22b6-103">Inicializadores de objeto: Tipos con nombre y anónimos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b22b6-103">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>

<span data-ttu-id="b22b6-104">Los inicializadores de objeto permiten especificar propiedades para un objeto complejo mediante el uso de una sola expresión.</span><span class="sxs-lookup"><span data-stu-id="b22b6-104">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="b22b6-105">Se pueden usar para crear instancias de tipos con nombre y de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-105">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="b22b6-106">Declaraciones</span><span class="sxs-lookup"><span data-stu-id="b22b6-106">Declarations</span></span>  

 <span data-ttu-id="b22b6-107">Las declaraciones de instancias de tipos con nombre y anónimos pueden ser prácticamente idénticas, pero sus efectos no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-107">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="b22b6-108">Cada categoría tiene capacidades y restricciones propias.</span><span class="sxs-lookup"><span data-stu-id="b22b6-108">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="b22b6-109">En el ejemplo siguiente se muestra una manera cómoda de declarar e inicializar una instancia de una clase con nombre, `Customer` , mediante una lista de inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b22b6-109">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="b22b6-110">Observe que el nombre de la clase se especifica después de la palabra clave `New` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-110">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 <span data-ttu-id="b22b6-111">Un tipo anónimo no tiene ningún nombre utilizable.</span><span class="sxs-lookup"><span data-stu-id="b22b6-111">An anonymous type has no usable name.</span></span> <span data-ttu-id="b22b6-112">Por lo tanto, una creación de instancias de un tipo anónimo no puede incluir un nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="b22b6-112">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 <span data-ttu-id="b22b6-113">Los requisitos y los resultados de las dos declaraciones no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-113">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="b22b6-114">Para `namedCust` , una `Customer` clase que tiene una `Name` propiedad ya debe existir y la declaración crea una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="b22b6-114">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="b22b6-115">Para `anonymousCust` , el compilador define una nueva clase que tiene una propiedad, una cadena denominada `Name` y crea una nueva instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="b22b6-115">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="b22b6-116">Tipos con nombre</span><span class="sxs-lookup"><span data-stu-id="b22b6-116">Named Types</span></span>  

 <span data-ttu-id="b22b6-117">Los inicializadores de objeto proporcionan una manera sencilla de llamar al constructor de un tipo y, a continuación, establecer los valores de algunas o todas las propiedades en una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="b22b6-117">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="b22b6-118">El compilador invoca el constructor adecuado para la instrucción: el constructor sin parámetros si no se presentan argumentos, o un constructor con parámetros si se envían uno o más argumentos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-118">The compiler invokes the appropriate constructor for the statement: the parameterless constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="b22b6-119">Después, las propiedades especificadas se inicializan en el orden en que se presentan en la lista de inicializadores.</span><span class="sxs-lookup"><span data-stu-id="b22b6-119">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="b22b6-120">Cada inicialización en la lista de inicializadores consta de la asignación de un valor inicial a un miembro de la clase.</span><span class="sxs-lookup"><span data-stu-id="b22b6-120">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="b22b6-121">Los nombres y los tipos de datos de los miembros se determinan cuando se define la clase.</span><span class="sxs-lookup"><span data-stu-id="b22b6-121">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="b22b6-122">En los ejemplos siguientes, la `Customer` clase debe existir y debe tener miembros denominados `Name` y `City` que puedan aceptar valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="b22b6-122">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 <span data-ttu-id="b22b6-123">Como alternativa, puede obtener el mismo resultado mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b22b6-123">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 <span data-ttu-id="b22b6-124">Cada una de estas declaraciones es equivalente al ejemplo siguiente, que crea un `Customer` objeto mediante el constructor sin parámetros y, a continuación, especifica los valores iniciales de `Name` las `City` propiedades y usando una `With` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b22b6-124">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the parameterless constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 <span data-ttu-id="b22b6-125">Si la `Customer` clase contiene un constructor con parámetros que le permite enviar un valor para `Name` , por ejemplo, también puede declarar e inicializar un `Customer` objeto de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b22b6-125">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 <span data-ttu-id="b22b6-126">No es necesario inicializar todas las propiedades, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b22b6-126">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 <span data-ttu-id="b22b6-127">Sin embargo, la lista de inicialización no puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="b22b6-127">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="b22b6-128">Las propiedades sin inicializar conservan sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b22b6-128">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="b22b6-129">Inferencia de tipos con tipos con nombre</span><span class="sxs-lookup"><span data-stu-id="b22b6-129">Type Inference with Named Types</span></span>  

 <span data-ttu-id="b22b6-130">Puede acortar el código para la declaración de `cust1` combinando los inicializadores de objeto y la inferencia de tipo local.</span><span class="sxs-lookup"><span data-stu-id="b22b6-130">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="b22b6-131">Esto le permite omitir la `As` cláusula en la declaración de variable.</span><span class="sxs-lookup"><span data-stu-id="b22b6-131">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="b22b6-132">El tipo de datos de la variable se deduce del tipo del objeto creado por la asignación.</span><span class="sxs-lookup"><span data-stu-id="b22b6-132">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="b22b6-133">En el ejemplo siguiente, el tipo de `cust6` es `Customer` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-133">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="b22b6-134">Comentarios acerca de los tipos con nombre</span><span class="sxs-lookup"><span data-stu-id="b22b6-134">Remarks About Named Types</span></span>  
  
- <span data-ttu-id="b22b6-135">No se puede inicializar un miembro de clase más de una vez en la lista de inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b22b6-135">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="b22b6-136">La declaración de `cust7` provoca un error.</span><span class="sxs-lookup"><span data-stu-id="b22b6-136">The declaration of `cust7` causes an error.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- <span data-ttu-id="b22b6-137">Un miembro se puede usar para inicializarse a sí mismo o a otro campo.</span><span class="sxs-lookup"><span data-stu-id="b22b6-137">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="b22b6-138">Si se tiene acceso a un miembro antes de que se haya inicializado, como en la siguiente declaración de `cust8` , se usará el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b22b6-138">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="b22b6-139">Recuerde que cuando se procesa una declaración que usa un inicializador de objeto, lo primero que ocurre es que se invoca el constructor adecuado.</span><span class="sxs-lookup"><span data-stu-id="b22b6-139">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="b22b6-140">Después, se inicializan los campos individuales en la lista de inicializadores.</span><span class="sxs-lookup"><span data-stu-id="b22b6-140">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="b22b6-141">En los ejemplos siguientes, se asigna el valor predeterminado para `Name` `cust8` y se asigna un valor inicializado en `cust9` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-141">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     <span data-ttu-id="b22b6-142">En el ejemplo siguiente se usa el constructor con parámetros de `cust3` y `cust4` para declarar e inicializar `cust10` y `cust11` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-142">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- <span data-ttu-id="b22b6-143">Los inicializadores de objeto se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="b22b6-143">Object initializers can be nested.</span></span> <span data-ttu-id="b22b6-144">En el ejemplo siguiente, `AddressClass` es una clase que tiene dos propiedades, `City` y `State` , y la `Customer` clase tiene una `Address` propiedad que es una instancia de `AddressClass` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-144">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- <span data-ttu-id="b22b6-145">La lista de inicialización no puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="b22b6-145">The initialization list cannot be empty.</span></span>  
  
- <span data-ttu-id="b22b6-146">La instancia que se está inicializando no puede ser de tipo Object.</span><span class="sxs-lookup"><span data-stu-id="b22b6-146">The instance being initialized cannot be of type Object.</span></span>  
  
- <span data-ttu-id="b22b6-147">Los miembros de clase que se van a inicializar no pueden ser miembros compartidos, miembros de solo lectura, constantes o llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-147">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
- <span data-ttu-id="b22b6-148">Los miembros de clase que se van a inicializar no se pueden indizar ni calificar.</span><span class="sxs-lookup"><span data-stu-id="b22b6-148">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="b22b6-149">En los siguientes ejemplos se producen errores del compilador:</span><span class="sxs-lookup"><span data-stu-id="b22b6-149">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="b22b6-150">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="b22b6-150">Anonymous Types</span></span>  

 <span data-ttu-id="b22b6-151">Los tipos anónimos usan inicializadores de objeto para crear instancias de nuevos tipos que no se definen explícitamente ni se denominan.</span><span class="sxs-lookup"><span data-stu-id="b22b6-151">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="b22b6-152">En su lugar, el compilador genera un tipo de acuerdo con las propiedades que se designan en la lista de inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b22b6-152">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="b22b6-153">Dado que no se especifica el nombre del tipo, se hace referencia a él como un *tipo anónimo*.</span><span class="sxs-lookup"><span data-stu-id="b22b6-153">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="b22b6-154">Por ejemplo, compare la siguiente declaración con la anterior para `cust6` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-154">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 <span data-ttu-id="b22b6-155">La única diferencia sintácticamente es que no se especifica ningún nombre después `New` del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-155">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="b22b6-156">Sin embargo, lo que sucede es bastante diferente.</span><span class="sxs-lookup"><span data-stu-id="b22b6-156">However, what happens is quite different.</span></span> <span data-ttu-id="b22b6-157">El compilador define un nuevo tipo anónimo que tiene dos propiedades, `Name` y `City` , y crea una instancia de ella con los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="b22b6-157">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="b22b6-158">La inferencia de tipos determina los tipos de `Name` y `City` en el ejemplo que son cadenas.</span><span class="sxs-lookup"><span data-stu-id="b22b6-158">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b22b6-159">El compilador genera el nombre del tipo anónimo y puede variar de la compilación a la compilación.</span><span class="sxs-lookup"><span data-stu-id="b22b6-159">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="b22b6-160">El código no debe utilizar ni basarse en el nombre de un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="b22b6-160">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="b22b6-161">Dado que el nombre del tipo no está disponible, no se puede usar una `As` cláusula para declarar `cust13` .</span><span class="sxs-lookup"><span data-stu-id="b22b6-161">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="b22b6-162">Se debe inferir su tipo.</span><span class="sxs-lookup"><span data-stu-id="b22b6-162">Its type must be inferred.</span></span> <span data-ttu-id="b22b6-163">Sin usar el enlace en tiempo de ejecución, esto limita el uso de tipos anónimos a variables locales.</span><span class="sxs-lookup"><span data-stu-id="b22b6-163">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="b22b6-164">Los tipos anónimos proporcionan compatibilidad crítica para las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="b22b6-164">Anonymous types provide critical support for LINQ queries.</span></span> <span data-ttu-id="b22b6-165">Para obtener más información sobre el uso de tipos anónimos en las consultas, vea [tipos anónimos](anonymous-types.md) e [Introducción a LINQ en Visual Basic](../linq/introduction-to-linq.md).</span><span class="sxs-lookup"><span data-stu-id="b22b6-165">For more information about the use of anonymous types in queries, see [Anonymous Types](anonymous-types.md) and [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="b22b6-166">Comentarios acerca de los tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="b22b6-166">Remarks About Anonymous Types</span></span>  
  
- <span data-ttu-id="b22b6-167">Normalmente, todas o la mayoría de las propiedades de una declaración de tipo anónimo serán propiedades de clave, que se indican escribiendo la palabra clave `Key` delante del nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b22b6-167">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     <span data-ttu-id="b22b6-168">Para obtener más información acerca de las propiedades de clave, consulte [key](../../../language-reference/modifiers/key.md).</span><span class="sxs-lookup"><span data-stu-id="b22b6-168">For more information about key properties, see [Key](../../../language-reference/modifiers/key.md).</span></span>  
  
- <span data-ttu-id="b22b6-169">Al igual que los tipos con nombre, las listas de inicializadores para definiciones de tipos anónimos deben declarar al menos una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b22b6-169">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- <span data-ttu-id="b22b6-170">Cuando se declara una instancia de un tipo anónimo, el compilador genera una definición de tipo anónimo coincidente.</span><span class="sxs-lookup"><span data-stu-id="b22b6-170">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="b22b6-171">Los nombres y los tipos de datos de las propiedades se toman de la declaración de instancia y se incluyen en el compilador en la definición.</span><span class="sxs-lookup"><span data-stu-id="b22b6-171">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="b22b6-172">Las propiedades no tienen nombre y se definen de antemano, como serían para un tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="b22b6-172">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="b22b6-173">Se deducen sus tipos.</span><span class="sxs-lookup"><span data-stu-id="b22b6-173">Their types are inferred.</span></span> <span data-ttu-id="b22b6-174">No se pueden especificar los tipos de datos de las propiedades mediante el uso de una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="b22b6-174">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
- <span data-ttu-id="b22b6-175">Los tipos anónimos también pueden establecer los nombres y valores de sus propiedades de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="b22b6-175">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="b22b6-176">Por ejemplo, una propiedad de tipo anónimo puede tomar el nombre y el valor de una variable, o el nombre y el valor de una propiedad de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="b22b6-176">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     <span data-ttu-id="b22b6-177">Para obtener más información sobre las opciones para definir propiedades en tipos anónimos, vea [Cómo: inferir nombres y tipos de propiedades en declaraciones de tipos anónimos](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span><span class="sxs-lookup"><span data-stu-id="b22b6-177">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b22b6-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b22b6-178">See also</span></span>

- [<span data-ttu-id="b22b6-179">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="b22b6-179">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="b22b6-180">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="b22b6-180">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="b22b6-181">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b22b6-181">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
- [<span data-ttu-id="b22b6-182">Procedimiento para deducir tipos y nombres de propiedades en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="b22b6-182">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="b22b6-183">Key</span><span class="sxs-lookup"><span data-stu-id="b22b6-183">Key</span></span>](../../../language-reference/modifiers/key.md)
- [<span data-ttu-id="b22b6-184">Procedimiento para declarar un objeto mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="b22b6-184">How to: Declare an Object by Using an Object Initializer</span></span>](how-to-declare-an-object-by-using-an-object-initializer.md)
