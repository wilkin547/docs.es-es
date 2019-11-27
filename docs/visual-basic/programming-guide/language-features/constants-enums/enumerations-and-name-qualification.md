---
title: Enumeraciones y calificación de nombres
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
ms.openlocfilehash: 4121266447b771ba954ad52a46e0d8b88de3f9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347497"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="db43f-102">Enumeraciones y calificación de nombres (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db43f-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="db43f-103">Normalmente, cuando se hace referencia a un miembro de una enumeración, se debe calificar el nombre del miembro con el nombre de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="db43f-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="db43f-104">Por ejemplo, para hacer referencia al `Sunday` miembro de la enumeración `Days`, usaría la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="db43f-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="db43f-105">Usar la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="db43f-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="db43f-106">Puede evitar el uso de nombres completos agregando una instrucción `Imports` a la sección de declaraciones de espacio de nombres del código, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db43f-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 <span data-ttu-id="db43f-107">Una instrucción `Imports` importa nombres de espacios de nombres de ensamblados y proyectos a los que se hace referencia y desde dentro del mismo proyecto que el módulo en el que aparece la instrucción.</span><span class="sxs-lookup"><span data-stu-id="db43f-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="db43f-108">Una vez agregada esta instrucción, puede hacer referencia a los miembros de enumeración sin calificación, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db43f-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 <span data-ttu-id="db43f-109">Al organizar conjuntos de constantes relacionadas en las enumeraciones, puede utilizar los mismos nombres de constantes en contextos diferentes.</span><span class="sxs-lookup"><span data-stu-id="db43f-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="db43f-110">Por ejemplo, puede usar los mismos nombres para las constantes Weekday en las enumeraciones `Days` y `WorkDays`.</span><span class="sxs-lookup"><span data-stu-id="db43f-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="db43f-111">Si usa la instrucción `Imports` con sus enumeraciones, debe tener cuidado de evitar referencias ambiguas.</span><span class="sxs-lookup"><span data-stu-id="db43f-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="db43f-112">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db43f-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 <span data-ttu-id="db43f-113">Suponiendo que `Monday` sea miembro de la enumeración `Days` y de la enumeración `Workdays`, este código genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="db43f-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="db43f-114">Para evitar referencias ambiguas al hacer referencia a una constante individual, califique el nombre de la constante con su enumeración.</span><span class="sxs-lookup"><span data-stu-id="db43f-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="db43f-115">El código siguiente hace referencia a las constantes de `Saturday` en las enumeraciones `Days` y `WorkDays`.</span><span class="sxs-lookup"><span data-stu-id="db43f-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="db43f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="db43f-116">See also</span></span>

- [<span data-ttu-id="db43f-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="db43f-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="db43f-118">Cómo: declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="db43f-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="db43f-119">Hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="db43f-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="db43f-120">Cómo: recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db43f-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="db43f-121">Determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="db43f-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="db43f-122">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="db43f-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="db43f-123">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="db43f-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="db43f-124">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db43f-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="db43f-125">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="db43f-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="db43f-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="db43f-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
