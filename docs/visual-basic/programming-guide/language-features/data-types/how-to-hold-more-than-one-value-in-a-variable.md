---
title: Procedimiento Contener más de un valor en una variable (Visual Basic)
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
ms.openlocfilehash: 8d07a34a98303f9d220dba0a3c955120b421340e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054196"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="e7a36-102">Procedimiento Contener más de un valor en una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7a36-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="e7a36-103">Una variable contiene más de un valor si se declara como un *tipo de datos compuesto*.</span><span class="sxs-lookup"><span data-stu-id="e7a36-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="e7a36-104">Los [tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) incluyen estructuras, matrices y clases.</span><span class="sxs-lookup"><span data-stu-id="e7a36-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="e7a36-105">Una variable de un tipo de datos compuesto puede contener una combinación de tipos de datos básicos y otros tipos compuestos.</span><span class="sxs-lookup"><span data-stu-id="e7a36-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="e7a36-106">Las estructuras y las clases pueden contener código y datos.</span><span class="sxs-lookup"><span data-stu-id="e7a36-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="e7a36-107">Para contener más de un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="e7a36-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="e7a36-108">Determine qué tipo de datos compuesto desea usar para la variable.</span><span class="sxs-lookup"><span data-stu-id="e7a36-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="e7a36-109">Si el tipo de datos compuesto todavía no está definido, debe definirlo para que la variable pueda usarlo.</span><span class="sxs-lookup"><span data-stu-id="e7a36-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="e7a36-110">Defina una estructura con una [instrucción Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="e7a36-111">Defina una matriz con una [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="e7a36-112">Defina una clase con una [instrucción de clase](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="e7a36-113">Declare la variable con `Dim` una instrucción.</span><span class="sxs-lookup"><span data-stu-id="e7a36-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="e7a36-114">Siga el nombre de la variable `As` con una cláusula.</span><span class="sxs-lookup"><span data-stu-id="e7a36-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="e7a36-115">Siga la `As` palabra clave con el nombre del tipo de datos compuesto adecuado.</span><span class="sxs-lookup"><span data-stu-id="e7a36-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7a36-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7a36-116">See also</span></span>

- [<span data-ttu-id="e7a36-117">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e7a36-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e7a36-118">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="e7a36-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="e7a36-119">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="e7a36-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="e7a36-120">Estructuras</span><span class="sxs-lookup"><span data-stu-id="e7a36-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e7a36-121">Matrices</span><span class="sxs-lookup"><span data-stu-id="e7a36-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e7a36-122">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="e7a36-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="e7a36-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="e7a36-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
