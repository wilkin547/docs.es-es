---
title: 'Cómo: Declarar una propiedad con niveles de acceso mixtos'
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
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349695"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="cdb96-102">Cómo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdb96-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="cdb96-103">Si desea que los procedimientos `Get` y `Set` de una propiedad tengan niveles de acceso diferentes, puede usar el nivel más permisivo en la instrucción `Property` y el nivel más restrictivo en la instrucción `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="cdb96-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="cdb96-104">Puede usar niveles de acceso mixtos en una propiedad si desea que determinadas partes del código puedan obtener el valor de la propiedad y otras partes del código para poder cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="cdb96-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="cdb96-105">Para obtener más información sobre los niveles de acceso, vea [niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cdb96-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="cdb96-106">Para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="cdb96-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="cdb96-107">Declare la propiedad de la manera normal y especifique el nivel de acceso menos restrictivo (como `Public`) en la instrucción `Property`.</span><span class="sxs-lookup"><span data-stu-id="cdb96-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="cdb96-108">Declare el `Get` o el procedimiento `Set` especificando el nivel de acceso más restrictivo (como `Friend`).</span><span class="sxs-lookup"><span data-stu-id="cdb96-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="cdb96-109">No especifique un nivel de acceso en el otro procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cdb96-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="cdb96-110">Se asume el nivel de acceso declarado en la instrucción `Property`.</span><span class="sxs-lookup"><span data-stu-id="cdb96-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="cdb96-111">Puede restringir el acceso solo en uno de los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cdb96-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="cdb96-112">En el ejemplo anterior, el procedimiento `Get` tiene el mismo acceso `Protected` que la propiedad, mientras que el procedimiento `Set` tiene `Private` acceso.</span><span class="sxs-lookup"><span data-stu-id="cdb96-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="cdb96-113">Una clase derivada de `employee` puede leer el valor de `salary`, pero solo la clase `employee` puede establecerlo.</span><span class="sxs-lookup"><span data-stu-id="cdb96-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb96-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdb96-114">See also</span></span>

- [<span data-ttu-id="cdb96-115">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="cdb96-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="cdb96-116">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="cdb96-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="cdb96-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="cdb96-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="cdb96-118">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cdb96-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="cdb96-119">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cdb96-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="cdb96-120">Crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="cdb96-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="cdb96-121">Llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="cdb96-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="cdb96-122">Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cdb96-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="cdb96-123">Establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="cdb96-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="cdb96-124">Obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="cdb96-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
