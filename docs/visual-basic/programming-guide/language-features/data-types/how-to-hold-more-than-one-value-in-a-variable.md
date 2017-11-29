---
title: "Cómo: Contener más de un valor en una variable (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c8c567ec2ba01d094819c98a2937af75cd105956
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="e4750-102">Cómo: Contener más de un valor en una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4750-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="e4750-103">Una variable contiene más de un valor si se declara como de un *tipo de datos compuesto*.</span><span class="sxs-lookup"><span data-stu-id="e4750-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="e4750-104">[Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) incluyen estructuras, matrices y clases.</span><span class="sxs-lookup"><span data-stu-id="e4750-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="e4750-105">Una variable de un tipo de datos compuesto puede contener una combinación de tipos de datos básicos y otros tipos compuestos.</span><span class="sxs-lookup"><span data-stu-id="e4750-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="e4750-106">Estructuras y clases pueden contener código, así como datos.</span><span class="sxs-lookup"><span data-stu-id="e4750-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="e4750-107">Para contener más de un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="e4750-107">To hold more than one value in a variable</span></span>  
  
1.  <span data-ttu-id="e4750-108">Determinar el tipo de datos compuestos que desea usar para la variable.</span><span class="sxs-lookup"><span data-stu-id="e4750-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2.  <span data-ttu-id="e4750-109">Si aún no se ha definido el tipo de datos compuesto, definirlo para que pueda utilizar la variable.</span><span class="sxs-lookup"><span data-stu-id="e4750-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="e4750-110">Definir una estructura con un [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e4750-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="e4750-111">Definir una matriz con un [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e4750-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="e4750-112">Definir una clase con un [Class (instrucción)](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e4750-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3.  <span data-ttu-id="e4750-113">Declare la variable con un `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e4750-113">Declare your variable with a `Dim` statement.</span></span>  
  
4.  <span data-ttu-id="e4750-114">Siga el nombre de variable con un `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e4750-114">Follow the variable name with an `As` clause.</span></span>  
  
5.  <span data-ttu-id="e4750-115">Siga el `As` palabra clave con el nombre del tipo de datos compuesto adecuado.</span><span class="sxs-lookup"><span data-stu-id="e4750-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4750-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4750-116">See Also</span></span>  
 [<span data-ttu-id="e4750-117">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e4750-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="e4750-118">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="e4750-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="e4750-119">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="e4750-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="e4750-120">Estructuras</span><span class="sxs-lookup"><span data-stu-id="e4750-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="e4750-121">Matrices</span><span class="sxs-lookup"><span data-stu-id="e4750-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="e4750-122">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="e4750-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="e4750-123">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="e4750-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
