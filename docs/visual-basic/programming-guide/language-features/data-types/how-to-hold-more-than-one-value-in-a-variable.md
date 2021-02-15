---
description: 'Más información acerca de cómo: contener más de un valor en una variable (Visual Basic)'
title: Procedimiento Inclusión de más de un valor en una variable
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 5248bc29f58cccf3b8ced95d3fba8f0d39033a83
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100484007"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="ba00b-103">Cómo: Contener más de un valor en una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba00b-103">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="ba00b-104">Una variable contiene más de un valor si se declara como un *tipo de datos compuesto*.</span><span class="sxs-lookup"><span data-stu-id="ba00b-104">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="ba00b-105">Los [tipos de datos compuestos](composite-data-types.md) incluyen estructuras, matrices y clases.</span><span class="sxs-lookup"><span data-stu-id="ba00b-105">[Composite Data Types](composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="ba00b-106">Una variable de un tipo de datos compuesto puede contener una combinación de tipos de datos básicos y otros tipos compuestos.</span><span class="sxs-lookup"><span data-stu-id="ba00b-106">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="ba00b-107">Las estructuras y las clases pueden contener código y datos.</span><span class="sxs-lookup"><span data-stu-id="ba00b-107">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="ba00b-108">Para contener más de un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="ba00b-108">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="ba00b-109">Determine qué tipo de datos compuesto desea usar para la variable.</span><span class="sxs-lookup"><span data-stu-id="ba00b-109">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="ba00b-110">Si el tipo de datos compuesto todavía no está definido, debe definirlo para que la variable pueda usarlo.</span><span class="sxs-lookup"><span data-stu-id="ba00b-110">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="ba00b-111">Defina una estructura con una [instrucción Structure](../../../language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ba00b-111">Define a structure with a [Structure Statement](../../../language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="ba00b-112">Defina una matriz con una [instrucción Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ba00b-112">Define an array with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="ba00b-113">Defina una clase con una [instrucción de clase](../../../language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ba00b-113">Define a class with a [Class Statement](../../../language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="ba00b-114">Declare la variable con una `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ba00b-114">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="ba00b-115">Siga el nombre de la variable con una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ba00b-115">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="ba00b-116">Siga la `As` palabra clave con el nombre del tipo de datos compuesto adecuado.</span><span class="sxs-lookup"><span data-stu-id="ba00b-116">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba00b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba00b-117">See also</span></span>

- [<span data-ttu-id="ba00b-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ba00b-118">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="ba00b-119">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="ba00b-119">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="ba00b-120">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="ba00b-120">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="ba00b-121">Estructuras</span><span class="sxs-lookup"><span data-stu-id="ba00b-121">Structures</span></span>](structures.md)
- [<span data-ttu-id="ba00b-122">Matrices</span><span class="sxs-lookup"><span data-stu-id="ba00b-122">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="ba00b-123">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="ba00b-123">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="ba00b-124">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="ba00b-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
