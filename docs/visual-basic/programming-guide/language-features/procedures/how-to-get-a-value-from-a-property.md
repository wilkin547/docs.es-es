---
title: Procedimiento para obtener un valor de una propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 983e2fd22badf4296004404d885df0a07ab2dc74
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071565"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="fb620-102">Cómo: Obtener un valor de una propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb620-102">How to: Get a Value from a Property (Visual Basic)</span></span>

<span data-ttu-id="fb620-103">Para recuperar el valor de una propiedad, incluya el nombre de la propiedad en una expresión.</span><span class="sxs-lookup"><span data-stu-id="fb620-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="fb620-104">El procedimiento de la propiedad `Get` recupera el valor, pero no lo llama explícitamente por su nombre.</span><span class="sxs-lookup"><span data-stu-id="fb620-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="fb620-105">La propiedad se usa de la misma manera que se usaría una variable.</span><span class="sxs-lookup"><span data-stu-id="fb620-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="fb620-106">Visual Basic realiza las llamadas a los procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fb620-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="fb620-107">Para recuperar un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="fb620-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="fb620-108">Use el nombre de la propiedad en una expresión de la misma manera que usaría un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="fb620-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="fb620-109">Puede usar una propiedad en cualquier lugar en el que pueda usar una variable o una constante.</span><span class="sxs-lookup"><span data-stu-id="fb620-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="fb620-110">o bien</span><span class="sxs-lookup"><span data-stu-id="fb620-110">-or-</span></span>  
  
     <span data-ttu-id="fb620-111">Use el nombre de la propiedad que sigue al signo igual ( `=` ) en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="fb620-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="fb620-112">En el ejemplo siguiente se lee el valor de la `Now` propiedad Visual Basic, que llama implícitamente a su `Get` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fb620-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="fb620-113">Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="fb620-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fb620-114">Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="fb620-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="fb620-115">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="fb620-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fb620-116">Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fb620-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="fb620-117">El valor de la propiedad participa en la expresión como una variable o una constante, o se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="fb620-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb620-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb620-118">See also</span></span>

- [<span data-ttu-id="fb620-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fb620-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fb620-120">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="fb620-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fb620-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="fb620-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fb620-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="fb620-122">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="fb620-123">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb620-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="fb620-124">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="fb620-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="fb620-125">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="fb620-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="fb620-126">Procedimiento para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="fb620-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="fb620-127">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb620-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="fb620-128">Procedimiento para establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="fb620-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
