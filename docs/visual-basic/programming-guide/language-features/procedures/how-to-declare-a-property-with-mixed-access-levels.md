---
description: 'Más información sobre: Cómo: declarar una propiedad con niveles de acceso mixtos (Visual Basic)'
title: Procedimiento para declarar una propiedad con niveles de acceso mixtos
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: e01849b0a590e499c1ee7b4a67d6aa794cd7cc5d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472467"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="ca5ae-103">Cómo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca5ae-103">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>

<span data-ttu-id="ca5ae-104">Si desea que los `Get` `Set` procedimientos y de una propiedad tengan niveles de acceso diferentes, puede usar el nivel más permisivo en la `Property` instrucción y el nivel más restrictivo en la `Get` `Set` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-104">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="ca5ae-105">Puede usar niveles de acceso mixtos en una propiedad si desea que determinadas partes del código puedan obtener el valor de la propiedad y otras partes del código para poder cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-105">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="ca5ae-106">Para obtener más información sobre los niveles de acceso, vea [niveles de acceso en Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ca5ae-106">For more information on access levels, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="ca5ae-107">Para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="ca5ae-107">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="ca5ae-108">Declare la propiedad de la manera normal y especifique el nivel de acceso menos restrictivo (como `Public` ) en la `Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-108">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="ca5ae-109">Declare `Get` o el `Set` procedimiento que especifica el nivel de acceso más restrictivo (como `Friend` ).</span><span class="sxs-lookup"><span data-stu-id="ca5ae-109">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="ca5ae-110">No especifique un nivel de acceso en el otro procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-110">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="ca5ae-111">Se asume el nivel de acceso declarado en la `Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-111">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="ca5ae-112">Puede restringir el acceso solo en uno de los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-112">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="ca5ae-113">En el ejemplo anterior, el `Get` procedimiento tiene el mismo `Protected` acceso que la propiedad, mientras que el `Set` procedimiento tiene `Private` acceso.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-113">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="ca5ae-114">Una clase derivada de `employee` puede leer el `salary` valor, pero solo la `employee` clase puede establecerlo.</span><span class="sxs-lookup"><span data-stu-id="ca5ae-114">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5ae-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca5ae-115">See also</span></span>

- [<span data-ttu-id="ca5ae-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ca5ae-116">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ca5ae-117">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="ca5ae-117">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ca5ae-118">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="ca5ae-118">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ca5ae-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="ca5ae-119">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="ca5ae-120">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca5ae-120">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="ca5ae-121">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="ca5ae-121">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="ca5ae-122">Procedimiento para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="ca5ae-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="ca5ae-123">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca5ae-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="ca5ae-124">Procedimiento para establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="ca5ae-124">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="ca5ae-125">Procedimiento para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="ca5ae-125">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
