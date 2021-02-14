---
description: 'Más información sobre: conceptos básicos de cadenas en Visual Basic'
title: Fundamentos de las cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 25d76ee177e5b3eaaa8aa6b2b1b1787dc29095a1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424364"
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="291e3-103">Fundamentos de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="291e3-103">String Basics in Visual Basic</span></span>

<span data-ttu-id="291e3-104">El tipo de datos de `String` representa una serie de caracteres (y cada uno de ellos representa a su vez una instancia del tipo de datos `Char`).</span><span class="sxs-lookup"><span data-stu-id="291e3-104">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="291e3-105">En este tema se presentan los conceptos básicos de las cadenas de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="291e3-105">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="291e3-106">Variables de cadena</span><span class="sxs-lookup"><span data-stu-id="291e3-106">String Variables</span></span>  

 <span data-ttu-id="291e3-107">A una instancia de una cadena se le puede asignar un valor literal que represente una serie de caracteres.</span><span class="sxs-lookup"><span data-stu-id="291e3-107">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="291e3-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="291e3-108">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 <span data-ttu-id="291e3-109">Una variable `String` también puede aceptar cualquier expresión que se evalúe como una cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-109">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="291e3-110">A continuación se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="291e3-110">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 <span data-ttu-id="291e3-111">Cualquier literal que se asigna a una variable `String` debe ir entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="291e3-111">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="291e3-112">Esto significa que una comilla contenida en una cadena no se puede representar mediante una comilla.</span><span class="sxs-lookup"><span data-stu-id="291e3-112">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="291e3-113">Por ejemplo, el código siguiente causa un error del compilador:</span><span class="sxs-lookup"><span data-stu-id="291e3-113">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 <span data-ttu-id="291e3-114">Este código provoca un error porque el compilador termina la cadena después de la segunda comilla, y el resto de la cadena se interpreta como código.</span><span class="sxs-lookup"><span data-stu-id="291e3-114">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="291e3-115">Para solucionar este problema, Visual Basic interpreta dos comillas en un literal de cadena como una comilla en la cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-115">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="291e3-116">En el ejemplo siguiente se muestra la forma correcta de incluir una comilla en una cadena:</span><span class="sxs-lookup"><span data-stu-id="291e3-116">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 <span data-ttu-id="291e3-117">En el ejemplo anterior, las dos comillas que preceden a la palabra `Look` se convierten en una comilla en la cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-117">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="291e3-118">Las tres comillas al final de la línea representan una comilla en la cadena y un carácter de terminación de cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-118">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="291e3-119">Los literales de cadena pueden contener varias líneas:</span><span class="sxs-lookup"><span data-stu-id="291e3-119">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="291e3-120">La cadena resultante contiene secuencias de nueva línea que usó en el literal de cadena (vbcr, vbcrlf, etc.).</span><span class="sxs-lookup"><span data-stu-id="291e3-120">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="291e3-121">La solución anterior ya no es necesaria:</span><span class="sxs-lookup"><span data-stu-id="291e3-121">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="291e3-122">Caracteres en cadenas</span><span class="sxs-lookup"><span data-stu-id="291e3-122">Characters in Strings</span></span>  

 <span data-ttu-id="291e3-123">Una cadena puede considerarse como una serie de valores `Char` y el tipo `String` tiene funciones integradas que permiten realizar muchas manipulaciones en una cadena similares a las permitidas por las matrices.</span><span class="sxs-lookup"><span data-stu-id="291e3-123">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="291e3-124">Al igual que todas las matrices de .NET Framework, son matrices de base cero.</span><span class="sxs-lookup"><span data-stu-id="291e3-124">Like all array in .NET Framework, these are zero-based arrays.</span></span> <span data-ttu-id="291e3-125">Puede hacer referencia a un carácter específico de una cadena con la propiedad `Chars`, que proporciona una forma de acceso a un carácter mediante la posición en la que este aparece en la cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-125">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="291e3-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="291e3-126">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 <span data-ttu-id="291e3-127">En el ejemplo anterior, la propiedad `Chars` de la cadena devuelve el cuarto carácter de la cadena, que es `D`, y lo asigna a `myChar`.</span><span class="sxs-lookup"><span data-stu-id="291e3-127">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="291e3-128">También puede obtener la longitud de una cadena concreta mediante la propiedad `Length`.</span><span class="sxs-lookup"><span data-stu-id="291e3-128">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="291e3-129">Si necesita realizar varias manipulaciones de tipo de matriz en una cadena, puede convertirla en una matriz de instancias de `Char` usando la función `ToCharArray` de la cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-129">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="291e3-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="291e3-130">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 <span data-ttu-id="291e3-131">La variable `myArray` contiene ahora una matriz de valores `Char` y cada uno representa un carácter de `myString`.</span><span class="sxs-lookup"><span data-stu-id="291e3-131">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="291e3-132">Inmutabilidad de cadenas</span><span class="sxs-lookup"><span data-stu-id="291e3-132">The Immutability of Strings</span></span>  

 <span data-ttu-id="291e3-133">Una cadena es *inmutable*, lo que significa que su valor no se puede cambiar una vez que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="291e3-133">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="291e3-134">Sin embargo, esto no impide asignar más de un valor a una variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-134">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="291e3-135">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="291e3-135">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 <span data-ttu-id="291e3-136">Aquí se crea una variable de cadena con un valor y, a continuación, se cambia su valor. </span><span class="sxs-lookup"><span data-stu-id="291e3-136">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="291e3-137">Más concretamente, en la primera línea, se crea una instancia de tipo `String` y se le asigna el valor `This string is immutable`.</span><span class="sxs-lookup"><span data-stu-id="291e3-137">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="291e3-138">En la segunda línea del ejemplo se crea una nueva instancia y se le asigna el valor `Or is it?`, y la variable de cadena descarta su referencia a la primera instancia y almacena una referencia a la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="291e3-138">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="291e3-139">A diferencia de otros tipos de datos intrínsecos, `String` es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="291e3-139">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="291e3-140">Cuando una variable de tipo de referencia se pasa como argumento a una función o subrutina, se pasa una referencia a la dirección de memoria donde se almacenan los datos en lugar del valor real de la cadena.</span><span class="sxs-lookup"><span data-stu-id="291e3-140">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="291e3-141">Así, en el ejemplo anterior, el nombre de la variable sigue siendo el mismo, pero apunta a una nueva instancia diferente de la clase `String`, que contiene el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="291e3-141">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="291e3-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="291e3-142">See also</span></span>

- [<span data-ttu-id="291e3-143">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="291e3-143">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="291e3-144">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="291e3-144">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="291e3-145">Tipo de datos Char</span><span class="sxs-lookup"><span data-stu-id="291e3-145">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="291e3-146">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="291e3-146">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
