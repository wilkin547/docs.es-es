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
ms.openlocfilehash: 0b517bca3a9e296eb891e30df91c1d32eb357432
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830128"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="5e9fd-102">Uso eficiente de tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e9fd-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="5e9fd-103">Las variables no declaradas y las variables declaradas sin un tipo de datos se asignan los `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="5e9fd-104">Esto resulta muy fácil escribir programas rápidamente, pero puede hacer que se ejecute más lentamente.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="5e9fd-105">Permite establecer tipado fuerte</span><span class="sxs-lookup"><span data-stu-id="5e9fd-105">Strong Typing</span></span>  
 <span data-ttu-id="5e9fd-106">Especificar los tipos de datos para todas las variables se conoce como *establecimiento inflexible de tipos*.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="5e9fd-107">Uso de establecimiento inflexible de tipos tiene varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="5e9fd-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="5e9fd-108">Habilita la compatibilidad con IntelliSense para las variables.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="5e9fd-109">Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="5e9fd-110">Aprovecha de la comprobación de tipos del compilador.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="5e9fd-111">Esto detecta las instrucciones que se pueden producir un error en tiempo de ejecución debido a errores, como el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="5e9fd-112">También detecta llamadas a métodos en objetos que no las admiten.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="5e9fd-113">Se produce una ejecución más rápida del código.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="5e9fd-114">Tipos de datos más eficaces</span><span class="sxs-lookup"><span data-stu-id="5e9fd-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="5e9fd-115">Para las variables que no contienen nunca fracciones, los tipos de datos enteros son más eficaces que los tipos no integrales.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="5e9fd-116">En Visual Basic, `Integer` y `UInteger` son los tipos numéricos más eficaces.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="5e9fd-117">Para números fraccionarios, `Double` es el tipo de datos más eficaz, ya que los procesadores de plataformas actuales realizan operaciones de punto flotante de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="5e9fd-118">Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="5e9fd-119">Especifica el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5e9fd-119">Specifying Data Type</span></span>  
 <span data-ttu-id="5e9fd-120">Use la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="5e9fd-121">Al mismo tiempo, puede especificar su nivel de acceso mediante la [pública](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="5e9fd-122">Conversión de caracteres</span><span class="sxs-lookup"><span data-stu-id="5e9fd-122">Character Conversion</span></span>  
 <span data-ttu-id="5e9fd-123">El `AscW` y `ChrW` funciones funcionan en Unicode.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="5e9fd-124">Se deben usar en `Asc` y `Chr`, que se debe traducir dentro y fuera de Unicode.</span><span class="sxs-lookup"><span data-stu-id="5e9fd-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9fd-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9fd-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="5e9fd-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5e9fd-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="5e9fd-127">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="5e9fd-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="5e9fd-128">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="5e9fd-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="5e9fd-129">Usar IntelliSense</span><span class="sxs-lookup"><span data-stu-id="5e9fd-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
