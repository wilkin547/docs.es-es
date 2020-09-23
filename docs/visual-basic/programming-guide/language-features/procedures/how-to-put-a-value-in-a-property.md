---
title: Procedimiento para establecer un valor en una propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 7d85066d4678ee2a53b8339bee2db20374482579
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071409"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="f84e6-102">Cómo: Establecer un valor en una propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f84e6-102">How to: Put a Value in a Property (Visual Basic)</span></span>

<span data-ttu-id="f84e6-103">Para almacenar un valor en una propiedad, coloque el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="f84e6-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="f84e6-104">El procedimiento de la propiedad `Set` almacena un valor, pero no lo llama explícitamente por su nombre.</span><span class="sxs-lookup"><span data-stu-id="f84e6-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="f84e6-105">La propiedad se usa de la misma manera que se usaría una variable.</span><span class="sxs-lookup"><span data-stu-id="f84e6-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="f84e6-106">Visual Basic realiza las llamadas a los procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f84e6-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="f84e6-107">Para almacenar un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="f84e6-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="f84e6-108">Use el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="f84e6-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="f84e6-109">En el ejemplo siguiente se establece el valor de la `TimeOfDay` propiedad Visual Basic en mediodía, llamando implícitamente a su `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f84e6-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="f84e6-110">Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f84e6-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f84e6-111">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="f84e6-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="f84e6-112">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="f84e6-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f84e6-113">Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f84e6-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="f84e6-114">El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f84e6-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84e6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f84e6-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="f84e6-116">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="f84e6-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="f84e6-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="f84e6-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f84e6-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f84e6-118">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="f84e6-119">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f84e6-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="f84e6-120">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="f84e6-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="f84e6-121">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="f84e6-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="f84e6-122">Procedimiento para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="f84e6-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="f84e6-123">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f84e6-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="f84e6-124">Procedimiento para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="f84e6-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
