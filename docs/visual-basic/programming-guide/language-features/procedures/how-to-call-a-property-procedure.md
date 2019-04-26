---
title: Procedimiento Llamar a un procedimiento de propiedad (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: d05c1b63f5567ade9935f80ecc022eb4840e0af0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864369"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="8179e-102">Procedimiento Llamar a un procedimiento de propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8179e-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="8179e-103">Se llama a un procedimiento de propiedad almacenar un valor en la propiedad o recuperar su valor.</span><span class="sxs-lookup"><span data-stu-id="8179e-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="8179e-104">Obtener acceso a una propiedad del mismo modo que obtener acceso a una variable.</span><span class="sxs-lookup"><span data-stu-id="8179e-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="8179e-105">La propiedad `Set` procedimiento almacena un valor y su `Get` procedimiento recupera el valor.</span><span class="sxs-lookup"><span data-stu-id="8179e-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="8179e-106">Sin embargo, no llame explícitamente estos procedimientos por su nombre.</span><span class="sxs-lookup"><span data-stu-id="8179e-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="8179e-107">Utilice la propiedad en una instrucción de asignación o una expresión, tal como podría almacenar o recuperar el valor de una variable.</span><span class="sxs-lookup"><span data-stu-id="8179e-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="8179e-108">Visual Basic realiza las llamadas a procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8179e-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="8179e-109">Para llamar al procedimiento de una propiedad Get</span><span class="sxs-lookup"><span data-stu-id="8179e-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="8179e-110">Utilice el nombre de propiedad en una expresión de la misma manera que utilizaría un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="8179e-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="8179e-111">Puede usar una propiedad en cualquier lugar puede usar una variable o una constante.</span><span class="sxs-lookup"><span data-stu-id="8179e-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="8179e-112">-o bien-</span><span class="sxs-lookup"><span data-stu-id="8179e-112">-or-</span></span>  
  
     <span data-ttu-id="8179e-113">Utilice el nombre de propiedad tras la igual (`=`) inicie sesión en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="8179e-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="8179e-114">El ejemplo siguiente lee el valor de la <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> propiedad, se llama implícitamente a su `Get` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8179e-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="8179e-115">Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="8179e-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8179e-116">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8179e-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="8179e-117">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="8179e-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8179e-118">Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8179e-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="8179e-119">El valor de la propiedad participa en la expresión igual que una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="8179e-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="8179e-120">Para llamar a una propiedad de conjunto del procedimiento</span><span class="sxs-lookup"><span data-stu-id="8179e-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="8179e-121">Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="8179e-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="8179e-122">En el ejemplo siguiente se establece el valor de la <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> propiedad, se llama implícitamente a la `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8179e-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="8179e-123">Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="8179e-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8179e-124">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8179e-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="8179e-125">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="8179e-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8179e-126">Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8179e-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="8179e-127">El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8179e-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8179e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8179e-128">See also</span></span>

- [<span data-ttu-id="8179e-129">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="8179e-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="8179e-130">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="8179e-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="8179e-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8179e-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="8179e-132">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8179e-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="8179e-133">Cómo: Crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="8179e-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="8179e-134">Cómo: Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="8179e-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="8179e-135">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8179e-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="8179e-136">Cómo: Establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="8179e-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="8179e-137">Cómo: Obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="8179e-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="8179e-138">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8179e-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="8179e-139">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8179e-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
