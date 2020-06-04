---
title: Comentarios en código
ms.date: 07/20/2015
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
ms.openlocfilehash: b50e76b8f832c3a214ca54f97bab8b0b6789ac25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403322"
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="8c6f7-102">Comentarios en el código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c6f7-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="8c6f7-103">Cuando lea ejemplos de código, encontrará el símbolo de comentario (`'`).</span><span class="sxs-lookup"><span data-stu-id="8c6f7-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="8c6f7-104">Este símbolo indica al compilador de Visual Basic que omita el texto que le sigue o el *Comentario*.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-104">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="8c6f7-105">Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="8c6f7-106">Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento (lo que hace).</span><span class="sxs-lookup"><span data-stu-id="8c6f7-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="8c6f7-107">Esto ayuda al desarrollador y a los que puedan examinar el código.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="8c6f7-108">Debería separar los detalles de implementación (cómo lo hace el procedimiento) de los comentarios que describen las características funcionales.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="8c6f7-109">Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="8c6f7-110">Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="8c6f7-111">Ambas opciones quedan reflejadas en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 <span data-ttu-id="8c6f7-112">Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c6f7-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="8c6f7-113">Instrucciones sobre los comentarios</span><span class="sxs-lookup"><span data-stu-id="8c6f7-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="8c6f7-114">La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="8c6f7-115">Estas son sugerencias; Visual Basic no aplica reglas para agregar comentarios.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-115">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="8c6f7-116">Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="8c6f7-117">Tipo de comentario</span><span class="sxs-lookup"><span data-stu-id="8c6f7-117">Comment type</span></span>|<span data-ttu-id="8c6f7-118">Descripción del comentario</span><span class="sxs-lookup"><span data-stu-id="8c6f7-118">Comment description</span></span>|  
|<span data-ttu-id="8c6f7-119">Propósito</span><span class="sxs-lookup"><span data-stu-id="8c6f7-119">Purpose</span></span>|<span data-ttu-id="8c6f7-120">Describe qué hace el procedimiento (no cómo lo hace).</span><span class="sxs-lookup"><span data-stu-id="8c6f7-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="8c6f7-121">Suposiciones</span><span class="sxs-lookup"><span data-stu-id="8c6f7-121">Assumptions</span></span>|<span data-ttu-id="8c6f7-122">Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="8c6f7-123">Efectos</span><span class="sxs-lookup"><span data-stu-id="8c6f7-123">Effects</span></span>|<span data-ttu-id="8c6f7-124">Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen (únicamente si no es evidente).</span><span class="sxs-lookup"><span data-stu-id="8c6f7-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="8c6f7-125">Entradas</span><span class="sxs-lookup"><span data-stu-id="8c6f7-125">Inputs</span></span>|<span data-ttu-id="8c6f7-126">Especifica el propósito del argumento.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="8c6f7-127">Devuelve</span><span class="sxs-lookup"><span data-stu-id="8c6f7-127">Returns</span></span>|<span data-ttu-id="8c6f7-128">Explica los valores que devuelve el procedimiento</span><span class="sxs-lookup"><span data-stu-id="8c6f7-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="8c6f7-129">Recuerde los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="8c6f7-129">Remember the following points:</span></span>  
  
- <span data-ttu-id="8c6f7-130">Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
- <span data-ttu-id="8c6f7-131">Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
- <span data-ttu-id="8c6f7-132">Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="8c6f7-133">Para agregar o quitar símbolos de comentario de un bloque de código, seleccione una o varias líneas de código y elija el **Comentario** ( ![ el Visual Basic botón de comentario en Visual Studio ](./media/comments-in-code/visual-basic-comment-button.gif) ) y **Quite los comentarios** ( ![ el botón Visual Basic quitar comentarios de Visual Studio ](./media/comments-in-code/visual-basic-uncomment-button.gif) ) en la barra de herramientas de **edición** .</span><span class="sxs-lookup"><span data-stu-id="8c6f7-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c6f7-134">También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="8c6f7-135">Sin embargo, los `'` botones de símbolo y de **Comentario** / **Uncomment** son más fáciles de usar y requieren menos espacio y memoria.</span><span class="sxs-lookup"><span data-stu-id="8c6f7-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6f7-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c6f7-136">See also</span></span>

- [<span data-ttu-id="8c6f7-137">Instinto básico: documentar el código con comentarios XML</span><span class="sxs-lookup"><span data-stu-id="8c6f7-137">Basic Instincts - Documenting Your Code With XML Comments</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [<span data-ttu-id="8c6f7-138">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="8c6f7-138">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)
- [<span data-ttu-id="8c6f7-139">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="8c6f7-139">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)
- [<span data-ttu-id="8c6f7-140">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="8c6f7-140">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="8c6f7-141">Instrucción REM</span><span class="sxs-lookup"><span data-stu-id="8c6f7-141">REM Statement</span></span>](../../language-reference/statements/rem-statement.md)
