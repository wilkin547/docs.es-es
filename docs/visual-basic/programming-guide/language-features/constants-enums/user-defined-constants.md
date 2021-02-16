---
description: 'Más información sobre: constantes de User-Defined (Visual Basic)'
title: Constantes definidas por el usuario
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 290d4122249315ae3c6dc5e18ca4faefecb72044
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100485229"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="1a2db-103">Constantes definidas por el usuario (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a2db-103">User-Defined Constants (Visual Basic)</span></span>

<span data-ttu-id="1a2db-104">Una constante es un nombre significativo que ocupa el lugar de un número o una cadena que no cambia.</span><span class="sxs-lookup"><span data-stu-id="1a2db-104">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="1a2db-105">Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1a2db-105">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="1a2db-106">Puede usar constantes definidas por los controles o componentes con los que trabaja, o puede crear las suyas propias.</span><span class="sxs-lookup"><span data-stu-id="1a2db-106">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="1a2db-107">Las constantes que se crean se describen como *definidas por el usuario*.</span><span class="sxs-lookup"><span data-stu-id="1a2db-107">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="1a2db-108">Declare una constante con la `Const` instrucción, con las mismas instrucciones que para crear un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="1a2db-108">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="1a2db-109">Si `Option Strict` es `On` , debe declarar explícitamente el tipo de constante.</span><span class="sxs-lookup"><span data-stu-id="1a2db-109">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="1a2db-110">Uso de la instrucción const</span><span class="sxs-lookup"><span data-stu-id="1a2db-110">Const Statement Usage</span></span>  

 <span data-ttu-id="1a2db-111">Una `Const` instrucción puede representar una cantidad matemática o de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="1a2db-111">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 <span data-ttu-id="1a2db-112">También puede definir `String` constantes:</span><span class="sxs-lookup"><span data-stu-id="1a2db-112">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 <span data-ttu-id="1a2db-113">La expresión del lado derecho del signo igual ( `=` ) suele ser un número o una cadena literal, pero también puede ser una expresión que da como resultado un número o una cadena (aunque esa expresión no puede contener llamadas a funciones).</span><span class="sxs-lookup"><span data-stu-id="1a2db-113">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="1a2db-114">Incluso puede definir constantes en términos de constantes definidas previamente:</span><span class="sxs-lookup"><span data-stu-id="1a2db-114">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="1a2db-115">Ámbito de User-Defined constantes</span><span class="sxs-lookup"><span data-stu-id="1a2db-115">Scope of User-Defined Constants</span></span>  

 <span data-ttu-id="1a2db-116">`Const`El ámbito de una instrucción es el mismo que el de una variable declarada en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="1a2db-116">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="1a2db-117">Puede especificar el ámbito de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a2db-117">You can specify scope in any of the following ways:</span></span>  
  
- <span data-ttu-id="1a2db-118">Para crear una constante que solo existe dentro de un procedimiento, declárela en ese procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1a2db-118">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
- <span data-ttu-id="1a2db-119">Para crear una constante disponible para todos los procedimientos dentro de una clase, pero no para cualquier código fuera de ese módulo, declárelo en la sección declaraciones de la clase.</span><span class="sxs-lookup"><span data-stu-id="1a2db-119">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="1a2db-120">Para crear una constante que esté disponible para todos los miembros de un ensamblado, pero no para los clientes externos del ensamblado, declare el uso de la `Friend` palabra clave en la sección de declaraciones de la clase.</span><span class="sxs-lookup"><span data-stu-id="1a2db-120">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="1a2db-121">Para crear una constante disponible en toda la aplicación, declárela mediante la `Public` palabra clave en la sección declaraciones de la clase.</span><span class="sxs-lookup"><span data-stu-id="1a2db-121">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="1a2db-122">Para obtener más información, vea [Cómo: declarar una constante](how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="1a2db-122">For more information, see [How to: Declare A Constant](how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="1a2db-123">Evitar referencias circulares</span><span class="sxs-lookup"><span data-stu-id="1a2db-123">Avoiding Circular References</span></span>  

 <span data-ttu-id="1a2db-124">Dado que las constantes se pueden definir en términos de otras constantes, es posible crear accidentalmente un *ciclo* o una referencia circular entre dos o más constantes.</span><span class="sxs-lookup"><span data-stu-id="1a2db-124">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="1a2db-125">Un ciclo se produce cuando hay dos o más constantes públicas, cada una de las cuales se define en términos del otro, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a2db-125">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 <span data-ttu-id="1a2db-126">Si se produce un ciclo, Visual Basic genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="1a2db-126">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2db-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a2db-127">See also</span></span>

- [<span data-ttu-id="1a2db-128">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="1a2db-128">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
- [<span data-ttu-id="1a2db-129">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="1a2db-129">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="1a2db-130">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1a2db-130">Constants and Enumerations</span></span>](index.md)
- [<span data-ttu-id="1a2db-131">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1a2db-131">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="1a2db-132">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1a2db-132">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="1a2db-133">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="1a2db-133">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="1a2db-134">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="1a2db-134">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="1a2db-135">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="1a2db-135">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="1a2db-136">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1a2db-136">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
