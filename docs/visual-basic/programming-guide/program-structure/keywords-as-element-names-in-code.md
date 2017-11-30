---
title: "Palabras clave como nombres de elementos en código (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f410a0eaac0dcc034d406a89ed1d01a8f228a583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="a75bc-102">Palabras clave como nombres de elementos en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a75bc-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="a75bc-103">Cualquier elemento de programa, como una variable, una clase o un miembro, puede tener el mismo nombre que una palabra clave restringida.</span><span class="sxs-lookup"><span data-stu-id="a75bc-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="a75bc-104">Por ejemplo, puede crear una variable denominada `Loop`.</span><span class="sxs-lookup"><span data-stu-id="a75bc-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="a75bc-105">Sin embargo, para hacer referencia a la versión del mismo, que tiene el mismo nombre que restringido `Loop` palabra clave: debe ir precedida de una cadena de calificación completa o encerrar entre corchetes (`[ ]`), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a75bc-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="a75bc-106">Si no hace cualquiera de estos, Visual Basic se supone el uso de la función intrínseca `Loop` palabra clave y genera un error, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a75bc-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="a75bc-107">Puede utilizar corchetes al hacer referencia a los formularios y controles y al declarar una variable o al definir un procedimiento con el mismo nombre que una palabra clave restringida.</span><span class="sxs-lookup"><span data-stu-id="a75bc-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="a75bc-108">Puede ser fácil olvidarse de calificar los nombres o incluir los corchetes y, por tanto, introducir errores en el código y dificultar la lectura.</span><span class="sxs-lookup"><span data-stu-id="a75bc-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="a75bc-109">Por este motivo, se recomienda que no utilice palabras clave restringidas como nombres de elementos de programa.</span><span class="sxs-lookup"><span data-stu-id="a75bc-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="a75bc-110">Sin embargo, si una futura versión de Visual Basic define una nueva palabra clave que entra en conflicto con un nombre de control o un formulario existente, a continuación, se puede usar esta técnica al actualizar el código para trabajar con la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="a75bc-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a75bc-111">El programa también puede incluir nombres de elementos proporcionados por otros ensamblados que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="a75bc-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="a75bc-112">Si estos nombres entran en conflicto con palabras clave restringidas, a continuación, colocar corchetes alrededor de ellas hace que Visual Basic para interpretarlos como los elementos definidos.</span><span class="sxs-lookup"><span data-stu-id="a75bc-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75bc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a75bc-113">See Also</span></span>  
 [<span data-ttu-id="a75bc-114">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a75bc-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="a75bc-115">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="a75bc-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="a75bc-116">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a75bc-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
