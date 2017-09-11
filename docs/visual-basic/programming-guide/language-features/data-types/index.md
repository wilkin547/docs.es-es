---
title: Tipos de datos en Visual Basic
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b90a5e58d135a3769761ca431fd0c05f79e045f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="data-types-in-visual-basic"></a><span data-ttu-id="dff4c-102">Tipos de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dff4c-102">Data Types in Visual Basic</span></span>
<span data-ttu-id="dff4c-103">El *tipo de datos* de un elemento de programación hace referencia al tipo de datos que puede contener y cómo almacena los datos.</span><span class="sxs-lookup"><span data-stu-id="dff4c-103">The *data type* of a programming element refers to what kind of data it can hold and how it stores that data.</span></span> <span data-ttu-id="dff4c-104">Los tipos de datos se aplican a todos los valores que se pueden almacenar en la memoria del equipo o participar en la evaluación de una expresión.</span><span class="sxs-lookup"><span data-stu-id="dff4c-104">Data types apply to all values that can be stored in computer memory or participate in the evaluation of an expression.</span></span> <span data-ttu-id="dff4c-105">Cada variable, literal, constante, enumeración, propiedad, parámetro de procedimiento, argumento de procedimiento y valor devuelto de un procedimiento tiene un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dff4c-105">Every variable, literal, constant, enumeration, property, procedure parameter, procedure argument, and procedure return value has a data type.</span></span>  
  
## <a name="declared-data-types"></a><span data-ttu-id="dff4c-106">Tipos de datos declarados</span><span class="sxs-lookup"><span data-stu-id="dff4c-106">Declared Data Types</span></span>  
 <span data-ttu-id="dff4c-107">Define un elemento de programación con una instrucción de declaración y especifica su tipo de datos con la cláusula `As`.</span><span class="sxs-lookup"><span data-stu-id="dff4c-107">You define a programming element with a declaration statement, and you specify its data type with the `As` clause.</span></span> <span data-ttu-id="dff4c-108">En la tabla siguiente se muestran las instrucciones que usa para declarar diversos elementos.</span><span class="sxs-lookup"><span data-stu-id="dff4c-108">The following table shows the statements you use to declare various elements.</span></span>  
  
|<span data-ttu-id="dff4c-109">Elemento de programación</span><span class="sxs-lookup"><span data-stu-id="dff4c-109">Programming element</span></span>|<span data-ttu-id="dff4c-110">Declaración de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="dff4c-110">Data type declaration</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="dff4c-111">Variable</span><span class="sxs-lookup"><span data-stu-id="dff4c-111">Variable</span></span>|<span data-ttu-id="dff4c-112">En una [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-112">In a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)</span></span><br /><br /> <span data-ttu-id="dff4c-113">`Dim`   `amount As Double`</span><span class="sxs-lookup"><span data-stu-id="dff4c-113">`Dim`   `amount As Double`</span></span><br /><br /> <span data-ttu-id="dff4c-114">`Static`   `yourName As String`</span><span class="sxs-lookup"><span data-stu-id="dff4c-114">`Static`   `yourName As String`</span></span><br /><br /> <span data-ttu-id="dff4c-115">`Public`   `billsPaid As Decimal = 0`</span><span class="sxs-lookup"><span data-stu-id="dff4c-115">`Public`   `billsPaid As Decimal = 0`</span></span>|  
|<span data-ttu-id="dff4c-116">Literal</span><span class="sxs-lookup"><span data-stu-id="dff4c-116">Literal</span></span>|<span data-ttu-id="dff4c-117">Con un carácter de tipo literal; consulte "Caracteres de tipo literal" en [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-117">With a literal type character; see "Literal Type Characters" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span><br /><br /> <span data-ttu-id="dff4c-118">`Dim searchChar As Char = "."`  `C`</span><span class="sxs-lookup"><span data-stu-id="dff4c-118">`Dim searchChar As Char = "."`  `C`</span></span>|  
|<span data-ttu-id="dff4c-119">Constante</span><span class="sxs-lookup"><span data-stu-id="dff4c-119">Constant</span></span>|<span data-ttu-id="dff4c-120">En una [instrucción Const](../../../../visual-basic/language-reference/statements/const-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-120">In a [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)</span></span><br /><br /> <span data-ttu-id="dff4c-121">`Const`   `modulus As Single = 4.17825F`</span><span class="sxs-lookup"><span data-stu-id="dff4c-121">`Const`   `modulus As Single = 4.17825F`</span></span>|  
|<span data-ttu-id="dff4c-122">Enumeración</span><span class="sxs-lookup"><span data-stu-id="dff4c-122">Enumeration</span></span>|<span data-ttu-id="dff4c-123">En una [instrucción Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-123">In an [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)</span></span><br /><br /> <span data-ttu-id="dff4c-124">`Public`   `Enum`   `colors`</span><span class="sxs-lookup"><span data-stu-id="dff4c-124">`Public`   `Enum`   `colors`</span></span>|  
|<span data-ttu-id="dff4c-125">Propiedad</span><span class="sxs-lookup"><span data-stu-id="dff4c-125">Property</span></span>|<span data-ttu-id="dff4c-126">En una [instrucción Property](../../../../visual-basic/language-reference/statements/property-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-126">In a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)</span></span><br /><br /> <span data-ttu-id="dff4c-127">`Property`   `region() As String`</span><span class="sxs-lookup"><span data-stu-id="dff4c-127">`Property`   `region() As String`</span></span>|  
|<span data-ttu-id="dff4c-128">Parámetro de procedimiento</span><span class="sxs-lookup"><span data-stu-id="dff4c-128">Procedure parameter</span></span>|<span data-ttu-id="dff4c-129">En una [instrucción Sub](../../../../visual-basic/language-reference/statements/sub-statement.md), [instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md) o una [instrucción Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-129">In a [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md), or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="dff4c-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span><span class="sxs-lookup"><span data-stu-id="dff4c-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span></span>|  
|<span data-ttu-id="dff4c-131">Argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="dff4c-131">Procedure argument</span></span>|<span data-ttu-id="dff4c-132">En el código de llamada; cada argumento es un elemento de programación que ya se declaró, o bien una expresión que contiene los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="dff4c-132">In the calling code; each argument is a programming element that has already been declared, or an expression containing declared elements</span></span><br /><br /> <span data-ttu-id="dff4c-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span><span class="sxs-lookup"><span data-stu-id="dff4c-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span></span>|  
|<span data-ttu-id="dff4c-134">Valor devuelto de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="dff4c-134">Procedure return value</span></span>|<span data-ttu-id="dff4c-135">En una [instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md) o una [instrucción Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dff4c-135">In a [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="dff4c-136">`Function convert(ByVal b As Byte)`   `As String`</span><span class="sxs-lookup"><span data-stu-id="dff4c-136">`Function convert(ByVal b As Byte)`   `As String`</span></span>|  
  
 <span data-ttu-id="dff4c-137">Para ver una lista de los tipos de datos de Visual Basic, consulte [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="dff4c-137">For a list of Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff4c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="dff4c-138">See Also</span></span>  
 <span data-ttu-id="dff4c-139">[Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-139">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
 <span data-ttu-id="dff4c-140">[Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-140">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
 <span data-ttu-id="dff4c-141">[Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-141">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
 <span data-ttu-id="dff4c-142">[Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-142">[Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
 <span data-ttu-id="dff4c-143">[Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-143">[Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
 <span data-ttu-id="dff4c-144">[Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-144">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
 <span data-ttu-id="dff4c-145">[Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-145">[Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
 <span data-ttu-id="dff4c-146">[Tuplas](tuples.md)   </span><span class="sxs-lookup"><span data-stu-id="dff4c-146">[Tuples](tuples.md)   </span></span>  
 <span data-ttu-id="dff4c-147">[Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-147">[Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
 <span data-ttu-id="dff4c-148">[Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="dff4c-148">[Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
 [<span data-ttu-id="dff4c-149">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="dff4c-149">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

