---
title: 'Cómo: Establecer un valor en una propiedad (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 29e68ca2b9436921c81346eb1def2417157aae9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650376"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="4dc16-102">Cómo: Establecer un valor en una propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dc16-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="4dc16-103">Almacenar un valor en una propiedad colocando el nombre de propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="4dc16-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="4dc16-104">La propiedad `Set` procedimiento almacena un valor, pero no llamar explícitamente a él por su nombre.</span><span class="sxs-lookup"><span data-stu-id="4dc16-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="4dc16-105">Use la propiedad tal como utilizaría una variable.</span><span class="sxs-lookup"><span data-stu-id="4dc16-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="4dc16-106">Visual Basic realiza las llamadas a procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4dc16-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="4dc16-107">Para almacenar un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="4dc16-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="4dc16-108">Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="4dc16-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="4dc16-109">En el ejemplo siguiente se establece el valor de Visual Basic `TimeOfDay` propiedad al mediodía, se llama implícitamente a su `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4dc16-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  <span data-ttu-id="4dc16-110">Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4dc16-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="4dc16-111">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="4dc16-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="4dc16-112">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="4dc16-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="4dc16-113">Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4dc16-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="4dc16-114">El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4dc16-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc16-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dc16-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [<span data-ttu-id="4dc16-116">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="4dc16-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="4dc16-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="4dc16-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="4dc16-118">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4dc16-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="4dc16-119">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4dc16-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="4dc16-120">Crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="4dc16-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="4dc16-121">Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="4dc16-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="4dc16-122">Llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="4dc16-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="4dc16-123">Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4dc16-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="4dc16-124">Obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="4dc16-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
