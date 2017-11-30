---
title: Uso eficiente de tipos de datos (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e13a1d61aacb06eb336c39aab969847127dfc67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="f3727-102">Uso eficiente de tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3727-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="f3727-103">Las variables no declaradas y las variables declaradas sin un tipo de datos se les asigna el `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f3727-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="f3727-104">Esto resulta muy sencillo escribir programas rápidamente, pero puede hacer que se ejecute más lentamente.</span><span class="sxs-lookup"><span data-stu-id="f3727-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="f3727-105">Establecimiento inflexible tipos</span><span class="sxs-lookup"><span data-stu-id="f3727-105">Strong Typing</span></span>  
 <span data-ttu-id="f3727-106">Especificar los tipos de datos para todas las variables se conoce como *establecimiento inflexible de tipos*.</span><span class="sxs-lookup"><span data-stu-id="f3727-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="f3727-107">Uso de establecimiento inflexible de tipos tiene varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="f3727-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="f3727-108">Habilita la compatibilidad con IntelliSense para las variables.</span><span class="sxs-lookup"><span data-stu-id="f3727-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="f3727-109">Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.</span><span class="sxs-lookup"><span data-stu-id="f3727-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="f3727-110">Aprovecha las ventajas de la comprobación de tipos de compilador.</span><span class="sxs-lookup"><span data-stu-id="f3727-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="f3727-111">Esto detecta las instrucciones que pueden producir un error en tiempo de ejecución debido a errores, como el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="f3727-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="f3727-112">También detecta llamadas a métodos en objetos que no las admiten.</span><span class="sxs-lookup"><span data-stu-id="f3727-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="f3727-113">Se produce una ejecución más rápida del código.</span><span class="sxs-lookup"><span data-stu-id="f3727-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="f3727-114">Tipos de datos más eficaces</span><span class="sxs-lookup"><span data-stu-id="f3727-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="f3727-115">Para las variables que contienen nunca valores decimales, los tipos de datos enteros son más eficaces que los tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="f3727-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="f3727-116">En [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], `Integer` y `UInteger` son los tipos numéricos más eficaces.</span><span class="sxs-lookup"><span data-stu-id="f3727-116">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="f3727-117">Para los números fraccionarios, `Double` es el tipo de datos más eficaz, porque los procesadores en las plataformas actuales realizan operaciones de punto flotante de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="f3727-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="f3727-118">Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f3727-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="f3727-119">Especificar el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3727-119">Specifying Data Type</span></span>  
 <span data-ttu-id="f3727-120">Use la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="f3727-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="f3727-121">Al mismo tiempo, puede especificar su nivel de acceso mediante el [público](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3727-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="f3727-122">Conversión de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3727-122">Character Conversion</span></span>  
 <span data-ttu-id="f3727-123">El `AscW` y `ChrW` funcionan en Unicode.</span><span class="sxs-lookup"><span data-stu-id="f3727-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="f3727-124">Se deben utilizar en lugar de a `Asc` y `Chr`, que debe traducir dentro y fuera de Unicode.</span><span class="sxs-lookup"><span data-stu-id="f3727-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3727-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3727-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="f3727-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f3727-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="f3727-127">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="f3727-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="f3727-128">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="f3727-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="f3727-129">Usar IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f3727-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
