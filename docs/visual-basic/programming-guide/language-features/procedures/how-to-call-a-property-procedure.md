---
description: 'Más información acerca de cómo: llamar a un procedimiento de propiedad (Visual Basic)'
title: Procedimiento para llamar a un procedimiento de propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 541768cb6381aa3d2b1bf75267c5b34a82a3d2ab
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466762"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="d11b8-103">Cómo: Llamar a un procedimiento de propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d11b8-103">How to: Call a Property Procedure (Visual Basic)</span></span>

<span data-ttu-id="d11b8-104">Para llamar a un procedimiento de propiedad, se almacena un valor en la propiedad o se recupera su valor.</span><span class="sxs-lookup"><span data-stu-id="d11b8-104">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="d11b8-105">Puede tener acceso a una propiedad de la misma manera que tiene acceso a una variable.</span><span class="sxs-lookup"><span data-stu-id="d11b8-105">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="d11b8-106">El procedimiento de la propiedad `Set` almacena un valor y su `Get` procedimiento recupera el valor.</span><span class="sxs-lookup"><span data-stu-id="d11b8-106">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="d11b8-107">Sin embargo, no se llama a estos procedimientos explícitamente por nombre.</span><span class="sxs-lookup"><span data-stu-id="d11b8-107">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="d11b8-108">La propiedad se usa en una instrucción de asignación o una expresión, tal como se almacenaría o recuperaría el valor de una variable.</span><span class="sxs-lookup"><span data-stu-id="d11b8-108">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="d11b8-109">Visual Basic realiza las llamadas a los procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d11b8-109">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="d11b8-110">Para llamar al procedimiento get de una propiedad</span><span class="sxs-lookup"><span data-stu-id="d11b8-110">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="d11b8-111">Use el nombre de la propiedad en una expresión de la misma manera que usaría un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="d11b8-111">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="d11b8-112">Puede usar una propiedad en cualquier lugar en el que pueda usar una variable o una constante.</span><span class="sxs-lookup"><span data-stu-id="d11b8-112">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="d11b8-113">o bien</span><span class="sxs-lookup"><span data-stu-id="d11b8-113">-or-</span></span>  
  
     <span data-ttu-id="d11b8-114">Use el nombre de la propiedad que sigue al signo igual ( `=` ) en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="d11b8-114">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="d11b8-115">En el ejemplo siguiente se lee el valor de la <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> propiedad, que llama implícitamente a su `Get` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d11b8-115">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="d11b8-116">Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="d11b8-116">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="d11b8-117">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="d11b8-117">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="d11b8-118">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="d11b8-118">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="d11b8-119">Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d11b8-119">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="d11b8-120">El valor de la propiedad participa en la expresión como una variable o una constante, o se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="d11b8-120">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="d11b8-121">Para llamar al procedimiento set de una propiedad</span><span class="sxs-lookup"><span data-stu-id="d11b8-121">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="d11b8-122">Use el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="d11b8-122">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="d11b8-123">En el ejemplo siguiente se establece el valor de la <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> propiedad, que llama implícitamente al `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d11b8-123">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="d11b8-124">Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="d11b8-124">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="d11b8-125">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="d11b8-125">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="d11b8-126">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="d11b8-126">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="d11b8-127">Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d11b8-127">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="d11b8-128">El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d11b8-128">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11b8-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d11b8-129">See also</span></span>

- [<span data-ttu-id="d11b8-130">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="d11b8-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d11b8-131">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="d11b8-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d11b8-132">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d11b8-132">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="d11b8-133">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d11b8-133">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="d11b8-134">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="d11b8-134">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="d11b8-135">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="d11b8-135">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="d11b8-136">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d11b8-136">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="d11b8-137">Procedimiento para establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="d11b8-137">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="d11b8-138">Procedimiento para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="d11b8-138">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="d11b8-139">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d11b8-139">Get Statement</span></span>](../../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="d11b8-140">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d11b8-140">Set Statement</span></span>](../../../language-reference/statements/set-statement.md)
