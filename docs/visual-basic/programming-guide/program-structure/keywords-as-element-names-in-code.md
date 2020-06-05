---
title: Palabras clave como nombres de elementos en el código
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: a98f0b027700717b414d58e1284ddec655eb25f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403231"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="ee1b4-102">Palabras clave como nombres de elementos en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee1b4-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="ee1b4-103">Cualquier elemento de programa, como una variable, una clase o un miembro, puede tener el mismo nombre que una palabra clave restringida.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="ee1b4-104">Por ejemplo, puede crear una variable denominada `Loop` .</span><span class="sxs-lookup"><span data-stu-id="ee1b4-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="ee1b4-105">Sin embargo, para hacer referencia a su versión del mismo, que tiene el mismo nombre que la palabra clave Restricted, `Loop` debe precederlo con una cadena de calificación completa o encerrarlo entre corchetes ( `[ ]` ), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="ee1b4-106">Si no hace ninguno de estos, Visual Basic supone el uso de la `Loop` palabra clave Intrinsic y genera un error, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee1b4-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="ee1b4-107">Puede usar corchetes al hacer referencia a formularios y controles, y al declarar una variable o definir un procedimiento con el mismo nombre que una palabra clave restringida.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="ee1b4-108">Puede ser fácil olvidarse de calificar nombres o incluir corchetes y, por tanto, introducir errores en el código y dificultar su lectura.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="ee1b4-109">Por esta razón, se recomienda no usar palabras clave restringidas como nombres de elementos de programa.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="ee1b4-110">Sin embargo, si una versión futura de Visual Basic define una nueva palabra clave que entra en conflicto con un nombre de formulario o control existente, puede usar esta técnica al actualizar el código para que funcione con la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee1b4-111">El programa también podría incluir nombres de elementos proporcionados por otros ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="ee1b4-112">Si estos nombres entran en conflicto con palabras clave restringidas, la colocación de los corchetes hace que Visual Basic los interprete como elementos definidos.</span><span class="sxs-lookup"><span data-stu-id="ee1b4-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1b4-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee1b4-113">See also</span></span>

- [<span data-ttu-id="ee1b4-114">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee1b4-114">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="ee1b4-115">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="ee1b4-115">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="ee1b4-116">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ee1b4-116">Keywords</span></span>](../../language-reference/keywords/index.md)
