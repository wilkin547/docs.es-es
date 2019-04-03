---
title: La variable '<variablename>' oculta una variable en un bloque de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 15c35cbb829bec782771b584ea25b111b81b5e1f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827138"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="d4de0-102">Variable '\<NombreDeVariable >' oculta una variable en un bloque de inclusión</span><span class="sxs-lookup"><span data-stu-id="d4de0-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="d4de0-103">Una variable incluida en un bloque tiene el mismo nombre que otra variable local.</span><span class="sxs-lookup"><span data-stu-id="d4de0-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="d4de0-104">**Identificador de error:** BC30616</span><span class="sxs-lookup"><span data-stu-id="d4de0-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4de0-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d4de0-105">To correct this error</span></span>  
  
-   <span data-ttu-id="d4de0-106">Cambiar el nombre de la variable del bloque contenedor para que no sea igual que cualquier otra variable local.</span><span class="sxs-lookup"><span data-stu-id="d4de0-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="d4de0-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d4de0-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="d4de0-108">Una causa común de este error es el uso de `Catch e As Exception` dentro de un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d4de0-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="d4de0-109">Si este es el caso, el nombre del `Catch` variable de bloque `ex` lugar `e`.</span><span class="sxs-lookup"><span data-stu-id="d4de0-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="d4de0-110">Otra fuente común de este error es un intento para tener acceso a una variable local declarada dentro de un `Try` bloquear en otro `Catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="d4de0-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="d4de0-111">Para corregir este problema, declare la variable fuera del `Try...Catch...Finally` estructura.</span><span class="sxs-lookup"><span data-stu-id="d4de0-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4de0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4de0-112">See also</span></span>

- [<span data-ttu-id="d4de0-113">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d4de0-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="d4de0-114">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="d4de0-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
