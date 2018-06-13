---
title: Enumeraciones y calificación de nombres (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: eb1f5653d968e81168833cd57813219e8f049b70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648585"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="f7a68-102">Enumeraciones y calificación de nombres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7a68-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="f7a68-103">Normalmente, cuando se hace referencia a un miembro de una enumeración, debe calificar el nombre de miembro con el nombre de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f7a68-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="f7a68-104">Por ejemplo, para hacer referencia a la `Sunday` miembro de su `Days` enumeración, se utilizaría la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f7a68-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="f7a68-105">Mediante la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="f7a68-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="f7a68-106">Puede evitar el uso de nombres completos agregando un `Imports` instrucción a la sección de declaraciones de espacio de nombres del código, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7a68-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="f7a68-107">Un `Imports` instrucción importa los espacios de nombres de ensamblados y proyectos que se hace referencia y desde el mismo proyecto que el módulo en el que aparece la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f7a68-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="f7a68-108">Una vez agregada esta instrucción, puede hacer referencia a los miembros de enumeración sin calificación, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7a68-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="f7a68-109">Si organiza los conjuntos de constantes relacionadas en enumeraciones, puede usar los mismos nombres de constantes en diferentes contextos.</span><span class="sxs-lookup"><span data-stu-id="f7a68-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="f7a68-110">Por ejemplo, puede usar los mismos nombres para las constantes de día de la semana en el `Days` y `WorkDays` enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="f7a68-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="f7a68-111">Si usas el `Imports` instrucción con las enumeraciones, debe tener cuidado para evitar referencias ambiguas.</span><span class="sxs-lookup"><span data-stu-id="f7a68-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="f7a68-112">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7a68-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="f7a68-113">Suponiendo que `Monday` es un miembro de la `Days` enumeración y `Workdays` enumeración, este código genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="f7a68-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="f7a68-114">Para evitar referencias ambiguas Cuando se hace referencia a una constante individual, nombre de la constante con su enumeración.</span><span class="sxs-lookup"><span data-stu-id="f7a68-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="f7a68-115">El código siguiente hace referencia a la `Saturday` constantes en el `Days` y `WorkDays` enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="f7a68-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f7a68-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7a68-116">See Also</span></span>  
 [<span data-ttu-id="f7a68-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="f7a68-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="f7a68-118">Cómo: declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="f7a68-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="f7a68-119">Hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="f7a68-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="f7a68-120">Cómo: recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7a68-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="f7a68-121">Determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="f7a68-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="f7a68-122">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="f7a68-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="f7a68-123">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="f7a68-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="f7a68-124">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f7a68-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="f7a68-125">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="f7a68-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="f7a68-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f7a68-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
