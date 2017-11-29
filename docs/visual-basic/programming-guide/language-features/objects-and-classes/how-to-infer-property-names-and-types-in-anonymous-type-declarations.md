---
title: "Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 66b9f8c0346f74ff631969bda122de7913a551c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a><span data-ttu-id="04b5d-102">Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04b5d-102">How to: Infer Property Names and Types in Anonymous Type Declarations (Visual Basic)</span></span>
<span data-ttu-id="04b5d-103">Los tipos anónimos no proporcionan ningún mecanismo para especificar directamente los tipos de datos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="04b5d-103">Anonymous types provide no mechanism for directly specifying the data types of properties.</span></span> <span data-ttu-id="04b5d-104">Los tipos de todas las propiedades son inferidos.</span><span class="sxs-lookup"><span data-stu-id="04b5d-104">Types of all properties are inferred.</span></span> <span data-ttu-id="04b5d-105">En el ejemplo siguiente, los tipos de `Name` y `Price` se infieren directamente de los valores que se usan para inicializarlos.</span><span class="sxs-lookup"><span data-stu-id="04b5d-105">In the following example, the types of `Name` and `Price` are inferred directly from the values that are used to initialize them.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_1.vb)]  
  
 <span data-ttu-id="04b5d-106">Los tipos anónimos también pueden inferir nombres y tipos de propiedad de otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="04b5d-106">Anonymous types can also infer property names and types from other sources.</span></span> <span data-ttu-id="04b5d-107">En las secciones siguientes se ofrece una lista de las circunstancias donde es posible la inferencia y ejemplos de situaciones en que no lo es.</span><span class="sxs-lookup"><span data-stu-id="04b5d-107">The sections that follow provide a list of the circumstances where inference is possible, and examples of situations where it is not.</span></span>  
  
## <a name="successful-inference"></a><span data-ttu-id="04b5d-108">Inferencia correcta</span><span class="sxs-lookup"><span data-stu-id="04b5d-108">Successful Inference</span></span>  
  
#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a><span data-ttu-id="04b5d-109">Los tipos anónimos pueden inferir nombres y tipos de propiedad de los orígenes siguientes:</span><span class="sxs-lookup"><span data-stu-id="04b5d-109">Anonymous types can infer property names and types from the following sources:</span></span>  
  
-   <span data-ttu-id="04b5d-110">Nombres de variables.</span><span class="sxs-lookup"><span data-stu-id="04b5d-110">From variable names.</span></span> <span data-ttu-id="04b5d-111">El tipo anónimo `anonProduct` tendrá dos propiedades, `productName` y `productPrice`.</span><span class="sxs-lookup"><span data-stu-id="04b5d-111">Anonymous type `anonProduct` will have two properties, `productName` and `productPrice`.</span></span> <span data-ttu-id="04b5d-112">Sus tipos de datos serán los de las variables originales, `String` y `Double`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="04b5d-112">Their data types will be those of the original variables, `String` and `Double`, respectively.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#11](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_2.vb)]  
  
-   <span data-ttu-id="04b5d-113">Nombres de campo o propiedad de otros objetos.</span><span class="sxs-lookup"><span data-stu-id="04b5d-113">From property or field names of other objects.</span></span> <span data-ttu-id="04b5d-114">Por ejemplo, considere un objeto `car` de un tipo `CarClass` que incluya las propiedades `Name` y `ID` .</span><span class="sxs-lookup"><span data-stu-id="04b5d-114">For example, consider a `car` object of a `CarClass` type that includes `Name` and `ID` properties.</span></span> <span data-ttu-id="04b5d-115">Para crear una nueva instancia de tipo anónimo, `car1`, con las propiedades `Name` y `ID` que se inicializan con los valores del objeto `car` , puede escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04b5d-115">To create a new anonymous type instance, `car1`, with `Name` and `ID` properties that are initialized with the values from the `car` object, you can write the following:</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#34](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_3.vb)]  
  
     <span data-ttu-id="04b5d-116">La declaración anterior es equivalente a la línea más larga de código que define el tipo anónimo `car2`.</span><span class="sxs-lookup"><span data-stu-id="04b5d-116">The previous declaration is equivalent to the longer line of code that defines anonymous type `car2`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#35](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_4.vb)]  
  
-   <span data-ttu-id="04b5d-117">Nombres de miembros XML.</span><span class="sxs-lookup"><span data-stu-id="04b5d-117">From XML member names.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#12](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_5.vb)]  
  
     <span data-ttu-id="04b5d-118">El tipo resultante de `anon` tendría una propiedad, `Book`, del tipo <xref:System.Collections.IEnumerable>(de XElement).</span><span class="sxs-lookup"><span data-stu-id="04b5d-118">The resulting type for `anon` would have one property, `Book`, of type <xref:System.Collections.IEnumerable>(Of XElement).</span></span>  
  
-   <span data-ttu-id="04b5d-119">Una función sin parámetros, como `SomeFunction` en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="04b5d-119">From a function that has no parameters, such as `SomeFunction` in the following example.</span></span>  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     <span data-ttu-id="04b5d-120">La variable `anon2` en el código siguiente es un tipo anónimo que tiene una propiedad, un carácter denominado `First`.</span><span class="sxs-lookup"><span data-stu-id="04b5d-120">The variable `anon2` in the following code is an anonymous type that has one property, a character named `First`.</span></span> <span data-ttu-id="04b5d-121">Este código mostrará una letra "E", la letra que devuelve la función <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="04b5d-121">This code will display a letter "E," the letter that is returned by function <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#13](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_6.vb)]  
  
## <a name="inference-failures"></a><span data-ttu-id="04b5d-122">Errores de inferencia</span><span class="sxs-lookup"><span data-stu-id="04b5d-122">Inference Failures</span></span>  
  
#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a><span data-ttu-id="04b5d-123">Se producirá un error en la inferencia de nombre en muchas circunstancias, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="04b5d-123">Name inference will fail in many circumstances, including the following:</span></span>  
  
-   <span data-ttu-id="04b5d-124">La inferencia se deriva de la invocación de un método, un constructor o una propiedad con parámetros que requiere argumentos.</span><span class="sxs-lookup"><span data-stu-id="04b5d-124">The inference derives from the invocation of a method, a constructor, or a parameterized property that requires arguments.</span></span> <span data-ttu-id="04b5d-125">La declaración anterior de `anon1` genera un error si `someFunction` tiene uno o más argumentos.</span><span class="sxs-lookup"><span data-stu-id="04b5d-125">The previous declaration of `anon1` fails if `someFunction` has one or more arguments.</span></span>  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     <span data-ttu-id="04b5d-126">La asignación a un nuevo nombre de propiedad resuelve el problema.</span><span class="sxs-lookup"><span data-stu-id="04b5d-126">Assignment to a new property name solves the problem.</span></span>  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   <span data-ttu-id="04b5d-127">La inferencia se deriva de una expresión compleja.</span><span class="sxs-lookup"><span data-stu-id="04b5d-127">The inference derives from a complex expression.</span></span>  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     <span data-ttu-id="04b5d-128">El error se puede resolver asignando el resultado de la expresión a un nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="04b5d-128">The error can be resolved by assigning the result of the expression to a property name.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#14](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_7.vb)]  
  
-   <span data-ttu-id="04b5d-129">La inferencia de varias propiedades genera dos o más propiedades con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="04b5d-129">Inference for multiple properties produces two or more properties that have the same name.</span></span> <span data-ttu-id="04b5d-130">Si nos referimos a las declaraciones de los ejemplos anteriores, no se pueden mostrar `product.Name` y `car1.Name` como propiedades del mismo tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="04b5d-130">Referring back to declarations in earlier examples, you cannot list both `product.Name` and `car1.Name` as properties of the same anonymous type.</span></span> <span data-ttu-id="04b5d-131">Esto se debe a que el identificador inferido de cada uno de ellos sería `Name`.</span><span class="sxs-lookup"><span data-stu-id="04b5d-131">This is because the inferred identifier for each of these would be `Name`.</span></span>  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     <span data-ttu-id="04b5d-132">El problema puede resolverse asignando los valores a distintos nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="04b5d-132">The problem can be solved by assigning the values to distinct property names.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#36](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_8.vb)]  
  
     <span data-ttu-id="04b5d-133">Observe que los cambios entre mayúsculas y minúsculas no forman dos nombres distintos.</span><span class="sxs-lookup"><span data-stu-id="04b5d-133">Note that changes in case (changes between uppercase and lowercase letters) do not make two names distinct.</span></span>  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   <span data-ttu-id="04b5d-134">El tipo y el valor iniciales de una propiedad dependen de otra propiedad que todavía no está establecida.</span><span class="sxs-lookup"><span data-stu-id="04b5d-134">The initial type and value of one property depends on another property that is not yet established.</span></span> <span data-ttu-id="04b5d-135">Por ejemplo, `.IDName = .LastName` no es válido en una declaración de tipo anónimo, a menos que `.LastName` ya esté inicializado.</span><span class="sxs-lookup"><span data-stu-id="04b5d-135">For example, `.IDName = .LastName` is not valid in an anonymous type declaration unless `.LastName` is already initialized.</span></span>  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     <span data-ttu-id="04b5d-136">En este ejemplo, puede corregir el problema invirtiendo el orden en que las propiedades están declaradas.</span><span class="sxs-lookup"><span data-stu-id="04b5d-136">In this example, you can fix the problem by reversing the order in which the properties are declared.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#15](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_9.vb)]  
  
-   <span data-ttu-id="04b5d-137">Un nombre de propiedad del tipo anónimo es igual que el nombre de un miembro de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="04b5d-137">A property name of the anonymous type is the same as the name of a member of <xref:System.Object>.</span></span> <span data-ttu-id="04b5d-138">Por ejemplo, la siguiente declaración genera un error porque `Equals` es un método de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="04b5d-138">For example, the following declaration fails because `Equals` is a method of <xref:System.Object>.</span></span>  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     <span data-ttu-id="04b5d-139">Puede corregir el problema cambiando el nombre de propiedad:</span><span class="sxs-lookup"><span data-stu-id="04b5d-139">You can fix the problem by changing the property name:</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#16](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_10.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04b5d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="04b5d-140">See Also</span></span>  
 [<span data-ttu-id="04b5d-141">Inicializadores de objeto: Tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="04b5d-141">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="04b5d-142">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="04b5d-142">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="04b5d-143">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="04b5d-143">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="04b5d-144">Key</span><span class="sxs-lookup"><span data-stu-id="04b5d-144">Key</span></span>](../../../../visual-basic/language-reference/modifiers/key.md)
