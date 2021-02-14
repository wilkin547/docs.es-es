---
description: 'Más información acerca de: uso eficiente de tipos de datos (Visual Basic)'
title: Uso eficiente de los tipos de datos
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
ms.openlocfilehash: e7660bbdec530ef18d663975e314d90b64e4b055
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476441"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="ff715-103">Uso eficiente de tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff715-103">Efficient Use of Data Types (Visual Basic)</span></span>

<span data-ttu-id="ff715-104">A las variables no declaradas y a las variables declaradas sin un tipo de datos se les asigna el `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ff715-104">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="ff715-105">Esto facilita la escritura rápida de programas, pero puede hacer que se ejecuten más lentamente.</span><span class="sxs-lookup"><span data-stu-id="ff715-105">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="ff715-106">Establecimiento fuerte de tipos</span><span class="sxs-lookup"><span data-stu-id="ff715-106">Strong Typing</span></span>

 <span data-ttu-id="ff715-107">La especificación de tipos de datos para todas las variables se conoce como *fuertemente* tipados.</span><span class="sxs-lookup"><span data-stu-id="ff715-107">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="ff715-108">El uso de tipos fuertemente tipados tiene varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="ff715-108">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="ff715-109">Habilita la compatibilidad con IntelliSense para las variables.</span><span class="sxs-lookup"><span data-stu-id="ff715-109">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="ff715-110">Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.</span><span class="sxs-lookup"><span data-stu-id="ff715-110">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="ff715-111">Aprovecha la comprobación del tipo de compilador.</span><span class="sxs-lookup"><span data-stu-id="ff715-111">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="ff715-112">Esto detecta instrucciones que pueden producir errores en tiempo de ejecución debido a errores como el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="ff715-112">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="ff715-113">También detecta llamadas a métodos en objetos que no las admiten.</span><span class="sxs-lookup"><span data-stu-id="ff715-113">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="ff715-114">Esto da como resultado una ejecución más rápida del código.</span><span class="sxs-lookup"><span data-stu-id="ff715-114">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="ff715-115">Tipos de datos más eficaces</span><span class="sxs-lookup"><span data-stu-id="ff715-115">Most Efficient Data Types</span></span>

 <span data-ttu-id="ff715-116">En el caso de las variables que nunca contienen fracciones, los tipos de datos enteros son más eficaces que los tipos no enteros.</span><span class="sxs-lookup"><span data-stu-id="ff715-116">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="ff715-117">En Visual Basic, `Integer` y `UInteger` son los tipos numéricos más eficaces.</span><span class="sxs-lookup"><span data-stu-id="ff715-117">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="ff715-118">En el caso de los números fraccionarios, `Double` es el tipo de datos más eficaz, ya que los procesadores de las plataformas actuales realizan operaciones de punto flotante de doble precisión.</span><span class="sxs-lookup"><span data-stu-id="ff715-118">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="ff715-119">Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer` .</span><span class="sxs-lookup"><span data-stu-id="ff715-119">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="ff715-120">Especificar el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ff715-120">Specifying Data Type</span></span>

 <span data-ttu-id="ff715-121">Use la [instrucción Dim](../../../language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="ff715-121">Use the [Dim Statement](../../../language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="ff715-122">Puede especificar su nivel de acceso simultáneamente mediante la palabra clave [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)o [Private](../../../language-reference/modifiers/private.md) , como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff715-122">You can simultaneously specify its access level by using the [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), or [Private](../../../language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="ff715-123">Conversión de caracteres</span><span class="sxs-lookup"><span data-stu-id="ff715-123">Character Conversion</span></span>

 <span data-ttu-id="ff715-124">Las `AscW` `ChrW` funciones y funcionan en Unicode.</span><span class="sxs-lookup"><span data-stu-id="ff715-124">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="ff715-125">Debe utilizarlos en preferencia a `Asc` y `Chr` , que deben traducirse dentro y fuera de Unicode.</span><span class="sxs-lookup"><span data-stu-id="ff715-125">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff715-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff715-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="ff715-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ff715-127">Data Types</span></span>](index.md)
- [<span data-ttu-id="ff715-128">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="ff715-128">Numeric Data Types</span></span>](numeric-data-types.md)
- [<span data-ttu-id="ff715-129">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="ff715-129">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="ff715-130">Usar IntelliSense</span><span class="sxs-lookup"><span data-stu-id="ff715-130">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
