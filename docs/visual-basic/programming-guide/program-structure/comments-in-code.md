---
title: Comentarios en el código (Visual Basic)
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
ms.openlocfilehash: 2737d9494fb4cd2f0cfaec4da1bca69003c6bad7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753745"
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="3aa8c-102">Comentarios en el código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aa8c-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="3aa8c-103">Cuando lea ejemplos de código, encontrará el símbolo de comentario (`'`).</span><span class="sxs-lookup"><span data-stu-id="3aa8c-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="3aa8c-104">Este símbolo indica al compilador de Visual Basic para pasar por alto el texto que aparece a continuación o *comentario*.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-104">This symbol tells the Visual Basic compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="3aa8c-105">Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="3aa8c-106">Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento (lo que hace).</span><span class="sxs-lookup"><span data-stu-id="3aa8c-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="3aa8c-107">Esto ayuda al desarrollador y a los que puedan examinar el código.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="3aa8c-108">Debería separar los detalles de implementación (cómo lo hace el procedimiento) de los comentarios que describen las características funcionales.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="3aa8c-109">Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="3aa8c-110">Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="3aa8c-111">Ambas opciones quedan reflejadas en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#16)]  
  
 <span data-ttu-id="3aa8c-112">Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3aa8c-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#17)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="3aa8c-113">Instrucciones sobre los comentarios</span><span class="sxs-lookup"><span data-stu-id="3aa8c-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="3aa8c-114">La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="3aa8c-115">Estos son sugerencias; Visual Basic no aplica las reglas para agregar comentarios.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-115">These are suggestions; Visual Basic does not enforce rules for adding comments.</span></span> <span data-ttu-id="3aa8c-116">Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="3aa8c-117">Tipo de comentario</span><span class="sxs-lookup"><span data-stu-id="3aa8c-117">Comment type</span></span>|<span data-ttu-id="3aa8c-118">Descripción del comentario</span><span class="sxs-lookup"><span data-stu-id="3aa8c-118">Comment description</span></span>|  
|<span data-ttu-id="3aa8c-119">Finalidad</span><span class="sxs-lookup"><span data-stu-id="3aa8c-119">Purpose</span></span>|<span data-ttu-id="3aa8c-120">Describe qué hace el procedimiento (no cómo lo hace).</span><span class="sxs-lookup"><span data-stu-id="3aa8c-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="3aa8c-121">Suposiciones</span><span class="sxs-lookup"><span data-stu-id="3aa8c-121">Assumptions</span></span>|<span data-ttu-id="3aa8c-122">Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="3aa8c-123">Efectos</span><span class="sxs-lookup"><span data-stu-id="3aa8c-123">Effects</span></span>|<span data-ttu-id="3aa8c-124">Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen (únicamente si no es evidente).</span><span class="sxs-lookup"><span data-stu-id="3aa8c-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="3aa8c-125">Entradas</span><span class="sxs-lookup"><span data-stu-id="3aa8c-125">Inputs</span></span>|<span data-ttu-id="3aa8c-126">Especifica el propósito del argumento.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="3aa8c-127">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="3aa8c-127">Returns</span></span>|<span data-ttu-id="3aa8c-128">Explica los valores que devuelve el procedimiento</span><span class="sxs-lookup"><span data-stu-id="3aa8c-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="3aa8c-129">Recuerde los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="3aa8c-129">Remember the following points:</span></span>  
  
- <span data-ttu-id="3aa8c-130">Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
- <span data-ttu-id="3aa8c-131">Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
- <span data-ttu-id="3aa8c-132">Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="3aa8c-133">Puede agregar o quitar símbolos de comentario de un bloque de código seleccionando una o varias líneas de código y eligiendo la **comentario** (![botón el comentario de Visual Basic en Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) y **sin comentarios**  (![Botón la quite de Visual Basic en Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) los botones de la **editar** barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![The Visual Basic Comment button in Visual Studio.](./media/comments-in-code/visual-basic-comment-button.gif)) and **Uncomment** (![The Visual Basic Uncomment button in Visual Studio.](./media/comments-in-code/visual-basic-uncomment-button.gif)) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3aa8c-134">También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="3aa8c-135">Sin embargo, el `'` símbolo y el **comentario**/**sin comentarios** botones son más fáciles de utilizar y requieren menos espacio y memoria.</span><span class="sxs-lookup"><span data-stu-id="3aa8c-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa8c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3aa8c-136">See also</span></span>

- [<span data-ttu-id="3aa8c-137">Instintos básicos – documentar el código con comentarios XML</span><span class="sxs-lookup"><span data-stu-id="3aa8c-137">Basic Instincts - Documenting Your Code With XML Comments</span></span>](https://msdn.microsoft.com/magazine/dd722812.aspx)
- [<span data-ttu-id="3aa8c-138">Cómo: Crear documentación XML</span><span class="sxs-lookup"><span data-stu-id="3aa8c-138">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="3aa8c-139">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="3aa8c-139">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="3aa8c-140">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="3aa8c-140">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="3aa8c-141">REM (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3aa8c-141">REM Statement</span></span>](../../../visual-basic/language-reference/statements/rem-statement.md)
