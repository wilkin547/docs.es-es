---
title: La variable '<variablename>' oculta una variable en un bloque de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406526"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="076b8-102">La variable '\<variablename>' oculta una variable en un bloque de inclusión</span><span class="sxs-lookup"><span data-stu-id="076b8-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="076b8-103">Una variable encerrada en un bloque tiene el mismo nombre que otra variable local.</span><span class="sxs-lookup"><span data-stu-id="076b8-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="076b8-104">**Identificador de error:** BC30616</span><span class="sxs-lookup"><span data-stu-id="076b8-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="076b8-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="076b8-105">To correct this error</span></span>  
  
- <span data-ttu-id="076b8-106">Cambie el nombre de la variable en el bloque incluido para que no sea el mismo que cualquier otra variable local.</span><span class="sxs-lookup"><span data-stu-id="076b8-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="076b8-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="076b8-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="076b8-108">Una causa común de este error es el uso de `Catch e As Exception` dentro de un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="076b8-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="076b8-109">En este caso, asigne un nombre `Catch` a la variable de bloque `ex` en lugar de `e` .</span><span class="sxs-lookup"><span data-stu-id="076b8-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="076b8-110">Otro origen común de este error es un intento de obtener acceso a una variable local declarada dentro de un `Try` bloque en un `Catch` bloque independiente.</span><span class="sxs-lookup"><span data-stu-id="076b8-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="076b8-111">Para corregir esto, declare la variable fuera de la `Try...Catch...Finally` estructura.</span><span class="sxs-lookup"><span data-stu-id="076b8-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="076b8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="076b8-112">See also</span></span>

- [<span data-ttu-id="076b8-113">Instrucción Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="076b8-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="076b8-114">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="076b8-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
