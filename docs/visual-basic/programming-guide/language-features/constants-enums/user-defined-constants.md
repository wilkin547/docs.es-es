---
title: Constantes definidas por el usuario (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce839c3e843a52b31e40c13cb765f8eaf9959ea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="4e96d-102">Constantes definidas por el usuario (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e96d-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="4e96d-103">Una constante es un nombre descriptivo que ocupa el lugar de un número o una cadena que no cambia.</span><span class="sxs-lookup"><span data-stu-id="4e96d-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="4e96d-104">Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4e96d-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="4e96d-105">Puede usar constantes definidas por los controles o componentes con los que trabaja, o puede crear los suyos propios.</span><span class="sxs-lookup"><span data-stu-id="4e96d-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="4e96d-106">Se describen las constantes que crea usted mismo como *definido por el usuario*.</span><span class="sxs-lookup"><span data-stu-id="4e96d-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="4e96d-107">Declarar una constante con el `Const` instrucción, utilizando las mismas directrices que lo haría para crear un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="4e96d-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="4e96d-108">Si `Option Strict` es `On`, debe declarar explícitamente el tipo de constante.</span><span class="sxs-lookup"><span data-stu-id="4e96d-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="4e96d-109">Utilización de la instrucción const</span><span class="sxs-lookup"><span data-stu-id="4e96d-109">Const Statement Usage</span></span>  
 <span data-ttu-id="4e96d-110">Un `Const` instrucción puede representar un matemáticas o cantidad de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="4e96d-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 <span data-ttu-id="4e96d-111">También puede definir `String` constantes:</span><span class="sxs-lookup"><span data-stu-id="4e96d-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 <span data-ttu-id="4e96d-112">La expresión del lado derecho del signo igual ( `=` ) suele ser un número o una cadena literal, pero también puede ser una expresión que da como resultado un número o una cadena (aunque esa expresión no puede contener llamadas a funciones).</span><span class="sxs-lookup"><span data-stu-id="4e96d-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="4e96d-113">Incluso puede definir constantes en términos de constantes definidas anteriormente:</span><span class="sxs-lookup"><span data-stu-id="4e96d-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="4e96d-114">Ámbito de las constantes definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="4e96d-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="4e96d-115">Un `Const` ámbito de la instrucción es el mismo que el de una variable declarada en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="4e96d-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="4e96d-116">Puede especificar el ámbito en cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e96d-116">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="4e96d-117">Para crear una constante que sólo existe dentro de un procedimiento, declárela dentro de ese procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4e96d-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="4e96d-118">Para crear una constante disponible para todos los procedimientos dentro de una clase, pero no para el código fuera de ese módulo, declárelo en la sección de declaraciones de la clase.</span><span class="sxs-lookup"><span data-stu-id="4e96d-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="4e96d-119">Para crear una constante que esté disponible para todos los miembros de un ensamblado, pero no para clientes fuera del ensamblado, declárela mediante la `Friend` palabra clave en la sección de declaraciones de la clase.</span><span class="sxs-lookup"><span data-stu-id="4e96d-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="4e96d-120">Para crear una constante disponible en toda la aplicación, declárela con la `Public` palabra clave en las declaraciones de sección de la clase.</span><span class="sxs-lookup"><span data-stu-id="4e96d-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="4e96d-121">Para obtener más información, consulte [Cómo: declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="4e96d-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="4e96d-122">Evitar referencias circulares</span><span class="sxs-lookup"><span data-stu-id="4e96d-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="4e96d-123">Dado que constantes pueden definirse en términos de otras constantes, es posible crear inadvertidamente un *ciclo*, o una referencia circular, entre dos o más constantes.</span><span class="sxs-lookup"><span data-stu-id="4e96d-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="4e96d-124">Un ciclo se produce cuando hay dos o más constantes públicas, cada uno de los cuales se define en términos de la otra, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e96d-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 <span data-ttu-id="4e96d-125">Si se produce un ciclo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="4e96d-125">If a cycle occurs, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e96d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e96d-126">See Also</span></span>  
 [<span data-ttu-id="4e96d-127">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4e96d-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="4e96d-128">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="4e96d-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="4e96d-129">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="4e96d-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [<span data-ttu-id="4e96d-130">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="4e96d-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="4e96d-131">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="4e96d-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="4e96d-132">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="4e96d-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="4e96d-133">Cómo: declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="4e96d-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="4e96d-134">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="4e96d-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="4e96d-135">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4e96d-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
