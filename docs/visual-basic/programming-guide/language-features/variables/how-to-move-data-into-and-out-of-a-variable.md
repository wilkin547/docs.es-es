---
title: Procedimiento Movimiento de datos dentro y fuera de una variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: df55f122c4ea029a383196f8d9684295ac8926aa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631126"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="833ed-102">Procedimiento Movimiento de datos dentro y fuera de una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="833ed-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="833ed-103">Para almacenar un valor en una variable, coloque el nombre de la variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="833ed-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="833ed-104">Colocar datos en una variable</span><span class="sxs-lookup"><span data-stu-id="833ed-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="833ed-105">Para almacenar un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="833ed-105">To store a value in a variable</span></span>

- <span data-ttu-id="833ed-106">Use el nombre de la variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="833ed-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="833ed-107">En el ejemplo siguiente se establece el valor de `alpha`la variable.</span><span class="sxs-lookup"><span data-stu-id="833ed-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="833ed-108">El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.</span><span class="sxs-lookup"><span data-stu-id="833ed-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="833ed-109">Obtención de datos de una variable</span><span class="sxs-lookup"><span data-stu-id="833ed-109">Getting Data from a Variable</span></span>

<span data-ttu-id="833ed-110">Para recuperar el valor de una variable, incluya el nombre de la variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="833ed-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="833ed-111">Para recuperar un valor de una variable</span><span class="sxs-lookup"><span data-stu-id="833ed-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="833ed-112">Use el nombre de la variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="833ed-112">Use the variable name in an expression.</span></span> <span data-ttu-id="833ed-113">Puede usar una variable en cualquier parte donde pueda usar una constante o un literal, excepto en una expresión que defina el valor de una constante.</span><span class="sxs-lookup"><span data-stu-id="833ed-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="833ed-114">O bien</span><span class="sxs-lookup"><span data-stu-id="833ed-114">\-or-</span></span>

- <span data-ttu-id="833ed-115">Use el nombre de la variable que sigue`=`el signo igual () en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="833ed-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="833ed-116">En el ejemplo siguiente se lee el valor de `startValue` la variable y, a continuación, se `counter` usa el valor de la variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="833ed-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="833ed-117">El valor de la variable participa en la expresión de la misma forma que una constante y, a continuación, se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="833ed-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="833ed-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="833ed-118">See also</span></span>

- [<span data-ttu-id="833ed-119">Variables</span><span class="sxs-lookup"><span data-stu-id="833ed-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="833ed-120">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="833ed-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="833ed-121">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="833ed-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
