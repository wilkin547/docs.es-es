---
description: 'Más información sobre: Cómo: colocar un valor en una propiedad (Visual Basic)'
title: Procedimiento para establecer un valor en una propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 62f5552f821fb98bd3a4695505aba5ff73b08fc7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476207"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="b7504-103">Cómo: Establecer un valor en una propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7504-103">How to: Put a Value in a Property (Visual Basic)</span></span>

<span data-ttu-id="b7504-104">Para almacenar un valor en una propiedad, coloque el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="b7504-104">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="b7504-105">El procedimiento de la propiedad `Set` almacena un valor, pero no lo llama explícitamente por su nombre.</span><span class="sxs-lookup"><span data-stu-id="b7504-105">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="b7504-106">La propiedad se usa de la misma manera que se usaría una variable.</span><span class="sxs-lookup"><span data-stu-id="b7504-106">You use the property just as you would use a variable.</span></span> <span data-ttu-id="b7504-107">Visual Basic realiza las llamadas a los procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7504-107">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="b7504-108">Para almacenar un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="b7504-108">To store a value in a property</span></span>  
  
1. <span data-ttu-id="b7504-109">Use el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="b7504-109">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="b7504-110">En el ejemplo siguiente se establece el valor de la `TimeOfDay` propiedad Visual Basic en mediodía, llamando implícitamente a su `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b7504-110">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="b7504-111">Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="b7504-111">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="b7504-112">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="b7504-112">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="b7504-113">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="b7504-113">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="b7504-114">Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b7504-114">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="b7504-115">El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7504-115">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7504-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7504-116">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="b7504-117">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="b7504-117">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b7504-118">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="b7504-118">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b7504-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b7504-119">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="b7504-120">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7504-120">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="b7504-121">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="b7504-121">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="b7504-122">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="b7504-122">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="b7504-123">Procedimiento para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="b7504-123">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="b7504-124">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7504-124">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="b7504-125">Procedimiento para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="b7504-125">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
