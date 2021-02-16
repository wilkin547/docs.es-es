---
description: 'Más información sobre: comentarios en el código (Visual Basic)'
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
ms.openlocfilehash: 66e12a18c2532bb5b694affccb84153f01bcddd5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461936"
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="5c190-103">Comentarios en el código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c190-103">Comments in Code (Visual Basic)</span></span>

<span data-ttu-id="5c190-104">Cuando lea ejemplos de código, encontrará el símbolo de comentario (`'`).</span><span class="sxs-lookup"><span data-stu-id="5c190-104">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="5c190-105">Este símbolo indica al compilador de Visual Basic que omita el texto que le sigue o el *Comentario*.</span><span class="sxs-lookup"><span data-stu-id="5c190-105">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="5c190-106">Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.</span><span class="sxs-lookup"><span data-stu-id="5c190-106">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="5c190-107">Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento (lo que hace).</span><span class="sxs-lookup"><span data-stu-id="5c190-107">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="5c190-108">Esto ayuda al desarrollador y a los que puedan examinar el código.</span><span class="sxs-lookup"><span data-stu-id="5c190-108">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="5c190-109">Debería separar los detalles de implementación (cómo lo hace el procedimiento) de los comentarios que describen las características funcionales.</span><span class="sxs-lookup"><span data-stu-id="5c190-109">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="5c190-110">Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.</span><span class="sxs-lookup"><span data-stu-id="5c190-110">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="5c190-111">Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa.</span><span class="sxs-lookup"><span data-stu-id="5c190-111">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="5c190-112">Ambas opciones quedan reflejadas en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c190-112">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 <span data-ttu-id="5c190-113">Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c190-113">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="5c190-114">Instrucciones sobre los comentarios</span><span class="sxs-lookup"><span data-stu-id="5c190-114">Commenting Guidelines</span></span>  

 <span data-ttu-id="5c190-115">La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código.</span><span class="sxs-lookup"><span data-stu-id="5c190-115">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="5c190-116">Estas son sugerencias; Visual Basic no aplica reglas para agregar comentarios.</span><span class="sxs-lookup"><span data-stu-id="5c190-116">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="5c190-117">Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.</span><span class="sxs-lookup"><span data-stu-id="5c190-117">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="5c190-118">Tipo de comentario</span><span class="sxs-lookup"><span data-stu-id="5c190-118">Comment type</span></span>|<span data-ttu-id="5c190-119">Descripción del comentario</span><span class="sxs-lookup"><span data-stu-id="5c190-119">Comment description</span></span>|  
|<span data-ttu-id="5c190-120">Propósito</span><span class="sxs-lookup"><span data-stu-id="5c190-120">Purpose</span></span>|<span data-ttu-id="5c190-121">Describe qué hace el procedimiento (no cómo lo hace).</span><span class="sxs-lookup"><span data-stu-id="5c190-121">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="5c190-122">Supuestos</span><span class="sxs-lookup"><span data-stu-id="5c190-122">Assumptions</span></span>|<span data-ttu-id="5c190-123">Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="5c190-123">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="5c190-124">Efectos</span><span class="sxs-lookup"><span data-stu-id="5c190-124">Effects</span></span>|<span data-ttu-id="5c190-125">Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen (únicamente si no es evidente).</span><span class="sxs-lookup"><span data-stu-id="5c190-125">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="5c190-126">Entradas</span><span class="sxs-lookup"><span data-stu-id="5c190-126">Inputs</span></span>|<span data-ttu-id="5c190-127">Especifica el propósito del argumento.</span><span class="sxs-lookup"><span data-stu-id="5c190-127">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="5c190-128">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="5c190-128">Returns</span></span>|<span data-ttu-id="5c190-129">Explica los valores que devuelve el procedimiento</span><span class="sxs-lookup"><span data-stu-id="5c190-129">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="5c190-130">Recuerde los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="5c190-130">Remember the following points:</span></span>  
  
- <span data-ttu-id="5c190-131">Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.</span><span class="sxs-lookup"><span data-stu-id="5c190-131">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
- <span data-ttu-id="5c190-132">Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.</span><span class="sxs-lookup"><span data-stu-id="5c190-132">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
- <span data-ttu-id="5c190-133">Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="5c190-133">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="5c190-134">Para agregar o quitar símbolos de comentario de un bloque de código, seleccione una o varias líneas de código y elija el **Comentario** ( ![ el Visual Basic botón de comentario en Visual Studio ](./media/comments-in-code/visual-basic-comment-button.gif) ) y **Quite los comentarios** ( ![ el botón Visual Basic quitar comentarios de Visual Studio ](./media/comments-in-code/visual-basic-uncomment-button.gif) ) en la barra de herramientas de **edición** .</span><span class="sxs-lookup"><span data-stu-id="5c190-134">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c190-135">También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto.</span><span class="sxs-lookup"><span data-stu-id="5c190-135">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="5c190-136">Sin embargo, los `'` botones de símbolo y de **Comentario** /  son más fáciles de usar y requieren menos espacio y memoria.</span><span class="sxs-lookup"><span data-stu-id="5c190-136">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c190-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c190-137">See also</span></span>

- [<span data-ttu-id="5c190-138">Instinto básico: documentar el código con comentarios XML</span><span class="sxs-lookup"><span data-stu-id="5c190-138">Basic Instincts - Documenting Your Code With XML Comments</span></span>](/archive/msdn-magazine/2009/may/documenting-your-code-with-xml-comments)
- [<span data-ttu-id="5c190-139">Procedimiento para crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="5c190-139">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)
- [<span data-ttu-id="5c190-140">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="5c190-140">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)
- [<span data-ttu-id="5c190-141">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="5c190-141">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="5c190-142">Instrucción REM</span><span class="sxs-lookup"><span data-stu-id="5c190-142">REM Statement</span></span>](../../language-reference/statements/rem-statement.md)
