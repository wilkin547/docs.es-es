---
description: "Más información sobre: BC30616: la variable ' <variablename> ' oculta una variable en un bloque de inclusión"
title: La variable '<variablename>' oculta una variable en un bloque de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: a0b2a4d024ff0409b5617354b5e671ca6dc0305b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666126"
---
# <a name="bc30616-variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="07f7f-103">BC30616: la variable ' \<variablename> ' oculta una variable en un bloque de inclusión</span><span class="sxs-lookup"><span data-stu-id="07f7f-103">BC30616: Variable '\<variablename>' hides a variable in an enclosing block</span></span>

<span data-ttu-id="07f7f-104">Una variable encerrada en un bloque tiene el mismo nombre que otra variable local.</span><span class="sxs-lookup"><span data-stu-id="07f7f-104">A variable enclosed in a block has the same name as another local variable.</span></span>

 <span data-ttu-id="07f7f-105">**Identificador de error:** BC30616</span><span class="sxs-lookup"><span data-stu-id="07f7f-105">**Error ID:** BC30616</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="07f7f-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="07f7f-106">To correct this error</span></span>

- <span data-ttu-id="07f7f-107">Cambie el nombre de la variable en el bloque incluido para que no sea el mismo que cualquier otra variable local.</span><span class="sxs-lookup"><span data-stu-id="07f7f-107">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="07f7f-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="07f7f-108">For example:</span></span>

    ```vb
    Dim a, b, x As Integer
    If a = b Then
       Dim y As Integer = 20 ' Uniquely named block variable.
    End If
    ```

- <span data-ttu-id="07f7f-109">Una causa común de este error es el uso de `Catch e As Exception` dentro de un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="07f7f-109">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="07f7f-110">En este caso, asigne un nombre `Catch` a la variable de bloque `ex` en lugar de `e` .</span><span class="sxs-lookup"><span data-stu-id="07f7f-110">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>

- <span data-ttu-id="07f7f-111">Otro origen común de este error es un intento de obtener acceso a una variable local declarada dentro de un `Try` bloque en un `Catch` bloque independiente.</span><span class="sxs-lookup"><span data-stu-id="07f7f-111">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="07f7f-112">Para corregir esto, declare la variable fuera de la `Try...Catch...Finally` estructura.</span><span class="sxs-lookup"><span data-stu-id="07f7f-112">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="07f7f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="07f7f-113">See also</span></span>

- [<span data-ttu-id="07f7f-114">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="07f7f-114">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="07f7f-115">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="07f7f-115">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
