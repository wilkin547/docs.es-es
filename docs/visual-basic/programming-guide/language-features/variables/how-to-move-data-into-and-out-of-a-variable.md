---
title: Filtrar Movimiento de datos dentro y fuera de una Variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818545"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="e8554-102">Filtrar Movimiento de datos dentro y fuera de una Variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8554-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="e8554-103">Almacenar un valor en una variable colocando el nombre de variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="e8554-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="e8554-104">Colocación de datos en una Variable</span><span class="sxs-lookup"><span data-stu-id="e8554-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="e8554-105">Para almacenar un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="e8554-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="e8554-106">Utilice el nombre de variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="e8554-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="e8554-107">En el ejemplo siguiente se establece el valor de la variable `alpha`.</span><span class="sxs-lookup"><span data-stu-id="e8554-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="e8554-108">El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.</span><span class="sxs-lookup"><span data-stu-id="e8554-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="e8554-109">Obtener datos de una Variable</span><span class="sxs-lookup"><span data-stu-id="e8554-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="e8554-110">Recuperar el valor de una variable mediante la inclusión del nombre de variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e8554-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="e8554-111">Para recuperar un valor de una variable</span><span class="sxs-lookup"><span data-stu-id="e8554-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="e8554-112">Utilice el nombre de variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e8554-112">Use the variable name in an expression.</span></span> <span data-ttu-id="e8554-113">Puede usar una variable en cualquier lugar puede usar una constante o un literal, excepto en una expresión que define el valor de una constante.</span><span class="sxs-lookup"><span data-stu-id="e8554-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="e8554-114">-o bien-</span><span class="sxs-lookup"><span data-stu-id="e8554-114">-or-</span></span>  
  
-   <span data-ttu-id="e8554-115">Utilice el nombre de variable siguiendo la igual (`=`) inicie sesión en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="e8554-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="e8554-116">En el ejemplo siguiente se lee el valor de la variable `startValue` y, a continuación, usa el valor de la variable `counter` en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e8554-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="e8554-117">El valor de la variable participa en la expresión tal como haría una constante y, a continuación, se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="e8554-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8554-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8554-118">See also</span></span>

- [<span data-ttu-id="e8554-119">Variables</span><span class="sxs-lookup"><span data-stu-id="e8554-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="e8554-120">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="e8554-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e8554-121">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="e8554-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
