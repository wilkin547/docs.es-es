---
title: Uso eficiente de tipos de datos (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 68371a9f8d4dcc5d0a2b67955d5e88943a83b085
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631107"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="8d13f-102">Uso eficiente de tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d13f-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="8d13f-103">A las variables no declaradas y a las variables declaradas sin un tipo de datos se les asigna el tipo de `Object` datos.</span><span class="sxs-lookup"><span data-stu-id="8d13f-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="8d13f-104">Esto facilita la escritura rápida de programas, pero puede hacer que se ejecuten más lentamente.</span><span class="sxs-lookup"><span data-stu-id="8d13f-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="8d13f-105">Establecimiento fuerte de tipos</span><span class="sxs-lookup"><span data-stu-id="8d13f-105">Strong Typing</span></span>
 <span data-ttu-id="8d13f-106">La especificación de tipos de datos para todas las variables se conoce como *fuertemente*tipados.</span><span class="sxs-lookup"><span data-stu-id="8d13f-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="8d13f-107">El uso de tipos fuertemente tipados tiene varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="8d13f-107">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="8d13f-108">Habilita la compatibilidad con IntelliSense para las variables.</span><span class="sxs-lookup"><span data-stu-id="8d13f-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="8d13f-109">Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.</span><span class="sxs-lookup"><span data-stu-id="8d13f-109">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="8d13f-110">Aprovecha la comprobación del tipo de compilador.</span><span class="sxs-lookup"><span data-stu-id="8d13f-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="8d13f-111">Esto detecta instrucciones que pueden producir errores en tiempo de ejecución debido a errores como el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="8d13f-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="8d13f-112">También detecta llamadas a métodos en objetos que no las admiten.</span><span class="sxs-lookup"><span data-stu-id="8d13f-112">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="8d13f-113">Esto da como resultado una ejecución más rápida del código.</span><span class="sxs-lookup"><span data-stu-id="8d13f-113">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="8d13f-114">Tipos de datos más eficaces</span><span class="sxs-lookup"><span data-stu-id="8d13f-114">Most Efficient Data Types</span></span>
 <span data-ttu-id="8d13f-115">En el caso de las variables que nunca contienen fracciones, los tipos de datos enteros son más eficaces que los tipos no enteros.</span><span class="sxs-lookup"><span data-stu-id="8d13f-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="8d13f-116">En Visual Basic, `Integer` y `UInteger` son los tipos numéricos más eficaces.</span><span class="sxs-lookup"><span data-stu-id="8d13f-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="8d13f-117">En el caso de los `Double` números fraccionarios, es el tipo de datos más eficaz, ya que los procesadores de las plataformas actuales realizan operaciones de punto flotante de doble precisión.</span><span class="sxs-lookup"><span data-stu-id="8d13f-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="8d13f-118">Sin embargo, las `Double` operaciones con no son tan rápidas como con los tipos enteros `Integer`como.</span><span class="sxs-lookup"><span data-stu-id="8d13f-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="8d13f-119">Especificar el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d13f-119">Specifying Data Type</span></span>
 <span data-ttu-id="8d13f-120">Use la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="8d13f-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="8d13f-121">Puede especificar su nivel de acceso simultáneamente mediante la palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)o [Private](../../../../visual-basic/language-reference/modifiers/private.md) , como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d13f-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="8d13f-122">Conversión de caracteres</span><span class="sxs-lookup"><span data-stu-id="8d13f-122">Character Conversion</span></span>
 <span data-ttu-id="8d13f-123">Las `AscW` funciones `ChrW` y funcionan en Unicode.</span><span class="sxs-lookup"><span data-stu-id="8d13f-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="8d13f-124">Debe utilizarlos en preferencia a `Asc` y `Chr`, que deben traducirse dentro y fuera de Unicode.</span><span class="sxs-lookup"><span data-stu-id="8d13f-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d13f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d13f-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="8d13f-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8d13f-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="8d13f-127">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="8d13f-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="8d13f-128">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="8d13f-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="8d13f-129">Usar IntelliSense</span><span class="sxs-lookup"><span data-stu-id="8d13f-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
