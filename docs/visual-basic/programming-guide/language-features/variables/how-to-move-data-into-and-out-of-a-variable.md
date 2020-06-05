---
title: Procedimiento para introducir y extraer los datos de una variable
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: fe19a6160623aa9ea867becdf7a15b51319abf45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410443"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="bf491-102">Cómo: Introducir y extraer los datos de una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf491-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="bf491-103">Para almacenar un valor en una variable, coloque el nombre de la variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="bf491-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="bf491-104">Colocar datos en una variable</span><span class="sxs-lookup"><span data-stu-id="bf491-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="bf491-105">Para almacenar un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="bf491-105">To store a value in a variable</span></span>

- <span data-ttu-id="bf491-106">Use el nombre de la variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="bf491-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="bf491-107">En el ejemplo siguiente se establece el valor de la variable `alpha` .</span><span class="sxs-lookup"><span data-stu-id="bf491-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="bf491-108">El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.</span><span class="sxs-lookup"><span data-stu-id="bf491-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="bf491-109">Obtención de datos de una variable</span><span class="sxs-lookup"><span data-stu-id="bf491-109">Getting Data from a Variable</span></span>

<span data-ttu-id="bf491-110">Para recuperar el valor de una variable, incluya el nombre de la variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="bf491-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="bf491-111">Para recuperar un valor de una variable</span><span class="sxs-lookup"><span data-stu-id="bf491-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="bf491-112">Use el nombre de la variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="bf491-112">Use the variable name in an expression.</span></span> <span data-ttu-id="bf491-113">Puede usar una variable en cualquier parte donde pueda usar una constante o un literal, excepto en una expresión que defina el valor de una constante.</span><span class="sxs-lookup"><span data-stu-id="bf491-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="bf491-114">O bien</span><span class="sxs-lookup"><span data-stu-id="bf491-114">\-or-</span></span>

- <span data-ttu-id="bf491-115">Use el nombre de la variable que sigue el signo igual ( `=` ) en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="bf491-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="bf491-116">En el ejemplo siguiente se lee el valor de la variable `startValue` y, a continuación, se usa el valor de la variable `counter` en una expresión.</span><span class="sxs-lookup"><span data-stu-id="bf491-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="bf491-117">El valor de la variable participa en la expresión de la misma forma que una constante y, a continuación, se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="bf491-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf491-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf491-118">See also</span></span>

- [<span data-ttu-id="bf491-119">Variables</span><span class="sxs-lookup"><span data-stu-id="bf491-119">Variables</span></span>](index.md)
- [<span data-ttu-id="bf491-120">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="bf491-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="bf491-121">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="bf491-121">Object Variables</span></span>](object-variables.md)
