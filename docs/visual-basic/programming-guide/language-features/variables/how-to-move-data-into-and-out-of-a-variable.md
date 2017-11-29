---
title: "Cómo: Introducir y extraer los datos de una variable (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="dbcf4-102">Cómo: Introducir y extraer los datos de una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbcf4-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="dbcf4-103">Almacenar un valor en una variable colocando el nombre de variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="dbcf4-104">Colocación de datos en una Variable</span><span class="sxs-lookup"><span data-stu-id="dbcf4-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="dbcf4-105">Para almacenar un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="dbcf4-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="dbcf4-106">Utilice el nombre de variable en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="dbcf4-107">En el ejemplo siguiente se establece el valor de la variable `alpha`.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="dbcf4-108">El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="dbcf4-109">Obtener datos de una Variable</span><span class="sxs-lookup"><span data-stu-id="dbcf4-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="dbcf4-110">Recupera el valor de una variable incluyendo el nombre de variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="dbcf4-111">Para recuperar un valor de una variable</span><span class="sxs-lookup"><span data-stu-id="dbcf4-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="dbcf4-112">Utilice el nombre de variable en una expresión.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-112">Use the variable name in an expression.</span></span> <span data-ttu-id="dbcf4-113">Puede utilizar una variable en cualquier lugar puede usar una constante o un literal, excepto en una expresión que define el valor de una constante.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="dbcf4-114">O bien</span><span class="sxs-lookup"><span data-stu-id="dbcf4-114">-or-</span></span>  
  
-   <span data-ttu-id="dbcf4-115">Utilice el nombre de variable siguiendo la igual (`=`) iniciar sesión en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="dbcf4-116">En el ejemplo siguiente se lee el valor de la variable `startValue` y, a continuación, usa el valor de la variable `counter` en una expresión.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="dbcf4-117">El valor de la variable participa en la expresión tal como haría una constante y, a continuación, se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="dbcf4-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcf4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbcf4-118">See Also</span></span>  
 [<span data-ttu-id="dbcf4-119">Variables</span><span class="sxs-lookup"><span data-stu-id="dbcf4-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="dbcf4-120">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="dbcf4-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="dbcf4-121">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="dbcf4-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
